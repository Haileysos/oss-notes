
# 실습  


| Widget    | Description                                    | |
| ---------- | ---------------------------------------------- | --|
| <img width="50%" alt="image" src="https://github.com/user-attachments/assets/ad504eed-793b-4ef5-9244-cb4cef2e7437" /> | A.txt 파일생성                       | working directory                 |
|                                                                                                                       | git add A.txt                        | working directory → staging area  |
|                                                                                                                       | git commit -m "add A file"           | staging area → repository         |
| <img width="50%" alt="image" src="https://github.com/user-attachments/assets/7354ac6c-c497-4dbb-821a-cdd0650eb460" /> | B.txt 파일생성                       | working directory                 |
|                                                                                                                       | git add B.txt                        | working directory → staging area  |
|                                                                                                                       | git commit -m "add B file"           | staging area → repository         |
| <img width="50%" alt="image" src="https://github.com/user-attachments/assets/68263a9d-4bbf-4179-9673-b1143d22ce6f" /> | A 파일 내용 수정                     | working directory                 | 
|                                                                                                                       | git add A.txt                        | working directory → staging area  |
|                                                                                                                       | git commit -m "modified A file ver1" | staging area → repository         |   

**commit history**  
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/609ce460-194d-4b7b-899f-92189db11386" />
<br>  
<br><br>

### 📍 목표 1 : c3 commit 을 취소하기 `revert c3.hash`
**git revert c3.hash**, **commit history**  확인  
<br><img width="60%" alt="image" src="https://github.com/user-attachments/assets/609a19d7-5969-4007-8299-d1f989e76b50" />
<br>
🩵 결과 : 새로운 커밋이 생겼음!! + A 파일이 c3 commit 하기 전으로 되돌아 감
| revert 전 | revert 후|
|---|---|
|<img width="50%" alt="image" src="https://github.com/user-attachments/assets/68263a9d-4bbf-4179-9673-b1143d22ce6f" />|<img width="50%" alt="image" src="https://github.com/user-attachments/assets/ad504eed-793b-4ef5-9244-cb4cef2e7437" />|

<br><br><br>

### 📍 목표 2 : c1 commit 을 취소하기 `revert c1.hash`
**git revert c1.hash**  하면  
CONFLICT (modify/delete) 라고 노랗게 뜨면서 충돌 발생  
git rm A.txt  
git revert --continue  
git log  
<br>
결과 :  
revert c1 의 목적 = c1을 취소하는 것  
c1 = A.txt 생성  
c1취소 = A.txt 삭제  
따라서 revert c1 의 목적 = A.txt 를 삭제하는 것  
BUT 이미 A.txt는 수정이 된 상태임 (c3)  
따라서 충돌이 발생한 것이다.  
이를 해결하는 방법은 A.txt를 직접 삭제하는 것.  
그래서 git rm A.txt로 내가 삭제하고자 하는 파일을 직접 삭제했고,  
충돌문제를 해결했기 때문에 revert --continue 로 revert를 마무리한다.  

<br><br><br>
