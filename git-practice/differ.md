## 파일비교
<img width="1448" height="277" alt="Image" src="https://github.com/user-attachments/assets/5aff9479-790f-4428-b658-c1319f852856" />

## diff  
git diff : 파일을 수정했을 때 수정내용울 보여줌
- add 하기전에는 git diff 명령어로 바로 볼 수 있움
- commit을 한 다음에는 commit number 를 이용해 git diff A B 로 볼 수 있음
   - A,B 는 커밋 넘버
   - A : 기준이 되는넘버, B : 비교할 넘버
- git diff 8a24d26c2b98d6e57bcd4fd7c6fff121a7aa435c 395d1a75af9f03e3829a11808ccb4cb7d2cb0522  
<img width="1442" height="92" alt="image" src="https://github.com/user-attachments/assets/5f4f5922-fb6d-49b1-811f-124a1cdfcaff" />  
- git log --patch : 각 commit의 diff 결과를 다 보여줌  
<img width="1428" height="483" alt="image" src="https://github.com/user-attachments/assets/972d26ca-5be0-4c3c-97d0-770aaced837a" />  


git diff c1882cf1e8a1344e8b487316105bb06d292f05d2 1f0250cc18cb8f8d43f9d32928b65842ae8dac8d
<<txt 파일로 다시해보기>>
A1.txt 파일
<img width="352" height="266" alt="image" src="https://github.com/user-attachments/assets/1a9e2c3a-f6a8-4dcc-b6be-6767e158e4e5" />
A1.txt 파일에 A2 라는 내용을 추가함
<img width="352" height="292" alt="image" src="https://github.com/user-attachments/assets/fcaed32f-da36-4c63-98cc-24cff8a0addb" />

그러면 결과가 좀 다름 
-- a/test.txt
-- b/test.txt
ver1
ver2
no newline at end of file
.... 결과 해석해오기!!
