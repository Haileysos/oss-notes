파일 수정 해보자
A_ver1.hwp 에 "A ver.2" 내용 추가
git status 로 확인 - 해당 파일이 modified라고 알림
modified A_ver1.hwp파일을 commit하기! (메모내용:A_ver2)

PS C:\OSS> git init
Initialized empty Git repository in C:/OSS/.git/
PS C:\OSS> git add A_ver1.hwp
PS C:\OSS> git commit -m "A_ver2"
[master (root-commit) 2ddbae9] A_ver2
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 A_ver1.hwp
PS C:\OSS> git log
