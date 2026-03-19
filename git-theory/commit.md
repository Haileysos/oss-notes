<img width="1450" height="140" alt="image" src="https://github.com/user-attachments/assets/327bdecd-cb95-407b-b08d-835e211e4332" /><img width="1273" height="320" alt="image" src="https://github.com/user-attachments/assets/12f78caa-a731-4bd7-a472-55a3a1534906" />

## commit

"commit한다" = "하나의 버전으로 기록한다"  
staging area (장바구니)에 있는 모든것이 하나의 상자로 잘 포장되어 repository에 차곡차곡 쌓임  
-붉은색표시=현재커밋
-문자열=40자16진수의hash
-hash=commit을 식별하기위한 고유 아이디

현재 A만 add한 상태
<img width="1273" height="320" alt="Image" src="https://github.com/user-attachments/assets/d08acf82-8ce0-4bee-bda1-695bd127e615" />
- git commit -m "메모내용"
메모내용은 간결하면서도 모든 내용이 포함되는 명확한 문장 혹은 단어여야 함. 웬만하면 한글쓰지마소
<img width="1451" height="96" alt="Image" src="https://github.com/user-attachments/assets/26492e43-a1d7-4443-9ad8-52a1dd25e84b" />

에러남.. 이메일을 등록하지 않았기 때문임. 글로벌로 사용자 지정해보소 나는 아무 그거없이 잘 되길래 git config --list 로 확인해보니까 이미 글로벌 이엇음 (?) 근데 이메일이 지정되어잇어야 되는거라는 말씀을 하시네 뭐지

git status 하면 A 파일 없어져잇음


- git log : git의 commit 상태 확인
<img width="1450" height="140" alt="Image" src="https://github.com/user-attachments/assets/c8a0d565-19a1-4a5d-9c3a-478f73bf7fb9" />
hash 정보 (노랑글씨) / commit 메모 내용 / (HEAD -> master) 이거 중요함 ★ 근데 나중에 설명할게염

git status 로 확인을 해 보면 stage 에 있던 A_ver1.hwp 파일이 commit 되어 사라져 있음
<img width="1446" height="165" alt="Image" src="https://github.com/user-attachments/assets/40eb5c71-bf2e-410a-abdf-d6a63cc6e9a6" />
남아잇는 B파일도 commit 하기


git add B_ver1.hwp
git commit -m "B_ver1"
<img width="1405" height="113" alt="Image" src="https://github.com/user-attachments/assets/a89ad25e-49da-4e23-b505-811288fbf697" />
git log로 확인
<img width="1397" height="277" alt="Image" src="https://github.com/user-attachments/assets/d5d8a368-f0ba-497d-95c6-b80a1d3cea6b" />
가장 최근에 commit한 것이 위로 쌓임, 헤드의 위치도 바뀜
git status도 확인해보기
<img width="1388" height="75" alt="Image" src="https://github.com/user-attachments/assets/6aae65e9-0e68-418c-b4c4-181a9de3b44b" />
A_ver1.hwp, B_ver1.hwp 두 개의 파일 모두 commit 되어 없어짐


## git reset
commit을 취소하는 방벙 -> git reset 돌아가고자하는 commit hash 번호
- git reset db7bc572853082f1d0947922dab042a0b2993470
<img width="1432" height="23" alt="Image" src="https://github.com/user-attachments/assets/7680ef94-5405-4ce8-905c-0b7c990e1fb1" />
git log 로 확인하기
<img width="1447" height="136" alt="Image" src="https://github.com/user-attachments/assets/795fe26a-b31b-4fa8-a28b-6b4b0270bcbb" />
git status 해서 확인해보면
<img width="1446" height="162" alt="Image" src="https://github.com/user-attachments/assets/bd6bf351-9794-4b7c-a11f-905161af4ecd" />

reset 을 해서 돌아가면 없어진 commit에서 수정했던 파일 내용은그대로 있고
(mixed(기본값)와 soft는 변하지 않음, hard는 수정 전 상태로 돌아감 <-나중에..)
add이전 상태로 남아잇음
해당 파일 수정을 다시하고 add -> commit 하면 됨
reset과 revert 차이점?




파일비교
git diff : 파일 을 수정했울 때 수정내용울보옂ㅜㅁ
- add 하기전에는 git diff 명령어로 바로 볼 수 있움
- commit을 한 다음에는 commit number 를 이용해 git diff A B 로 볼 수 있음
   - A,B 는 커밋 넘버
   - A:기준이 되는넘버, B:비교할 넘버
- git log --patch : 각 commit의 diff 결과를 다 보여줌
git diff c1882cf1e8a1344e8b487316105bb06d292f05d2 1f0250cc18cb8f8d43f9d32928b65842ae8dac8d
<<txt 파일로 다시해보기>>
그러면 결과가 좀 다름 
-- a/test.txt
-- b/test.txt
ver1
ver2
no newline at end of file
.... 결과 해석해오기!!



