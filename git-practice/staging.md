# Practice : add & reset  
<br><br>
폴더에 A_ver1.hwp , B_ver1.hwp 파일을 만들어보자 (각 파일에는 A ver.1 , B ver1 이라는 내용이 저장되어잇어야 함)
<br><br><img width="60%" alt="Image" src="https://github.com/user-attachments/assets/bd06cd2b-f080-4b5b-9eb1-3727775e7f67" /><br><br>

git status 명령어를 쳐서 확인해보자
<br><br><img width="60%" alt="Image" src="https://github.com/user-attachments/assets/15e7a966-420b-459a-8628-3f52b2b33804" /><br><br>
빨간 글씨로 내가 만들었던 파일들의 이름이 나옴 (이 파일들은 untracked files로 확인이 됨)
<br><br><br><br><br><br>
## git add  
`git add A_ver1.hwp` 로 A_ver1.hwp 파일을 staging area 에 추가해보자
<br><br><img width="60%" alt="Image" src="https://github.com/user-attachments/assets/1f52a416-cf33-410e-91b4-c7677b6aae3e" /><br><br>
`git status` 로 확인해보자
<br><br><img width="60%" alt="Image" src="https://github.com/user-attachments/assets/de6e96f4-5aaa-4a3e-8b8d-29b52115c95a" /><br><br>
untracked files 에 있던 A_ver1.hwp 파일이 stage 로 올라감 (녹색글씨)  
이 파일은 commit 명령어로 갈 준비가 된 것이다. 즉, git에 의해서 tracking이 된 것  

그래서 보통 원하는 파일 골라서 add 하면 됨. 근데 한꺼번에 모든 파일을 add 하고 싶으면 `git add.` 
<br><br><br><br><br><br>
## git reset  
add 했던 파일을 취소하고 싶으면 `git reset A_ver1.hwp` 하면된다 
<br><br><img width="60%" alt="Image" src="https://github.com/user-attachments/assets/09c60063-efa7-4d33-9a35-db52e20db207" /><br><br>
`git status` 로 확인해보자 
<br><br><img width="60%" alt="Image" src="https://github.com/user-attachments/assets/33ab99bf-7325-4922-a3d6-fb79ddc65470" /><br><br>
A_ver1.hwp 파일이 다시 Untracked files 로 이동이 되어있음을 확인할 수 있다
