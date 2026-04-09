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

### 📍 목표 1 : `reset --mixed` + `restore 파일명`
**git reset c1의 hash** 후, **commit history**, **파일상태**    
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/49c82e7c-b9a3-403d-94ba-22a0c8113a2c" /><br>
🩵 결과 :
|              | working directory      | staging area      | commit (HEAD) |
|--------------|------------------------|-------------------|---------------|
| BEFORE reset | a + b                  | 없음              | c2            |
| AFTER reset  | a + b (c2상태 그대로)  | a (c1 상태)       | c1            |    

현재, staging area 에 있는 애는 수정되기 전 파일 (a 내용만 있는)  
현재, working directory 에 있는 애는 수정된 파일 (a, b 내용이 있는)  

즉, working directory에는 a + b 라는 내용이 있는데, 아직 add를 안해서 staging area에는 a 라는 내용만 있는 상태!!!  
그래서 우리는 지금 working directory를 staging are랑 똑같은 상태로 맞추고싶음
<br><br>

**git restore 파일명** 후, **commit history**, **파일상태**     
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/b6a49d21-1c04-410a-8e37-5f539e583187" /><br>
🩵 결과 : working directory를 staging 상태로 맞춰버림 →  test.txt 파일에 a 가 적혀 있음 !! 
|               | working directory | staging area | commit (HEAD) |
|---------------|-------------------|--------------|---------------|
| AFTER restore | a                 | a            | c1            |  

<br><br><br>

### 📍 목표 2 : `reset --soft` + `restore --staged` + `restore`
**git reset --soft c1.hash** 후, **commit history**, **파일상태**    
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/61db5f08-cb3a-45ee-9f87-112bab23955e" />
<br>
**git restore --staged &lt;fileName&gt;** 후, **commit history**, **파일상태**    
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/7495efc7-3cb0-493b-b928-2eec570ad3bc" /><br>
**git restore &lt;fileName&gt;** 후, **commit history**, **파일상태**    
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/036df60c-933a-4f5c-9c03-c58e8e381185" /><br>
|                                          | working directory | staging area | repository |
|------------------------------------------|-------------------|--------------|------------|
| git reset --soft c1.hash 후              | a<br><br>b        | a<br><br>b   | a          |  
| git restore --staged &lt;fileName&gt; 후 | a<br><br>b        | a            | a          |  
| git restore &lt;fileName&gt; 후          | a                 | a            | a          |   

세 영역이 모두 동일한 내용으로 덮어씌워지기 되어서 다 똑같아짐  

<br><br><br>
