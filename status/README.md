# git status
- 초록 메세지 : repository의 상태와 staging area의 상태가 다를 때 (commit할 준비가 됨)  
- 빨간 메세지: staging area의 상태와 working directory의 상태가 다를 때 (수정했지만 아직 commit할 준비 안됨)
 
파일을 수정하고 저장하는 즉시, 항상 working directory에 기록 됨  
편집기로 파일을 열어서 보는 모든 내용은 오직 워킹 디렉터리에 있는 상태를 보여줌  

<img width="40%" alt="image" src="https://github.com/user-attachments/assets/e7f7cdcf-4106-4115-97d0-23f729e15e84" />  

결국 git은 내부적으로 working directory, staging area, repository 라는 세 가지 공간에 각각 동일한 파일의 snapshot을 보관하고 관리  

→ 특정 시점의 파일 내용 전체를 서로 다른 영역에 가지고 있음  

→ 파일을 세 군데나 따로 두는 이유 : "검토와 취소"를 유연하게 하기 위함  

→ git commit을 완료한 직후에는 세 영역의 파일 내용이 모두 일치하게 되기 때문에 git status를 입력하면 "nothing to commit, working tree clean"라는 메세지가 출력됨  



