# restore
: 특정 영역에 있는 파일을 다른 영역으로 복사(덮어쓰기)하여 되돌리는 것  

<br><img width="50%" alt="image" src="https://github.com/user-attachments/assets/9841d6f2-600d-408f-9aef-fb53230ed7db" /><br>

1: git restore &lt;fileName&gt;        : staging are에 있는 파일을 working directory로 복사  
2: gir restore --staged &lt;fileName&gt; : repository에 았는 파일을 staging area로 복사  
3: git restore --source = 특정시점해쉬코드 or 브랜치명<fileName> : 리포지토리 파일을 즉시 워킹 디렛토리로 복사  
4: git restore --continue : revert 했는데 충돌이 발생하면, 알아서 해결하고 그 후에 revert를 마저 끝내겠다. 라는 의미로 사용

reset (--mixed) 혹은 reset --soft 를 한 후에는 수정된 파일이 reset 이전으로 돌아가진 않음  
하지만 git restore 파일명 으로 파일 내용을 reset 이전으로 되돌릴수있음.  
그러면 git status에서는 history가 제거되고 파일도 수정 전으로 돌아감  

작은 팁 : cmd 창에서 바로 파일의 내용 보는 법 : vi 파일명 
