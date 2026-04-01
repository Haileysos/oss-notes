reset 

C1--C2--C3--C4 (HEAD)일 때
- git rest C2 -> 기본적으로 --mixed (=git reset --mixed C2) 옵션과 동일함
  - C1--C2(HEAD) <- C3,C4는 사라짐(변경 내용만 남음)
  -파일 내용은 유지하고 commit만 되돌리고 싶을때


soft
-> C2 이후 변경사항을 "모두 add 된 상테(staging상태)로 유지"
mixed
-> C2 이후 변경사항을 "모두 수정된 상태(unstaged)로 유지"
hard
-> C2 이후 변경사항을 "모두삭제" 


# 실습  


| Widget    | Description                                    | |
| ---------- | ---------------------------------------------- | --|
| <img width="50%" alt="image" src="https://github.com/user-attachments/assets/4e0cffa3-c849-4c02-a7b2-e878b08c7590" /> | resetA.txt 파일생성   | working directory                 |
|                                                                                                                       | git add resetA.txt    | working directory -> staging area |
|                                                                                                                       | git commit -m "c1"    | repository                        |
| <img width="50%" alt="image" src="https://github.com/user-attachments/assets/c3834bd5-886c-4aeb-970f-fb919cdb920d" /> | resetB.txt 파일생성   | working directory                 |
|                                                                                                                       | git add resetB.txt    | working directory -> staging area |
|                                                                                                                       | git commit -m "c2"    | repository                        |
| <img width="50%" alt="image" src="https://github.com/user-attachments/assets/1408b7bc-ee11-4c8c-ac72-c2b9c85c7139" /> | resetA 파일 내용 수정 | working directory                 | 
|                                                                                                                       | git add resetA.txt    | working directory -> staging area |
|                                                                                                                       | git commit -m "c3"    | repository                        |   

**commit history**  
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/76afe9a0-cb66-423c-a874-a1a0424113b6" /><br>  
<br><br>

### 목표 : c1으로 돌아가기  
📍 **git reset --soft c1의 hash** 후, **commit history**  확인  
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/34bd20b4-3e91-4823-a4bf-7196813898d6" /><br>
🩵 결과 : c2, c3 가 commit history 에서 지워짐 !! 
<br>  

☑️ 상태확인
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/5fa9506a-281b-4f93-9175-2cdb599086e0" /><br>
🩵 결과 : 파일들이 add된 상태로(tracked) staging area에 있음 !!
