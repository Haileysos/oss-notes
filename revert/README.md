# revert
- 이미 만든 commit을 취소하는 새로운 commit 생성  
- git revert [취소하려는 commit id] <----> git reset [돌아가려는 commit id]  
- reset과 달리 history를 삭제하지 않고 남겨두기 때문에 안전하게 되돌아가기 가능  
- 협업 중이나 이미 push한 commit을 되돌릴 때 적합함
  <br><br><br>
  A ----> B -----> C ----> D  
          (HEAD)

D,C를 차례로 revert 하면  

  A ----> B -----> C ----> D ----> D' ----> C'  
                 (HEAD)  
