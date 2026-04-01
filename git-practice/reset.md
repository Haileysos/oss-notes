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

