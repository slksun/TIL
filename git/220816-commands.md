

우리는이 공부를 하면서 git을 사용하기 위해 CLI Shell command와 vim editor를 다룰 수 있을 것입니다.

또한, 코드 관리를 위한 git의 정확한 사용법을 이해할 수 있을 것입니다.


kernal : 하드웨어와 응용프로그램을 이어주는 운영체제의 핵심 시스템소프트웨어입니다.


Linux : 리누스 토발즈가 작성한 커널 혹은 GNU 프로젝트의 라이브러리와 도구가 포함된 운영체제
	PC와 모바일 ,서버 , 임베디드 시스템 등 다양한 분야에서 활용가능
	Redhat , Debian, Ubuntu , Android 등 다양한 배포판이 존재


shell : 운영체제의 커널과 사용자를 이어주는 소프트웨어
	sh : AT&T Bell 연구소의 Steve Bourne이 작성한 유식스 쉘
	csh : 버클리의 Bill Joy가 작성한 유닉스 쉘
	bash : Brian Fox가 작성한 유닉스 쉘
		다양한 운영체제에서 기본 쉘로 채택
	zsh : Paul Falstad가 작성한 유닉스 쉘
		sh 확장형 쉘
		현재까지 가장 완벽한 쉘



shell Command


cd Documents/
mkdir dev
cd .. 
pwd

touch readme.md
mv readme.md bin/
cp readme.md bin/
mv readme.md ./README.txt
rm README.txt

rm -rf bin/
chmod 750 readme.md
cat readme.md
vi readme.md



git 은 vcs (Version Control System) 이다!

== SCM (Source Code Management)

< SCM (Software Configuration Management : 형상관리)




git by Linus Torvalds


- Bitkeeper의 이용약관 위반으로 라이센스 제한에 화가 나 2주만에 만든 분산형 버전관리시스템

- 압도적 업계 1위


Characteristics of git


- 빠른 속도, 단순한 구조

- 분산형 저장소 지원

- 비선형적 개발 (수천개의 브랜치) 가능



Pros of git


- 소스코드 주고받기 없이 동시작업이 가능해져 생산성이 증가

- 수정내용은 commit 단위로 관리 , 배포 뿐 아니라 원하는 시점으로 Checkout 가능

- 새로운 기능 추가는 Branch로 개발하여 편안한 실험이 가능하며, 성공적으로 개발이 완료되면 Merge하여 반영

- 인터넷이 연결되지 않아도 개발할 수 있음




git objects

- Blob : 파일 하나의 내용에 대한 정보

- Tree : Blob이나 subtree의 메타데이터 (디렉토리 위치 , 속성, 이름 등)

- Commit : 커밋 순간의 스냅샷



git Process Flow and Command


Local : working directory , staging area , localrepo 


Remote : remote repo



working directory -> staging area 는 git add.
staging area -> localrepo 는 git commit.
localrepo -> remote repo 는 git push.
remote repo -> localrepo 는 git pull.
localrepo -> working directory는 git checkout






# 단어 설명


ctrl + ==> 글자 사이즈 커지기!

커서

특수문자 $ ==> 쉘이 지금 사용자의 입력을 받을 준비가 되었다!

특수문자 ~ ==> 호칭은 틸드. 의미는 권한없이 사용할 수 있는 최상위 디렉토리! (최상위 폴더!)


pwd ==> 작업 중인 경로를 절대경로로 표시해줌!


ls ==> 하위로 접근할 수 있는 디렉토리나 파일의 이름 출시! 그 중 document 를 찾으면 되겠지!


document 이동? ==> cd Documtnts/


상위폴더가기! ==> cd ..

옵션 : 하위 폴더들을 보고 싶은데 좀 더 디테일하게 보고 싶다! 옵션 (세부 명령)


flag ==> 특정한 옵션을 불러오면 on 안 불러오면 off

ls - ( - 씀으로써 옵션 활성화!)

ls -a ==> 숨긴파일 보여줘!

ls -l ==> 현재 폴더들의 디테일한 정보 보여줘!

ls -al ==> 둘다 동시에 쓸 수 있다!



새 디렉토리 만들기 (새 폴더 만들기와 비슷!) ==> mkdir dev (dev 라는 디렉토리를 만들어줘라!)


mkdir .test (앞에 . 은 숨김 파일!)


ls ==> 해주면 sample 하나만 보임! (숨기지 않은 파일들만 보인다는 의미!)

ls -

ls -a ==> 숨김파일인 .test 도 보여줌!




touch (파일 생성)


touch test.txt , touch sample.md , touch server.py , touch main.js (텍스트 기반의 파일)

xlsx 등은 특정한 어플리케이션을 기반으로 해주기 때문에 touch 명령어가 듣지 않는다!


디렉토리 , 폴더 ==> 디렉토리는 단계적 속성 , 폴더는 걍 폴더 (용도의 차이!). 거의 차이 없다!

파일 ==> 열거 , 이동 , 복사 , 삭제 , 이름 바꾸기.

clear ==> 과거 기록 삭제.


