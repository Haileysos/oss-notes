# Practice : diff
<br><br>
A_ver1.hwp 파일 에 A1 이라는 내용이 있는 상태에서 커밋 한 후, A2 라는 내용을 추가하고 또 커밋을 한 상태이다.
<br><br><img width="1448" height="277" alt="Image" src="https://github.com/user-attachments/assets/5aff9479-790f-4428-b658-c1319f852856" /><br><br>

## diff  
`git diff A B` : 파일을 수정했을 때 수정내용을 보여줌  
- add 하기 전에는 git diff 명령어로 바로 볼 수 있음  
- commit을 한 다음에는 commit number 를 이용해 git diff A B 로 볼 수 있음  
   - A,B 는 커밋 넘버  
   - A : 기준이 되는넘버, B : 비교할 넘버  
<br><br><img width="1442" height="92" alt="image" src="https://github.com/user-attachments/assets/5f4f5922-fb6d-49b1-811f-124a1cdfcaff" /><br><br>
- `git log --patch` : 각 commit의 diff 결과를 다 보여줌  
<br><br><img width="1428" height="483" alt="image" src="https://github.com/user-attachments/assets/972d26ca-5be0-4c3c-97d0-770aaced837a" /><br><br>
뭔가가 이상한 느낌!
<br><br><br><br>
# txt 파일로 다시해보기
<br><br>
A1.txt 파일
<br><br><img width="352" height="266" alt="image" src="https://github.com/user-attachments/assets/1a9e2c3a-f6a8-4dcc-b6be-6767e158e4e5" /><br><br>
A1.txt 파일 add > commit > log로 확인
<br><br><img width="1441" height="853" alt="image" src="https://github.com/user-attachments/assets/7f11a20b-a155-4ec3-b278-f33d4e292176" /><br><br>
A1.txt 파일에 A2 라는 내용을 추가함
<br><br><img width="352" height="292" alt="image" src="https://github.com/user-attachments/assets/fcaed32f-da36-4c63-98cc-24cff8a0addb" /><br><br>
내용을 추가(수정)한 A1.txt 파일 add > commit > log로 확인
<br><br><img width="1435" height="921" alt="image" src="https://github.com/user-attachments/assets/ab81ed31-7e11-4687-9dbb-36a959fbf5cb" /><br><br>
<br><br>
- `git diff A B`
<br><br><img width="1455" height="251" alt="image" src="https://github.com/user-attachments/assets/d80928fb-6255-454e-88ff-c47ac83b2995" /><br><br>

원래 파일: A1  
수정 후: A1  
         A2  
🔍 diff 결과  
-A1  
+A1  
+A2  
❗ 왜 A1이 삭제됐다가 다시 추가된 것처럼 보일까?  
줄 단위 비교라서 그렇게 보이는 것뿐이고, 실제로 A1은 수정된 게 아님  
git diff는 “줄(line)” 단위로 비교함  
즉, 한 줄짜리 파일이 두 줄짜리 파일로 바뀜  
Git은 변경 사항을 줄 단위로 비교하기 때문에, 기존의 A1이 삭제된 후 새로운 A1, A2가 추가된 것으로 표시된다.  
하지만 실제로는 기존 내용은 유지되고 A2가 추가된 것이다.  
