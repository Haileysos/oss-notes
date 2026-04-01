# 실습  


| Widget    | Description                                    | |
| ---------- | ---------------------------------------------- | --|
| <img width="50%" alt="image" src="https://github.com/user-attachments/assets/2408d05f-9be3-4047-b59f-30165fa76d95" /> | test.txt 파일 생성      | working directory                 |
|                                                                                                                       | git add test.txt        | working directory → staging area  |
|                                                                                                                       | git commit -m "c1"      | staging area → repository         |
| <img width="50%" alt="image" src="https://github.com/user-attachments/assets/460fde8b-3efc-4121-a149-783c7d7c2eb3" /> | test.txt 파일 내용 수정 | working directory                 | 
|                                                                                                                       | git add test.txt        | working directory → staging area  |
|                                                                                                                       | git commit -m "c2"      | staging area → repository         |   

**commit history**  
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/522cf3af-effd-453b-bfaf-52d85701952c" />
<br>  
<br><br>

### 목표 1 : `reset --mixed` `restore 파일명`
📍 **git reset c1의 hash** 후, **commit history**, **파일상태**    
<br><img width="1316" height="390" alt="image" src="https://github.com/user-attachments/assets/49c82e7c-b9a3-403d-94ba-22a0c8113a2c" /><br>
🩵 결과 : 파일이 add되지 않은 상태로 working directory 에 있음,  c2 가 commit history 에서 지워짐 !!  
<br>  

📍 **git restore 파일명** 후,@@@@@@@@@@@@@@@@@@@@@
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/5fa9506a-281b-4f93-9175-2cdb599086e0" /><br>
🩵 결과 : 파일들이 add된 상태로(tracked) staging area에 있음 !!
<br><br><br>
