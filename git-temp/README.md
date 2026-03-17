
cmd open
cd C:\Users\gywls\OneDrive\바탕 화면\OSS : 해당 경로로 이동
git init : 깃으로 사용할 폴더를 설정해야하는데 깃 이닛 하면 설정이됨 그리고 해당 폴더에 .git 이라는 파일이 만들어짐
<img width="921" height="27" alt="Image" src="https://github.com/user-attachments/assets/099dacde-4279-4366-a135-05b0b8f289b6" />
dir :  해당 폴더안에 들어잇는것들을 보여줌
<img width="923" height="22" alt="Image" src="https://github.com/user-attachments/assets/77ae2f34-d616-4e8d-9962-48f49271ec0c" />
폴더 > 옵션 > 보기 > 숨김 파일 표시 설정하기 (그래야 .git 파일이 눈에 보임)
ㅡㅡ여기까지가 일단 깃으로 쓸 파일을 설정하는 단계 ㅡㅡ


Git 사용자 등록 예
git config --global user.name "name"
git config --global user.email "email"
<img width="925" height="25" alt="Image" src="https://github.com/user-attachments/assets/61ceb8f7-96cb-4ed6-a966-717f219567f7" />  
해당 local(폴더)에 사용자 지정 - local 설정 파일 : 하나의 Repository에만 적용 (git config --local)
global에 사용 - global 설정 파일 : 한 사용자의 전체 Git Repository에 적용(git config --global)
해당 system에 사용지 지정 - system 설정 파일 : 모든 시스템 사용자에게 적용 (git config --system)
설정 읽을 때 우선순위 1. local 2. global 3. system에
system>global>local

PS C:\OSS> git config --local user.name "Hailey"
-> OSS 폴더에서 사용자(Hailey)를 local로 등록

PS C:\OSS> git config --list
->
<img width="922" height="622" alt="Image" src="https://github.com/user-attachments/assets/74581a1a-2602-4774-939a-9a12270ab340" />
  
다른 폴더가서 git config --list 하면 나타나지않음 내이름같은거 등등 즉 결국 해당폴더(OSS)만 git이 Hailey로 설정한거임

git local 사용자 삭제
local로 등록한 사용자를 삭제하려면 해당폴더로 이동후 unset
git config --local --unset user.name
<img width="923" height="27" alt="Image" src="https://github.com/user-attachments/assets/4c84aae3-45dc-4310-9c52-fde8d83b5f4a" />

로컬 사용자가 이미 등록되어잇는 파일에다가 사용자를 글로벌로 등록해보자
git config --global user.name "Hailey_global"
<img width="907" height="26" alt="Image" src="https://github.com/user-attachments/assets/66ee8b6d-3a59-4d01-806c-8acd2a774577" />
git config --list 로 확인해보니 user.name=Hailey_global 로 되었다!
<img width="917" height="626" alt="Image" src="https://github.com/user-attachments/assets/cfb5dc93-31d3-4c52-a8b8-a9f3af8286d4" />
해당 폴더가 아닌 다른 경로에 가서 설정을 확인해보면 사용자(Hailey_global)가 동일하게 등록되어잇음을 확인할수잇다.

git global 사용자 삭제
global로 등록한 사용자를 삭제하려면 해당폴더로 이동후 unset
어느 경로에서 확인하든 전부 삭제되엇음을 확인할수잇다. 
unset 과 global 은 순서상관없음 (local도 마찬가지 )
git config --global --unset user.name
git config --unset --global user.name


























ㅡㅡ사용자등록은 여기까지ㅡㅡ

git사용
git의 영역들 
- working directory :현재작업하고잇는 영역(쇼핑)
- staging area : 잠깐 대기하는 영역 (장바구니)
- repository : git 과 관련된 모든 데이터가 이곳에 저장(최종구매)  

untracked                                   Tracking
작업디렉터리      -----git add----> 스테이징 영역 -----git commit---> 리포지토리
working directory                            staging area                              repository(.git)

git status : 작업 디렉토리(working directory  )와 스태이징 영억(staging area )의 상태를 확인
장바구니에담는 명령어가 add 구매를 한다는 명령어는 commit  
















ㅡㅡ실습 ㅡㅡ

폴더에 A_ver1.hwp , B_ver1.hwp 파일을 만들어보자 (각 파일에는 A ver.1 , B ver1 이라는 내용이 저장되어잇어야 함)
<img width="737" height="202" alt="Image" src="https://github.com/user-attachments/assets/bd06cd2b-f080-4b5b-9eb1-3727775e7f67" />

git status 명령어를 쳐서 확인해보자
<img width="928" height="256" alt="Image" src="https://github.com/user-attachments/assets/15e7a966-420b-459a-8628-3f52b2b33804" />
빨간글씨로 내가 만들었던 파일들의 이름이 나옴 (이 파일들은 untracked files로 확인이 됨)

add
git add A_ver1.hwp 로 A_ver1.hwp 파일만 staging area 에 추가해보자
<img width="916" height="25" alt="Image" src="https://github.com/user-attachments/assets/1f52a416-cf33-410e-91b4-c7677b6aae3e" />
git status 명령어를 쳐서 확인해보자
<img width="922" height="292" alt="Image" src="https://github.com/user-attachments/assets/de6e96f4-5aaa-4a3e-8b8d-29b52115c95a" />
untracked files 에 있던 A 파일이 stage 에 올라감 (녹색글씨)
이 A 파일이 commit 명령어로 갈 준비가 된거임. git에 의해서 tracking이 된거임
그래서 보통 원하는 파일 골라서 애드 애드애드애드 하면됨 근데 한꺼번에모든 파일을 애드 하고싶으면 add하는 명령어 : git add. 사용하면됨

reset
add햇던 파일 A를 취소하고싶으면 git reset A_ver1.hwp 하면된다 
<img width="918" height="25" alt="Image" src="https://github.com/user-attachments/assets/09c60063-efa7-4d33-9a35-db52e20db207" />
git status 명령어를 쳐서 확인해보니 A파일이 다시 Untracked files 로 이동이 되어잇는걸 확인할 수 잇다
<img width="927" height="255" alt="Image" src="https://github.com/user-attachments/assets/33ab99bf-7325-4922-a3d6-fb79ddc65470" />






commit 
중요하다 장바구니에담은걸 결제를 하는 단계니까 중요함

근데 다음시간에 할게요 ㅂㅂ