main.js 라는 파일을 sample 디렉토리에 넣어줘라! ==> mv (move)

==> mv main.js sample


mv ../test.txt (상위폴더의 test.txt을 현재 위치에 가져오겠다!)

(ls , cd .. , ls는 기록 확인 가능!)


새파일을 복제하다! ==> copy ===> cp server.py ./server-copy.py (복제가 됨!)


cp sample.md sample/ (sample.md 를 복사해줘! sample 에 넣어줘!)



상위 디렉토리에 있는 파일을 복사해줘서 여기에 옮기자!

==> cp ../server.py ./ (맨 뒤 슬래쉬 빼도 됨!) , cp ../serve.py ./blahblah (상위 폴더 이름 복사 이름 바꿔서 여기로!)



파일 삭제 rm (remove) ==> rm test.txt


(ls : 경로 파일 확인 , cd .. 상위 폴더 가기)



* ==> 모든 이라는 의미!


rm *.py ==> 모든 .py 파일을 지워라!

rm sample.* ==> sample을 지워라! 모든 확장자 파일을!



touch old.py (old.py 라는 이름의 파일을 만들어라!)

mv old.py new.py ( = mv ./new.py ./olp.py) ==> 이름 바꾸기!


rm -r sample/ ==> sample 디렉토리를 삭제해 주마!




vim practice.md (메모장 같은 녀석!) (들어가면 노멀모드!)

(텍스트 수정을 위해서 insert 모드로 들어가야됨! i로 쓰기!)

(To enter insert mode, press i on normal mode.)






## ==> 제목 텍스트

- i on normal mode : enter insert mode

- <ul><li></li></ul> ==> 순서가 없는 기록!


백 따옴표는 강조표시!


`` ==> 강조 표시 , ``` ==> 코드 블록!

esc ==> normal 모드로 가기! , i는 insert 모드로 들어가기!


normal 모드에서 ==> 쉬프트 콜론 ==> command 모드로 들어가기!


command 모드 ==> 메뉴바. (저장하기, 나가기, 등등)

나가기 - :q

:wq 저장하고 나가기 그러면 터미널로 다시 나오게 됨!



cat practice.md (한줄 한줄 읽기!) ==> 모드로 들어가지 않고 터미널(쉘) 에서 마크다운 기록물을 볼 수 있는!


Branch를 통해 여러가지 실험적인 용도로도 사용할 수 있다!

github를 안쓰면 취업이 안된다!


github는 소스코드의 히스토리를 관리하는 프로그램! (데이터 관리하는 툴은 아님!)


github를 통해 데이터 수집, 전처리, 가공 ==> 그 역사를 ㅗㅂㄹ 수 있음!








working directory ==> 태초마을

staging area ==> 앞접시 (탕수육을 먹을 앞접시) (변경사항) , 작업할 내용이 앞접시로 오는 것!


메타데이터를 작업하는 것! staging area ==> localrepo (변경사항 작업 , 메타 데이터 작업)


히스토리를 쭉 쌓아놨다가 한번에 보기! remote repo (github 같은 것들!)



staging area , localrepo는 가상개념이라고 생각하면 됨!


git은 버전 관리 시스템! github은 git을 바탕으로 웹 서비스를 하는 것!

(git 은 버전 관리 시스템이고 github는 그 시스템을 활용하는 공간!)









쓰는 법



git clone https://github.com/slksun/first-repo.git

touch fizzbuzz.py

ls

vi fizzbuzz.py


(빨간색에서 초록색으로 변하게 해야지!)


git status (빨 -> 초로 변했니? 상태 확인!)


git add fizzbuzz.py (빨 -> 초)


git commit (마크다운 들어가기) -> feat : Add feature that print 'buzz' , condition : i is times of 5. (예를 들면 이런것 적기!)

==> 기능개발!





git push origin main (가급적 자주 안하는게 좋음!)

(어느 정도 완성 됐을 대 하는게 좋음!)






git add 220816-commands.md (./ 로 뜨는 경우가 있는데 축약 된 것!)


작업을 하고 결과를 보고 맞으면 (빨간색인지 확인하기위해 git status)

git commit


초깃 커밋 만들면 클론!




git , github ==> cri 기반!

gui 기반? ==> 윈도우 탐색기 등

gitbash는 저장이 기반이 되는 프로그램이 아님!





유닉스

데니스 리치 , 켄 톰슨 - c 개발 , c 기반 , unix 재작성


unix - 쓰가다 특정인이 고칠 능력이 되는데 못 고치게 하니 불만 쌓임


--> 리차드 스톨먼이 오픈 소프트웨어 자유성 확보를 위한 GNU 프로젝트 돌입 (GNU는 유닉스가 아니다 프로젝트)


커널 (윈도우즈 md 커널?) : 하드웨어와 응용프로그램을 이어주는 운영체제의 핵심 시스템소프트웨어


리누스 토발즈가 커널인 리눅스 발표


안드로이드도 리눅스의 배포판의 일부!


쉘 : 운영체제의 커널과 사용자를 연결하는 소프트웨어



























