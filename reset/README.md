# reset  

C4 (HEAD)일 때      git rest (--mixed) C2hash 를 하면      C2(HEAD)  
C3                                C1  
C2                                 ↓  
C1                              C3, C4 는 사라짐  
                              BUT 변경 내용만 남음  

: 즉, 파일의 내용은 유지하고 commit만 되돌리고 싶을 때 사용

### `git reset --(   ) hash`  
- soft : C2 이후 변경사항을 "모두 add 된 상태(staging상태)로 유지"

- mixed : C2 이후 변경사항을 "모두 수정된 상태(unstaged)로 유지"

- hard : C2 이후 변경사항을 "모두삭제"   

### `git reset 파일명`  
- 특정파일만 reset하는것도 가능!

### `git reset hash` → 되돌리기
- reset 하는 것도 / 되돌리는 것도 명령어가 같음  
- hash값만 알고 있다면 언제든지 그 시점으로 repository의 포인터(HEAD)를 옮길 수 잇음  

<br><br><br>
ㅇ --hard 모드도 실제로 모든것이 삭제되는 것이 아님
ㅇ 커밋이후 변경 사항들을 어디에 둘것이냐에 따라 동작 방식이 달라지는 것임
ㅇ git은 모든 브랜치 이동,리셋,체크아웃 등의 기록들은 내부적으로 "reflog"에 저장됨
    - reflog 에서도 일정 시간이 지나면 사라짐 : 일반적으로 90일
