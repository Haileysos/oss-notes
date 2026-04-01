
# 실습  


| Widget    | Description                                    | |
| ---------- | ---------------------------------------------- | --|
| <img width="50%" alt="image" src="https://github.com/user-attachments/assets/4e0cffa3-c849-4c02-a7b2-e878b08c7590" /> | resetA.txt 파일생성   | working directory                 |
|                                                                                                                       | git add resetA.txt    | working directory → staging area  |
|                                                                                                                       | git commit -m "c1"    | staging area → repository         |
| <img width="50%" alt="image" src="https://github.com/user-attachments/assets/c3834bd5-886c-4aeb-970f-fb919cdb920d" /> | resetB.txt 파일생성   | working directory                 |
|                                                                                                                       | git add resetB.txt    | working directory → staging area  |
|                                                                                                                       | git commit -m "c2"    | staging area → repository         |
| <img width="50%" alt="image" src="https://github.com/user-attachments/assets/1408b7bc-ee11-4c8c-ac72-c2b9c85c7139" /> | resetA 파일 내용 수정 | working directory                 | 
|                                                                                                                       | git add resetA.txt    | working directory → staging area  |
|                                                                                                                       | git commit -m "c3"    | staging area → repository         |   

**commit history**  
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/76afe9a0-cb66-423c-a874-a1a0424113b6" /><br>  
<br><br>

### 목표 1 : c1으로 돌아가기  
📍 **git reset --soft c1의 hash** 후, **commit history**  확인  
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/34bd20b4-3e91-4823-a4bf-7196813898d6" /><br>
🩵 결과 : c2, c3 가 commit history 에서 지워짐 !! 
<br>  

☑️ 상태확인
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/5fa9506a-281b-4f93-9175-2cdb599086e0" /><br>
🩵 결과 : 파일들이 add된 상태로(tracked) staging area에 있음 !!
<br>

### 목표 2 : staging area 에서 빼기  
📍 위 사진과 같은 상황에서, **git reset c1의 hash** 후, **commit history**  확인  
<br><img width="1321" height="206" alt="image" src="https://github.com/user-attachments/assets/ebbc8c7d-6366-42fc-ba4c-a96e16f969ab" /><br>  
🩵 결과 : 이미 HEAD 라서 commit history 는 변화가 없음  
<br>    

☑️ 상태확인
<br><img width="1283" height="277" alt="image" src="https://github.com/user-attachments/assets/da7fe2ea-308f-4a78-92c9-b39c2197845e" /><br>  
🩵 결과 : 파일들이 add되지 않은 상태로 working directory 에 있음 !!  

🩵 Changes not staged for commit : 
🩵 modified:   resetA.txt  
- resetA.txt 는 working directory에 있지만, 수정사항이 staging area 에 있지 않음
- 이 파일은 이미 git에 의해 추적(tracked)중인 파일 (이미 commit된 적 있기 때문에)
- 파일의 내용은 수정되었지만, 아직 저장(git add)하지 않은 상태
- 수정 O, add X

🩵 Untracked files :
🩵 resetB.txt
- working directory에 있지만 git이 한 번도 관리하지 않은 파일
- 새로생김, add X
<br><br><br>
