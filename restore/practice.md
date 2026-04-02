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

### 📍 목표 1 : `reset --mixed` `restore 파일명`
**git reset c1의 hash** 후, **commit history**, **파일상태**    
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/49c82e7c-b9a3-403d-94ba-22a0c8113a2c" /><br>
🩵 결과 :
|            | working directory      | staging area      | commit (HEAD) |
|------------|------------------------|-------------------|---------------|
|BEFORE reset| a + b                  | 없음              | c2            |
|AFTER reset | 그대로 c2 상태 (a + b) | c1 상태 (a만 있음) | c1            |  
staging area 에 있는 애는 수정되기 전 파일 (a내용만 있는)  
working directory 에 있는 애는 수정된 파일 (a, b 내용이 있는)

<br>  

**git restore 파일명** 후, **commit history**, **파일상태**     
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/b6a49d21-1c04-410a-8e37-5f539e583187" /><br>
🩵 결과 : working directory를 staging 상태로 맞춰버림 →  test.txt 파일에 a 가 적혀 있음 !! 
|             | working directory | staging area | commit (HEAD) |
|-------------|-------------------|--------------|---------------|
|AFTER restore| a                 | a            | c1            |  

<br><br><br>



