# restore

reset (--mixed) 혹은 reset --soft 를 한 후에는 수정된 파일이 reset 이전으로 돌아가진 않음  
하지만 git restore 파일명 으로 파일 내용을 reset 이전으로 되돌릴수있음.  
그러면 git status에서는 history가 제거되고 파일도 수정 전으로 돌아감  
