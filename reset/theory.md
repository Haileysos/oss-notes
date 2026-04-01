# reset  


C4 (HEAD)일 때      git rest (--mixed) C2hash 를 하면      C2(HEAD)  
C3                                C1  
C2                                 ↓  
C1                              C3, C4 는 사라짐  
                              BUT 변경 내용만 남음  


: 즉, 파일의 내용은 유지하고 commit만 되돌리고 싶을 때 사용

- soft : C2 이후 변경사항을 "모두 add 된 상태(staging상태)로 유지"

- mixed : C2 이후 변경사항을 "모두 수정된 상태(unstaged)로 유지"

- hard : C2 이후 변경사항을 "모두삭제"   


