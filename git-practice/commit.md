파일을 수정 해보자
A_ver1.hwp 에 "A ver.2" 내용 추가
<img width="690" height="125" alt="Image" src="https://github.com/user-attachments/assets/2616f688-1994-4b16-997b-b2e571e76177" />

git status 로 확인 - 해당 파일이 modified라고 알림
<img width="1442" height="277" alt="Image" src="https://github.com/user-attachments/assets/dfff5c65-cc73-4b3e-9516-4a283291a199" />

modified A_ver1.hwp파일을 commit하기! (메모내용:add A ver.2)
먼저 add 로 stage에 올려야 함.
<img width="1435" height="245" alt="Image" src="https://github.com/user-attachments/assets/30cb7b34-4b60-4ed3-84b5-cd39a7aa7a33" />
commit 하기
<img width="1452" height="71" alt="Image" src="https://github.com/user-attachments/assets/174f4618-f572-49fe-8392-b4ee64a7433f" />
log로 확인하는 거 캡쳐본 부터 ㄱㄱ









PS C:\OSS> git init
Initialized empty Git repository in C:/OSS/.git/
PS C:\OSS> git add A_ver1.hwp
PS C:\OSS> git commit -m "A_ver2"
[master (root-commit) 2ddbae9] A_ver2
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 A_ver1.hwp
PS C:\OSS> git log
