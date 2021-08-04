# Django web

## 프로젝트 계획

------------
> 블로그 post형식으로 web사이트 구현
> Django 문법과 bootstrap을 읽히기위해 블로그형식으로 사이트를 구현
 
#### 계획을 통해 구현할 목록
* Post형식인 사진과 글이있는 리스트목록 형식
* post 글쓰기, 수정, 삭제 
* post 댓글 
* 카테고리, 태그 삽입 기능
* 검색기능 
* 회원가입, 로그인, 로그아웃
* 내소개 및 우리집 강아지 소개
####
## 프로젝트 환경설정

-----------------------
* python, Pycharm 설치
    * pycharm에서 setting >project:프로젝트명>설정>Location에 프로젝트주소/venv(가상환경)>ok하고 터미널에서 가상환경venv실행된 곳에서 pip를 통해 다운받는다.
* pip install Django : python 프레임워크, MTV(Model-Template-View) 패턴을 사용하여  더 적은 코드로 더 신속하게 개발
* pip install Pillow :파이썬에 이미지 처리하기 위한 라이브러리
* pip install django-crispy forms : 게시판에서 폼이 한쪽으로 치우쳐져 있는 모양을 수정(폼이 가로화면 전체로 바뀜)
* pip install django-markdownx : 마크다운 설치, 공지사항에서 마크다운 적용
* pip install django-allauth : 구글, 카카오톡, 페이스북 등 로그인하는 기능을 손쉽게 할 수 있도록 구현
* pip install beautifulsoup4 : HTML로 나타나는 페이지의 요소를 쉽게 다룰 수 있는 도구(타이틀, 버튼 등에 써있는 내용은 무엇인지)
웹 스크레이핑 라이브러리, HTML과 XML 파일로부터 데이터를 추출하는 데 사용된다. 테스트를 하기위해 사용
* pip install requests : HTTP 프로토콜을 이용하여 웹에서 리소스를 가져오거나, HTTP 패킷을 직접 만들어서 전송할 수 있다.
* pip install urllib3 : URL 작업을 위한 여러 모듈을 모은 패키지
####
## 구현한 기능 설명

-----------------------
1. HOME
    * bootstrap을 이용하여 반응형 블로그웹사이트
    * HOME과 로고를 누르면 HOME 화면으로 이동.
    * HOME에는 카드형식으로 3개의 최신글이 보이고 카드를 클릭시 해당 post로 이동.
    ####
![home](https://user-images.githubusercontent.com/86580625/128176304-c532ab0a-2c28-48fc-9ae3-3fe478140a20.jpg)


###
2. Blog
    * blog 앱에서 구현
    * 리스트마다 사진, 제목, 소제목, 내용 45자, 해당 카테고리, 태그가 한 목록으로 리스트로 구현.
    * serch를 검색이 가능하다. 2글자 미만으로 쓴 경우 경고창이 나온다.
    * 카테고리는 글쓰기나 수정할때 입력하면 카테고리로 분류가 되고 카테고리를 입력하지 않을시에는 미분류로 분류가 된다.
    * 태그는 글쓰기나 수정할때 입력할 수 있고 태그를 누르면 해당 태그들만 리스트로 볼 수 있다.
    * 페이징은 맨끝에 더이상 post가 없는경우 비활성화로 표시가 된다.
    * 로그인이 했을경우에만 글쓰기가 나타난다.
    * 사진 업로드를 안한 경우 https://picsum.photos/을 통해 사진을 임의적으로 가져와 저장.      
    * p.id는 DB에 index를 넣어 고정시켜 저장한다. seed/id로 고정하지 않으면 임의적으로 계속 랜덤으로 사진이 바뀐다.
    * 이미지 태그안에 img class="card-img-top" src="https://picsum.photos/seed/{{ p.id }}/800/200" alt="random_image"

####
![blog](https://user-images.githubusercontent.com/86580625/128176349-aecedca7-9bb7-46b6-bfa7-4439f0ac38a4.jpg)

###
2. Post
    * blog앱에서 구현
    * 해당글을 쓴 아이디로 로그인한 경우 삭제, 수정 버튼이 나타난다.
    * 댓글도 로그인해야만 글쓰기가 가능.
    * 댓글을 해당글을 쓴사람만 수정하고 삭제할 수 있다.
    * 파일을 업로드한 경우 하단에 파일 다운로드가 표시.
    * 사진 업로드한 경우 업로드한 이미지가 나오지만 없는경우 임의의 사진이 등록된다.
####
![post](https://user-images.githubusercontent.com/86580625/128176439-cc90b51e-8fc6-41df-8086-488dcb646a89.jpg)

###
3. About Me
    * one_pages에 구현.
    * 자기 소개 페이지와 강아지소개 페이지.
    * 카드형식으로 각각 강아지들 사진 소개로 카드를 누르면 더 자세한 설명이 나온다.
####
![about](https://user-images.githubusercontent.com/86580625/128176503-3d67f710-462c-43e7-bf66-6292534890f7.jpg)
## 외부 리소스, 출처 및 참고문헌
_______________________________
1. bootstrap
2. fontawesome : icon 이미지
3. https://picsum.photos/ : 임의의 사진 제공
4. http://hangul.thefron.me/ : 장문의 글을 생성
5. google API
6. 장고+부트스트랩 파이썬 웹개발의 정석   

    


    
