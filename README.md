# 웹사이트 배포 작업

## 일자

### 12월 17일
* wikidocs에서 점프투장고를 참조해 Lightsail을 이용한 배포계획 수립
![](/img/1217.png)
  
### 12월 18일
* 점프투장고를 읽으며 조원과 회의

### 12월 19일
* 점프투장고를 참조해 첫 사이클을 하였으나, 실패로 끝남.

### 12월 20일
* 같은 조원과 화상회의를 통해 갈피를 잡기 시작

### 12월 21일
* 많은 시행착오와 고민을 통해 본격적 웹사이트 배포 작업 시행

### 12월 22일
* 웹사이트 배포 완료 (모든 기능은 추가하지는 않음.)
### 점프 투 장고에선 pybo 로 실습을 진행했지만 전 차이를 두기 위해 HelloWorld 라는 이름으로 실습했습니다!
### 12월 23일 (업로드 시작) 1장. 장고 개발 준비
- 파이썬 설치하기
- 장고 개발환경 준비하기
- 장고 프로젝트 생성하기
- 파이참 설치하고 장고 개발 서버 실행하기
### 12월 24일 2장. 장고의 기본 요소 익히기
- 주소와 화면을 연결하는 URL과 뷰
- 데이터를 관리하는 모델
- 개발 편의를 제공하는 장고 Admin
- 질문 목록과 질문 상세 기능 구현하기
- URL 더 똑똑하게 사용하기
- 답변 등록 기능 만들기
- 스태틱화면 예쁘게 꾸미기
- 부트스트랩으로 더 쉽게 화면 꾸미기
- 표준 HTML과 템플릿 상속 사용해 보기
- 질문 등록 기능 만들기
### 12월 25일 3장. 파이보 서비스 개발!
- 내비게이션 기능 추가하기
- 게시판 페이징 기능 추가하기
- 템플릿 필터 직접 만들어 보기
- 질문에 달린 답변 개수 표시하기
- 로그인 로그아웃 구현하기
- 회원가입 구현하기
- 모델에 글쓴이 추가하기
- 글쓴이 표시하기
- 게시물 수정 & 삭제 기능 추가하기
- 댓글 기능 추가하기
### 12월 26일 4장. 세상에 선보이는 파이보 서비스!
- 깃으로 버전 관리하기
- 깃허브 사용해 보기
- 파이보를 위한 서버 운영 방법 알아보기
- AWS 라이트세일 공개하기
- 세상에 파이보 공개하기




### 스샷첨부

* 디렉터리 생성
![](/img/1221_1.png)
  
* 프로젝트 생성
![](/img/1221_2.png)

* 파이참 작업
![](/img/1221_3.png)
  
* Settings.py 수정 
![](/img/1221_4.png)
  
### 추가된 소스코드 
## 12월 23일 장고 개발 준비
## 파이썬 설치하기
- 파이썬 공식 홈페이지 주소 : www.python.org
```python
선택하셔야할 부분 install Now ,하단에 Add python.38 to path, install launcher for all users
```
## 파이썬 설치 확인하기
- 명령 프롬프트(CMD)
```python
C:\Users\park> python -V
python 3.8.5
```python
만약 명령어를 제대로 입력했는데도 파이썬 버전이 나타나지 않고 ‘찾을 수 없는 명령’이라는 오류 메시지가 출력된다면 
앞의 설치 과정에서 경로 설정에 문제가 있을 가능성이 크다. 이때는 1단계에서 내려받은 설치 파일을 다시 실행해 <Uninstall>을 눌러 삭제한 후 2단계부터 다시 설치하자.
```
## 장고 개발환경 준비하기
윈도우에서 명령 프롬프트를 실행하고 다음 명령어를 입력해 C:/venvs라는 디렉터리를 만들자.
- 명령 프롬프트
```python
C:\Users\park> cd \
C:\> mkdir venvs
C:\> cd venvs
```
## 가상 환경 만들기
파이썬 가상 환경을 만드는 다음 명령어를 입력해 실행하자.
- 명령 프롬프트
```python
C:\venvs> python -m venv mysite
```
명령에서 python -m venv는 파이썬 모듈 중 venv라는 모듈을 사용한다는 의미다.
## 가상 환경에 진입하기
가상 환경에 진입하려면 우리가 생성한 mysite 가상 환경에 있는 Scripts 디렉터리의 activate 명령을 수행해야 한다.
- 명령 프롬프트
```python
C:\venvs>cd C:\venvs\mysite\Scripts
C:\venvs\mysite\Scripts> activate
(mysite) C:\venvs\mysite\Scripts>
```
그러면 C:/ 왼쪽에 (mysite)라는 프롬프트를 확인할 수 있다. 이름에서 볼 수 있듯 현재 여러분이 진입한 가상 환경을 의미한다.
## 가상 환경애서 벗어나기
현재 진입한 가상 환경에서 벗어나려면 deactivate 라는 명령을 실행하면 된다. 이 명령은 어느 위치에서 실행해도 상관없다.
- 명령 프롬프트
```python
(mysite) C:\venvs\mysite\Scripts> deactivate
```
가상 환경에서 벗어났다면 C:/ 왼쪽에 있던 (mysite)라는 프롬프트가 사라졌을 것이다
## 가상 환경인지 확인하기
명령 프롬프트 왼쪽에 (mysite) 프롬프트가 보이는지 확인하자.
```python
C:\venvs\mysite\Scripts> activate
(mysite) C:\venvs\mysite\Scripts>
```
## 가상 환경에서 장고 설치하기
```python
mysite 가상 환경에 진입한 상태에서 pip install django==3.1.3 명령을 입력하자.
pip은 파이썬 라이브러리를 설치하고 관리해 주는 파이썬 도구이다. pip install django==3.1.3는 pip으로 장고 3.1.3 버전을 설치하는 명령이라고 생각하면 된다.
```
- 명령 프롬프트
```python
(mysite) C:\venvs\mysite\Scripts> pip install django==3.1.3
(생략)
WARNING: You are using pip version 19.2.3, however version 20.2.3 is available.
You should consider upgrading via the 'python -m pip install --upgrade pip' command.
```
그런데 마지막에 경고(WARNING) 문구가 보인다. pip이 최신 버전이 아니라는 내용이다.
## pip 최신 버전으로 설치하기
- 명령 프롬프트
```python
(mysite) C:\venvs\mysite\Scripts> python -m pip install --upgrade pip
(생략)
Successfully installed pip-20.0.2
```
## 장고 프로젝트 생성하기
장고에는 프로젝트라는 개념이 있는데, 장고의 프로젝트는 하나의 웹 사이트라고 생각하면 된다.
## 프로젝트 디렉터리 루트 디렉터리 생성하기
장고 프로젝트는 여러 개가 될 수 있으므로 프로젝트를 모아 둘 프로젝트 루트 디렉터리 셍성은 필수다.
- 명령 프롬프트
```python
C:\projects>C:\venvs\mysite\Scripts\activate
(mysite) C:\projects>
```
## 장고 프로젝트를 담을 디렉터리 생성하고 이동하기
장고 프로젝트를 담을 mysite 디렉터리를 생성하고 이동하자.
- 명령 프롬프트
```python
(mysite) C:\projects>mkdir mysite
(mysite) C:\projects>cd mysite
(mysite) C:\projects\mysite>
```
## 장고 프로젝트 생성하기
```python
mysite 디렉터리에서 django-admin이라는 도구로 장고 프로젝트를 생성하자. 
이때 config 다음에 점 기호(.)가 있음에 주의하자. 점 기호는 ‘현재 디렉터리를 프로젝트 디렉터리로 만들라’는 의미이다.
```
- 명령 프롬프트
```python
(mysite) C:\projects\mysite>django-admin startproject config .
```
## 장고 프로젝트 내용물 확인하기
위 단계들이 완료되면 다음과 같은 구조로 디렉터리가 구성되어 있는지, 파일이 잘 생성되어 있는지 확인해 보자.
- 디렉터리 구조와 파일
```python
C:\projects\mysite
├── config/
│      ├─ asgi.py
│      ├─ settings.py
│      ├─ urls.py
│      ├─ wsgi.py
│      └─ __init__.py
└── manage.py
```
## 개발 서버 구동하고 웹 사이트에 접속해 보기
개발 서버를 구동하고 웹 사이트에 접속해 보자.
## 개발 서버 구동하기
```python
python manage.py runserver 명령을 실행하면 개발 서버가 구동된다.
맨 아랫줄에는 ‘Quit the server with CTRL-BREAK’이라는 개발 서버 종료 방법도 안내되어 있다.
개발 서버를 종료하려면 <Ctrl+C>를 누르란 뜻이다.
```
- 명령 프롬프트
```python
(mysite) C:\projects\mysite>python manage.py runserver
(생략)
Quit the server with CTRL-BREAK.
```
개발 서버가 구동된 상태를 유지하고 웹 브라우저를 이용하여 127.0.0.1:8000에 접속해 보자. 
```python
- 개발 서버는 127.0.0.0, 즉 로컬호스트localhost로 실행되므로 로컬 서버라 부르기도 한다. 필자는 개발을 위해 실행된 개발 서버를 ‘개발 서버’라 부르겠다.
- 127.0.0.1:8000 대신 localhost:8000이라고 입력해도 같은 화면을 볼 수 있다. 127.0.0.1과 localhost는 현재 컴퓨터를 가리키는 아이피 주소다.
```
아직은 개발 서버 환경에서 사이트가 실행되고 있으므로 본인 컴퓨터에서만 서버가 열린다.
## 개발 서버 종료하기
<Ctrl+C> 를 눌러 개발 서버를 종료해 보자. 
```python
로컬 아이피 주소로 다른 사람이 접속할 수 없는 이유

앞에서 ‘아직은 여러분이 만든 사이트에 다른 사람이 접속할 수 없다’고 이야기했다. 왜 그럴까? 다른 사람이 여러분이 만든 사이트에 접속하려면 localhost나 127.0.0.1이라는 로컬 아이피 주소가 아닌 15.165.210.240과 같은 인터넷 세상 속의 아이피 주소 또는 pybo.kr과 같은 도메인이 필요하기 때문이다. 로컬 아이피 주소의 ‘로컬’은 지역이라는 뜻이며,
이는 곧 ‘내 PC’를 의미한다. 내 PC의 아이피 주소이므로 친구가 접속할 수 없다.
4장에서 인터넷 세상 속의 아이피 주소로 여러분이 만든 사이트에 접속하는 방법을 소개하므로 우선은 파이보 기능을 완성하는 데 집중하자.
```
## mysite 가상 환경에 간단히 진입하기
```python
mysite 가상 환경에 진입하려면 매번 명령 프롬프트를 실행하고 C:/venvs/mysite/Scripts 디렉터리로 이동하여 activate 명령을 수행해야 한다.
이런 일련의 과정을 한 번에 수행할 수 있는 배치 프로그램을 만들어 귀찮음을 덜어 보자.
```
## mysite.cmd 배치 파일 생성하기
```python
mysite.cmd 파일을 venvs 디렉터리에 만들고 다음과 같이 작성하여 저장하자.
확장자 .cmd가 붙은 파일은 배치(batch) 파일이라 부르며, 명령어 입력과 실행을 한 번에 해주는 파일이라 생각하면 된다.
```
- 파일 이름 [파일 이름: C:/venvs/mysite.cmd]
- mysite.cmd 안에 넣어야 할 소스 코드
```python
@echo off
cd c:/projects/mysite
c:/venvs/mysite/scripts/activate
```
배치 파일의 내용은 C:/projects/mysite 디렉터리로 이동한 다음, C:/venvs/mysite/scripts/activate 명령을 수행하라는 뜻이다.
## 배피 파일 위치를 PATH 환경 변수에 추가하기
```python
1. 윈도우 + R 키를 눌러서 실행화면 띄우기
2. sysdm.cpl 명령을 입력한 다음 <확인> 클릭
3. ‘시스템 속성’ 창이 나타난다. 여기서 <고급> 탭을 선택하고 <환경 변수> 클릭
4. ‘환경 변수’ 창이 나타난다. 여기서 사용자 변수 중 <Path>를 선택하고 <편집> 버튼 클릭
5. <새로 만들기> 버튼 클릭
6. C:/venvs(저는 c:/Users/parrk/Venvs)라는 디렉터리를 추가하고 <확인> 버튼
7.마지막으로 다음 ‘환경 변수’ 창에서 <확인> 버튼
```
## PATH 환경 변수 확인하기
```python
이렇게 하면 환경 변수 PATH에 C:/venvs 디렉터리가 추가되어 mysite.cmd 명령을 어디서든 실행할 수 있다.
명령 프롬프트를 다시 시작하자(그래야 변경된 환경 변수 PATH가 제대로 반영된다).
그리고 set path 명령을 실행하여 변경된 환경 변수 PATH의 내용을 확인해 보자. 
C:/venvs라는 디렉터리가 환경 변수 PATH에 포함되어 있으면 된다.
```
- 명령 프롬프트(CMD)
```python
C:\Users\park>set path
Path=C:\Windows\system32; (... 생략 ...) ;C:\venvs
PATHEXT=.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC
```
## 배치 파일 실행하여 가상 환경에 진입하기
```python
이제 지금까지 만든 mysite 명령(배치 파일 이름)을 실행하여 가상 환경에 잘 진입하는지 확인해 보자.
참고로 윈도우에서 확장자가 .cmd인 파일은 확장자를 빼고 입력해도 된다.
```
- 명령 프롬프트
```python
C:\Users\parky> mysite
(mysite) C:\projects\mysite>
```
## 파이참 설치하고 장고 개발 서버 실행하기
보통 파이썬과 장고 개발에 많이 사용되는 에디터는 비주얼 스튜디오 코드와 파이참이다.
이 책에서는 파이참으로 장고 개발을 진행한다.
## 파이참 설치하기
윈도우용 파이참 설치 파일 주소: www.jetbrains.com/ko-kr/pycharm/download/#section=windows
```python
<Professional>과 <Community> 중 무료 버전인 <Community>를 선택하자. 파이참 설치 파일을 내려받은 후 설치를 진행하자.
설치할 때 특별히 주의할 점은 없으므로 끝까지 <Next>를 선택하여 설치하면 된다.
```
## 파이참 실행하기
```python
[윈도우 키]를 누르고 프로그램 목록에서 [JetBrains → PyCharm Community Edition]을 선택하면 파이참이 실행된다.
파이참을 처음 실행하는 독자라면 다음과 같은 설정 창이 나타날 것이다. 
테마, 플러그인 등의 옵션은 기본값으로 선택하고 넘어가자.
이어서 다음과 같은 창이 나오면 두 번째 메뉴인 <Open>을 선택하여 앞에서 우리가 생성한 장고 프로젝트인 C:/projects/mysite를 선택하자.
처음 프로젝트를 만들면 mysite 디렉터리 안에 main.py 파일이 자동으로 생성될 수 있다. 파일이 있다면 삭제 후 실습을 진행하자.
```
## 파이참 인터프리터 설정하고 개발 서버 한글로 실행하기
파이참으로 장고 프로젝트를 불러온 후 가장 먼저 해야 할 일은 장고 프로젝트가 바라봐야 할 파이썬 인터프리터 위치를 설정하는 것이다.
## 현재 파이썬 인터프리터 위치 확인하기
```python
파이참 메뉴에서 [File → Settings]를 눌러 설정 창을 열고 [Project: mysite → Project Interpreter]를 순서대로 눌러 파이썬 인터프리터 위치를 설정할 수 있는 창을 열자.
그런 다음 오른쪽 위에 보이는 Python Interpreter를 보자.
아마도 파이썬을 설치한 디렉터리로 설정되어 있을 것이다.
```
## 파이썬 인터프리터 위치를 가상 환경 위치로 수정하기
하지만 지금은 가상 환경을 사용하므로 파이썬 인터프리터 위치를 가상 환경 위치로 수정해야 한다.
```python 
1. Python Interpreter 오른쪽에 보이는 톱니바퀴 모양 아이콘을 누른 다음 <Add>를 누르자.
2. 파이썬 인터프리터 위치를 설정할 수 있는 ‘Add Python Interpreter’ 창이 나타난다.
3. <Existing environment>를 누른 다음 Interpreter 오른쪽에 보이는 <...>을 누르자.
4. C:/venvs/mysite/Scripts/python.exe를 선택한 후 <OK>를 누른다.
5. 나머지 창도 를 눌러 설정을 마치면 파이참이 mysite 가상 환경에 있는 파이썬 인터프리터를 인식하기 시작한다.
```
## 파이참에서 settings.py 파일 수정하기
```python
이제 파이참으로 장고를 개발할 준비가 완료되었다. 장고 개발을 맛보는 차원에서 장고의 설정값이 들어 있는 settings.py 파일을 수정해 보자.
파이참에서 settings.py 파일을 열어 LANGUAGE_CODE와 TIME_ZONE 설정값을 수정하자.
LANGUAGE_CODE를 en-us에서 ko-kr로 수정하고 TIME_ZONE을 UTC에서 Asia/Seoul로 수정했다.
언어와 시간을 한국 값으로 바꾼 것이다.
```
- [파일이름: C:/projects/mysite/config/settings.py]
```python
(... 생략 ...)
# ---------------------------------- [edit] ---------------------------------- #
LANGUAGE_CODE = 'ko-kr'

TIME_ZONE = 'Asia/Seoul'
# ---------------------------------------------------------------------------- #
(... 생략 ...)
```
## 개발 서버 다시 구동하기
앞의 실습을 잘 진행했다면 개발 서버가 종료된 상태이다.
개발 서버를 다시 구동하자. localhost:8000으로 접속하면 초기 화면이 영어에서 한글로 바뀌어 있다.
- 코드 : python manage.py runserver

## 12월 24일 장고의 기본 요소 익히기
## 주소와 화면을 연결하는 URL과 뷰 
이제부터 파이보를 만들면서 장고의 기능을 살펴볼 것이다.
가장 먼저 요청 URL을 어떻게 처 리하고 또 어떻게 파이썬 프로그램을 호출하는지 알아보자.
## 앱 생성하고 확인하기
```python
1장에서 mysite 프로젝트를 생성했다. 프로젝트에는 장고가 제공하는 기본 앱과 개발자(여러분)가 직접 만든 앱이 포함될 수 있으며,
장고에서 말하는 ‘앱’은 안드로이드 앱과 성격이 다르다고 언급했다.
그러면 장고의 앱이란 정말로 무엇일까? 우리의 파이보 서비스에 필요한 pybo(저는 HelloWorld로 만들었습니다.) 앱을 만들어 보며 알아보자.
```
## pybo 앱 생성하기
명령 프롬프트에서 django-admin의 startapp 명령을 이용하여 pybo 앱을 생성
- 명령 프롬프트
```python
(mysite) C:\projects\mysite>django-admin startapp pybo
(mysite) C:\projects\mysite>
```
## 생성된 앱 확인하기
```python
1단계를 진행하면 아무런 메시지가 나타나지 않을 것이다.
하지만 파이참에서 다음의 프로젝트 디렉터리 목록을 살펴보면 pybo라는 이름의 디렉터리가 생성되었음을 확인할 수 있다.
```
## 안녕하세요 파이보?
```python
지금부터 실습을 시작해 보자. 실습을 진행하면 파이보 서비스가 조금씩 완성될 것이다. 여기서 필자가 여러분에게 한 가지 부탁하고 싶은 것이 있다.
결과를 보기 위해 실습을 무작정 따라 하지 않길 바란다. 결과를 보고 싶은 조급한 마음은 이해하지만,
결과가 나온 이유를 명확하게 이해하면서 따라 해야 좋은 개발자가 될 수 있다.
```
## 개발 서버 구동하기
개발 서버를 구동하자.
- 명령 프롬프트
```python
(mysite) C:\projects\mysite> python manage.py runserver
```
## localhost:8000/pybo에 접속하기
```python
웹 브라우저 주소창에 다음을 입력하여 접속해 보자.
앞으로 이 과정을 ‘페이지를 요청한다’ 또는 localhost:8000을 생략하여 ‘/pybo/를 요청한다’라고 할 것이다.
```
## 오류 메시지 확인하기
그러면 ‘Page not found (404)’ 오류 페이지가 보인다.
## config/urls.py 수정하기
장고가 사용자의 페이지 요청을 이해할 수 있도록 config/urls.py 파일을 수정하자.
- [파일이름: C:\projects\mysite\config\urls.py]
```python
from django.contrib import admin
from django.urls import path
# ---------------------------------- [edit] ---------------------------------- #
from pybo import views
# ---------------------------------------------------------------------------- #

urlpatterns = [
    path('admin/', admin.site.urls),
# ---------------------------------- [edit] ---------------------------------- #    
    path('pybo/', views.index),
# ---------------------------------------------------------------------------- #    
]
```
코드의 urlpatterns 변수를 보면 path 함수를 사용하여 pybo/ URL과 views.index를 매핑했다.
views.index는 views.py 파일의 index 함수를 의미한다. 장고는 이런 식으로 URL과 뷰 함수를 매핑했다.
## config/urls.py 다시 살펴보기
```python
그런데 여러분이 urlpatterns에 입력한 URL은 웹 브라우저에 입력한 localhost:8000/pybo에서 호스트명 localhost와 포트 번호 :8000이 생략된 pybo/이다.
호스트명과 포트는 장고가 실행되는 환경에 따라 변하는 값이며 장고가 이미 알고 있는 값이다.
그러므로 urlpatterns에는 호스트명과 포트를 입력하지 않는다.
```
- [urls.py 파일의 urlpatterns]
```python
urlpatterns = [
    path('admin/', admin.site.urls),
    path('pybo/', views.index),
]
```
```python
그리고 pybo에 슬래시 /를 붙여 입력한 점에도 주목하자! 슬래시를 붙이면 사용자가 슬래시 없이 주소를 입력해도 장고가 자동으로 슬래시를 붙여 준다.
이는 URL을 정규화하는 장고의 기능 덕분이다.
특별한 경우가 아니라면 URL 매핑에는 호스트명과 포트를 생략하고 끝에는 슬래시를 붙이자.
```
- 웹 브라우저 주소창에 localhost:8000/pybo라고 입력하면 장고가 자동으로 localhost:8000/pybo/와 같이 슬래시를 붙여 준다.
```python
프로젝트 디렉터리는 BASE_DIR 변수에 저장되어 있다.

여러분의 파이보 프로젝트 디렉터리는 C:/projects/mysite일 것이다. 장고는 이 경로를 settings.py 파일의 BASE_DIR 변수에 저장한다.
이 책에서는 파일 경로를 언급할 때 BASE_DIR을 생략한다.
예를 들어 config/urls.py라 언급하면 BASE_DIR의 값인 C:/projects/mysite가 생략된 것이므로
실제 언급하는 파일 위치는 C:/projects/mysite/config/urls.py이다.
```
## 오류 메시지 확인하기
```python
다시 localhost:8000/pybo/ 에 접속해 보자.
그러면 웹 브라우저에 ‘사이트에 연결할 수 없음’ 오류가 표시되고, 개발 서버에는 다음과 같은 오류가 표시된다.
```
- 명령 프롬프트
```python
(... 생략 ...)
  File "c:\projects\mysite\config\urls.py", line 23, in <module>
    path('pybo/', views.index),
AttributeError: module 'pybo.views' has no attribute 'index'
```
config/urls.py 파일을 수정했음에도 이런 오류가 발생한 이유는 URL 매핑에 추가한 뷰 함수인 views.index가 없기 때문이다.
## pybo/views.py 작성하기
pybo/views.py 파일에 index 함수를 추가하자.
- [파일이름: c:\projects\mysite\pybo\views.py]
```python
# ---------------------------------- [edit] ---------------------------------- #
from django.http import HttpResponse


def index(request):
    return HttpResponse("안녕하세요 pybo에 오신것을 환영합니다.")
# ---------------------------------------------------------------------------- #
```
## 첫 번째 장고 프로그램 완성!
이제 /pybo/ 페이지에 접속하면 웹 브라우저에 “안녕하세요 pybo에 오신것을 환영합니다.”라는 문자열이 출력된다
## 장고 개발 흐름 정리하기
```python
1. 웹 브라우저 주소창에 localhost:8000/pybo 입력(장고 개발 서버에 /pybo 페이지 요청).
2. config/urls.py 파일에서 URL을 해석해 pybo/views.py 파일의 index 함수 호출.
3. pybo/views.py 파일의 index 함수를 실행하고 그 결과를 웹 브라우저에 전달.
```
## URL 분리하기
## config/urls.py 다시 살펴보기
```python
config/urls.py 파일을 다시 한번 살펴보자. 아까 얘기했듯이 pybo 앱 관련 파일은 대부분 pybo 디렉터리에 있다.
하지만 매핑을 위한 urls.py 파일은 pybo 디렉터리에 없다. 
그러므로 pybo 앱에 URL 매핑을 추가하려면 pybo 디렉터리가 아닌 config 디렉터리에 있는 urls.py 파일을 수정해야 한다.
```
- [파일이름: C:/projects/mysite/config/urls.py]
```python
from django.contrib import admin
from django.urls import path
from pybo import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('pybo/', views.index),
]
```
이 방식은 프로젝트의 짜임새를 전혀 고려하지 않은 것이다. pybo 앱 관련 urls.py 파일을 따로 구성할 방법은 없을까? 물론 있다.
## config/urls.py 수정하기
include 함수를 임포트해 pybo/의 URL 매핑을 path('pybo/', views.index)에서 path('pybo/', include('pybo.urls'))로 수정하자.
- [파일이름: c:\projects\mysite\config\urls.py]
```python
from django.contrib import admin
# ---------------------------------- [edit] ---------------------------------- #
from django.urls import path, include
# ---------------------------------------------------------------------------- #

urlpatterns = [
    path('admin/', admin.site.urls),
# ---------------------------------- [edit] ---------------------------------- #
    path('pybo/', include('pybo.urls')),
# ---------------------------------------------------------------------------- #    
]
```
## pybo/urls.py 생성하기(파일명에는 반드시 확장자 .py가 포함되어야 한다.)
pybo 앱 디렉터리에 urls.py 파일을 생성하자. [pybo → 마우스 오른쪽 클릭 → New → File]을 한 다음 파일명으로 urls.py를 입력
## pybo/urls.py 수정하기
pybo/urls.py 파일을 다음과 같이 수정하자.
- [파일이름: C:\projects\mysite\pybo\urls.py]
```python
# ---------------------------------- [edit] ---------------------------------- #
from django.urls import path

from . import views

urlpatterns = [
    path('', views.index),
]
# ---------------------------------------------------------------------------- #
```
다시 /pybo/에 접속해 보자.
## 데이터를 관리하는 모델 
```python
장고는 모델로 데이터를 관리한다. 모델로 데이터를 관리한다는 것은 무엇이며 어떤 이점이 있을까? 보통 웹 개발에서는 데이터의 저장 · 조회를 위해 SQL 쿼리문을 이용한다.
이 말은 데이터 저장 · 조회를 위해서는 별도의 SQL 쿼리문을 배워야 한다는 말과 같다.
학습 장벽이 하나 더 생기는 셈이다. 
하지만 놀랍게도 모델을 사용하면 SQL 쿼리문을 몰라도 데이터를 저장 · 조회할 수 있다.
모델이 무엇이길래 이렇게 파격적으로 이야기하는지 실습을 통해 알아보자.
```
## migrate와 테이블 알아보기
## 장고 개발 서버 구동 시 나오는 경고 메시지 살펴보기
모델을 알아보기 위해 python manage.py runserver 명령 실행 시 나오는 경고 메시지를 조금 더 자세히 살펴보자.
- 명령 프롬프트
```python
(mysite) c:\projects\mysite>python manage.py runserver
Watching for file changes with StatReloader
Performing system checks...
(생략)
Quit the server with CTRL-BREAK.
```
## config/settings.py 열어 기본으로 설치된 앱 확인하기
```python
그러면 경고 메시지에 표시된 앱은 어디서 확인할 수 있고, 왜 경고 메시지에 언급되었을까? 
그 이유는 config/settings.py 파일을 열어 보면 어느 정도 짐작할 수 있다. 
파일을 열어 INSTALLED_APPS 항목을 찾아보자.
```
- [파일이름: C:/projects/mysite/config/settings.py]
```python
(... 생략 ...)
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
(... 생략 ...)
```
## config/settings.py 에서 데이터베이스 정보 살펴보기
```python
살펴보는 김에 config/settings.py 파일을 조금 더 살펴보자. config/settings.py 파일에는 설치된 앱뿐만 아니라 사용하는 데이터베이스에 대한 정보도 정의되어 있다.
DATABASES 설정 중 default의 'ENGINE' 항목을 보면 데이터베이스 엔진이 django.db.backends.sqlite3로 정의되어 있음을 알 수 있다.
그리고 'NAME' 항목을 보면 데이터베이스는 BASE_DIR에 있는 db.sqlite3이라는 파일에 저장되는 것도 알 수 있다.
```
- BASE_DIR은 프로젝트 디렉터리를 의미하며, 현재 우리의 BASE_DIR은 C:/projects/mysite이다.
- 데이터베이스를 여러 개 사용할 때 default에 지정한 데이터베이스 외에 추가로 등록해 사용할 수 있다.
- [파일이름: C:/projects/mysite/config/settings.py]
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
```
- SQLite는 파일 기반의 아주 작은 데이터베이스이다
```python
SQLite는 주로 소규모 프로젝트에서 사용되는 파일 기반의 가벼운 데이터베이스이다.
보통 초기 개발 단계에서 SQLite를 사용하여 빠르게 개발하고, 
서비스로 제공할 때 운영 환경에 어울리는 데이터베이스로 바꾼다.
```
## migrate 명령으로 앱이 필요로 하는 테이블 생성하기
```python
migrate 명령을 실행하여 경고 메시지에 있던 앱들이 필요로 하는 테이블들을 생성하자.
명령 프롬프트에서 python manage.py migrate를 입력하면 다음과 같은 메시지가 출력된다.
```
- [명령 프롬프트]
```python
(mysite) C:\projects\mysite>python manage.py migrate

Operations to perform:
  Apply all migrations: admin, auth, contenttypes, sessions
Running migrations:
  Applying contenttypes.0001_initial... OK
  Applying auth.0001_initial... OK
(생략)
```
## pybo/models.py에 질문 모델 작성하기
```python
질문 모델을 pybo/models.py에 작성해 보자. 질문 모델은 Question 클래스로 만든다. 
앞으로 대부분의 모델은 클래스로 만들 것이며,
이후 책에서는 클래스명으로 모델을 언급하겠다. 
이를테면 질문 모델은 Question 모델이라 하겠다.
```
- [파일이름: C:/projects/mysite/pybo/models.py]
```python
from django.db import models

# ---------------------------------- [edit] ---------------------------------- #
class Question(models.Model):
    subject = models.CharField(max_length=200)
    content = models.TextField()
    create_date = models.DateTimeField()
# ---------------------------------------------------------------------------- #
```
## pybo/models.py에 답변 모델 작성하기
이어서 같은 파일에 Answer 모델도 작성하자.
- [파일이름: C:/projects/mysite/pybo/models.py]
```python
from django.db import models


class Question(models.Model):
    subject = models.CharField(max_length=200)
    content = models.TextField()
    create_date = models.DateTimeField()

# ---------------------------------- [edit] ---------------------------------- #
class Answer(models.Model):
    question = models.ForeignKey(Question, on_delete=models.CASCADE)
    content = models.TextField()
    create_date = models.DateTimeField()
# ---------------------------------------------------------------------------- #
```
## config/settings.py를 열어 pybo 앱 등록하기
- [파일이름: C:/projects/mysite/config/settings.py]
```python
(... 생략 ...)
INSTALLED_APPS = [
# ---------------------------------- [edit] ---------------------------------- #
    'pybo.apps.PyboConfig',
# ---------------------------------------------------------------------------- #
    'django.contrib.admin',
    'django.contrib.auth',
    (... 생략 ...)
]
(... 생략 ...)
```
INSTALLED_APPS에 추가한 pybo.apps.PyboConfig 클래스는 pybo/apps.py 파일에 있는 클래스이다
## pybo/apps.py 열어 살펴보기
pybo/apps.py 파일을 열어 보자. 이 파일은 pybo 앱을 만들 때 자동으로 생성된 것이다. 
- [파일이름: C:/projects/mysite/pybo/apps.py]
```python
from django.apps import AppConfig

class PyboConfig(AppConfig):
    name = 'pybo'
```
## migrate로 테이블 생성하기
테이블을 생성을 위해 migrate 명령을 실행하자.
- [명령 프롬프트]
```python
(mysite) C:\projects\mysite>python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, sessions
Running migrations:
  No migrations to apply.
  Your models have changes that are not yet reflected in a migration, and so won't be applied.
  Run 'manage.py makemigrations' to make new migrations, and then re-run 'manage.py migrate' to apply them.
```
## makemigrations로 테이블 작업 파일 생성하기
```python
그런데 migrate 명령이 제대로 수행되지 않는다! 왜냐하면 모델이 생성되거나 변경된 경우 migrate 명령을 실행하려면 테이블 작업 파일이 필요하고,
테이블 작업 파일을 만들려면 makemigrations 명령을 실행해야 하기 때문이다.
makemigrations 명령을 먼저 실행하자.
```
- [명령 프롬프트]
```python
(mysite) c:\projects\mysite>python manage.py makemigrations
Migrations for 'pybo':
  pybo\migrations\0001_initial.py
    - Create model Question
    - Create model Answer
```
makemigrations 명령은 장고가 테이블 작업을 수행하기 위한 파일들을 생성한다.
## makemigrations로 생성된 파일 위치 살펴보기
makemigrations 명령을 수행하면 pybo/migrations/0001_initial.py이라는 파일이 자동으로 생성된다. 파일 위치를 확인해 보자.
## makemigrations 한 번 더 실행해 보기
```python
makemigrations 명령을 한 번 더 실행해도 'No changes detected'라는 메시지만 뜬다.
모델의 변경사항이 없다면 '모델 변경 사항 없음'이라고 알려 주는 것이다.
```
- [명령 프롬프트]
```python
(mysite) c:\projects\mysite>python manage.py makemigrations
No changes detected
```
## migrate 실행하기
```python
이제 드디어 migrate 명령을 실행할 때가 되었다.
이 명령을 실행하면 장고는 등록된 앱에 있는 모델을 참조하여 실제 테이블을 생성한다.
```
- [명령 프롬프트]
```python
(mysite) C:\projects\mysite>python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, pybo, sessions
Running migrations:
  Applying pybo.0001_initial... OK
```
## 데이터 만들고 저장하고 조회하기
```python
지금까지 모델을 이용하여 실제 테이블을 만들었다.
그러면 장고에서는 모델을 어떻게 사용할까? 장고 셸을 사용하면 모델 사용법을 쉽게 익힐 수 있다.
```
## 장고 셸 실행하기
다음을 입력하여 장고 셸을 실행하자.
- [명령 프롬프트]
```python
(mysite) C:\projects\mysite>python manage.py shell
Python 3.8.2 (tags/v3.8.2:7b3ab59, Feb 25 2020, 22:45:29) [MSC v.1916 32 bit (Intel)] on win32
Type "help", "copyright", "credits" or "license" for more information.
(InteractiveConsole)
```
## Question, Answer 모델 임포트하기
장고 셸을 실행했으면 다음 명령으로 Question과 Answer 모델을 장고 셸에 임포트하자.
- [명령 프롬프트]
>>> from pybo.models import Question, Answer
> ## Questions 모델로 Question 모델 데이터 만들기
```python
Question 모델을 이용하여 Question 모델 데이터를 하나만 만들어 보자. Question 모델의 subject 속성에 제목을, content 속성에 질문 내용을 입력한다. 
create_date 속성은 DateTimeField이므로 timezone.now()로 현재 일시를 입력한다.
```
- [명령 프롬프트]
```python
>>> from django.utils import timezone
>>> q = Question(subject='pybo가 무엇인가요?', content='pybo에 대해서 알고 싶습니다.', create_date=timezone.now())
>>> q.save()
```
이 과정을 통해 객체 q가 생성된다. 객체가 생성된 다음 q.save()를 입력하면 Question 모델 데이터 1건이 데이터베이스에 저장된다.
## Question 모델 데이터의 id값 확인하기
Question 모델 데이터가 잘 생성되었는지 확인해 보자. 장고는 데이터 생성 시 데이터에 id값을 자동으로 넣어준다.
- [명령 프롬프트]
```python
>>> q.id
1
```
## Question 모델로 Question 모델 데이터 1개 더 만들기
이를 확인하기 위해 두 번째 Question 모델 데이터를 만들어 저장해 보자.
- [명령 프롬프트]
```python
>>> q = Question(subject='장고 모델 질문입니다.', content='id는 자동으로 생성되나요?', create_date=timezone.now())
>>> q.save()
>>> q.id
2
```
결과를 보면 두 번째로 생성한 Question 모델 데이터의 id는 예상대로 2이다.
## Question 모델 데이터 모두 조회하기
```python
지금까지의 실습 과정은 모두 Question 모델 데이터를 저장하기 위한 것이었다.
이번에는 저장된 데이터를 조회해 보자.
여기서는 특별히 모든 Question 모델 데이터를 조회하기 위해 Questions.objects.all()을 입력한다.
```
- [명령 프롬프트]
```python
>>> Question.objects.all()
<QuerySet [<Question: Question object (1)>, <Question: Question object (2)>]>
```
## Question 모델 데이터 조회 결과에 속성값 보여 주기
그런데 위의 결과는 데이터 유형을 출력한 것이므로 사람이 보기 불편하다. 
이때 Question 모델에 __str__ 메서드를 추가하면 된다.
- [파일이름: C:/projects/mysite/pybo/models.py ]
```python
(... 생략 ...)

class Question(models.Model):
    subject = models.CharField(max_length=200)
    content = models.TextField()
    create_date = models.DateTimeField()

# ---------------------------------- [edit] ---------------------------------- #
    def __str__(self):
        return self.subject
# ---------------------------------------------------------------------------- #

(... 생략 ...)
```
이렇게 수정하면 데이터 조회 시 id가 아닌 제목을 표시해 준다.
## Question 모델 데이터 다시 조회해 보기
```python
모델이 수정되었으므로 장고 셸을 다시 시작하자.
장고 셸에서 quit() 명령을 실행해 종료한 후 다시 장고 셸을 시작한다.
그다음, Question 모델을 다시 임포트한 후 Question 모델 데이터를 조회해 보자.
```
- [명령 프롬프트]
```python
(mysite) C:\projects\mysite>python manage.py shell
Python 3.8.2 (tags/v3.8.2:7b3ab59, Feb 25 2020, 22:45:29) [MSC v.1916 32 bit (Intel)] on win32
Type "help", "copyright", "credits" or "license" for more information.
(InteractiveConsole)
>>> from pybo.models import Question, Answer
>>> Question.objects.all()
<QuerySet [<Question: pybo가 무엇인가요?>, <Question: 장고 모델 질문입니다.>]>
```
## 조건으로 Question 모델 데이터 조회하기
```python
이전 단계에서는 Question 모델 데이터를 모두 조회했다.
조건을 주어 Question 모델 데이터를 조회하고 싶다면 filter 함수를 사용하면 된다.
```
- [명령 프롬프트]
```python
>>> Question.objects.filter(id=1)
<QuerySet [<Question: pybo가 무엇인가요?>]>
```
```python
filter 함수는 조건에 해당하는 데이터를 모두 찾아준다. 지금은 유일한 값인 id를 조건에 사용했으므로 Question 모델 데이터 하나만 나왔다.
하지만 filter 함수는 1개 이상의 데이터를 반환한다.
다만 filter 함수는 반환값이 리스트 형태인 QuerySet이므로 정말로 1개의 데이터만 조회하고 싶다면 filter 함수 대신 get 함수를 쓰는 것이 좋다.
```
## Question 모델 데이터 하나만 조회하기
get 함수를 사용하면 리스트가 아닌 데이터 하나만 조회할 수 있다.
## [명령 프롬프트]
```python
>>> Question.objects.get(id=1)
<Question: pybo가 무엇인가요?>
```
## get으로 조건에 맞지 않는 데이터 조회하기
조건에 맞지 않는 데이터를 get 함수로 조회하면 어떻게 될까? id가 3인 데이터를 조회해 보자.
- 명령 프롬프트
```python
>>> Question.objects.get(id=3)
Traceback (most recent call last):
  File "<console>", line 1, in <module>
  File "C:\venvs\mysite\lib\site-packages\django\db\models\manager.py", line 82, in manager_method
    return getattr(self.get_queryset(), name)(*args, **kwargs)
  File "C:\venvs\mysite\lib\site-packages\django\db\models\query.py", line 415, in get
    raise self.model.DoesNotExist(
pybo.models.Question.DoesNotExist: Question matching query does not exist.
```
그러면 이와 같은 오류 메시지를 볼 수 있다. 조건에 맞는 데이터 1개를 반환해야 하는데 조건에 맞는 데이터가 없으니 오류가 발생한 것이다.
## filter로 조건에 맞지 않는 데이터 조회하기
그러면 filter 함수는 어떨까? filter 함수로 조건에 맞지 않는 데이터를 조회해 보자.
- 명령 프롬프트
```python
>>> Question.objects.filter(id=3)
<QuerySet []>
```
```python
filter 함수는 조건에 맞는 데이터가 없으면 그저 빈 QuerySet을 반환한다.
get 함수는 반드시 1건의 데이터를 반환해야 한다는 특징이 있으므로 오류가 발생할 것이다.
이번에는 조금 더 유용한 데이터 조회 방법을 알아보자.
만약 제목에 '장고'라는 글자가 포함된 데이터를 조회하려면 어떻게 해야 할까?
```
## 제목의 일부를 이용하여 데이터 조회하기
```python
subject에 "장고"라는 문자열이 포함된 데이터를 조회하려면 조건에 subject__contains를 이용하면 된다.
이때 subject와 contains 사이의 언더스코어는 1개가 아니라 2개이다.
장고 셸에서 다음 코드를 입력해 보자.
```
- [명령 프롬프트]
```python
>>> Question.objects.filter(subject__contains='장고')
<QuerySet [<Question: 장고 모델 질문입니다.>]>
```
```python
subject__contains='장고'의 의미는 'subject 속성에 '장고'라는 문자열이 포함되어 있는가?'이다.
이 밖에도 filter 함수의 사용 방법은 무궁무진하다. 자세한 filter 함수의 사용 방법은 장고 공식 문서를 참조하자.

- 장고는 외워서 사용할 수 있는 프레임워크가 아니므로 장고 공식 문서를 자주 참고하는 습관을 들이는 것이 좋다.
- 장고 공식 문서(데이터 조회 관련): docs.djangoproject.com/en/3.0/topics/db/queries
```
## 데이터 수정하기
이번에는 지금까지 저장했던 Question 모델 데이터를 수정하자.
## Question 모델 데이터 수정하기
```python
Question 모델 데이터를 수정하려면 우선 수정할 데이터를 조회해야 한다.
다음은 id가 2인 데이터를 조회한 것이다. 이 데이터를 수정할 것이다.
```
- 명령 프롬프트
```python
>>> q = Question.objects.get(id=2)
>>> q
<Question: 장고 모델 질문입니다.>
```
## subject 속성 수정하기
subject 속성을 수정하자.
- 명령 프롬프트
```python
>>> q.subject = 'Django Model Question'
```
## 수정한 Question 모델 데이터 데이터베이스에 저장하기
```python
위의 단계만으로는 변경된 Question 모델 데이터가 데이터베이스에 적용되지 않는다.
반드시 다음처럼 save 함수를 실행해야 변경된 Question 모델 데이터가 데이터베이스에 반영된다.
```
- 명령 프롬프트
```python
>>> q.save()
>>> q
<Question: Django Model Question>
```
## 데이터 삭제하기
```python
이번에는 Question 모델 데이터를 데이터베이스에서 삭제해 보자.
```
## Question 모델 데이터 삭제하기
데이터 삭제는 데이터 수정과 비슷한 과정으로 진행된다. 여기서는 id가 1인 Question 모델 데이터를 삭제한다.
- 명령 프롬프트
```python
>>> q = Question.objects.get(id=1)
>>> q.delete()
(1, {'pybo.Question': 1})
```
```python
delete 함수를 수행하면 해당 데이터가 데이터베이스에서 즉시 삭제되며, 삭제된 데이터의 추가 정보가 반환된다.
(1, {'pybo.Question': 1})에서 앞의 1은 삭제된 Question 모델 데이터의 id를 의미하고 {'pybo.Question': 1}은 삭제된 모델 데이터의 개수를 의미한다.

Answer 모델을 만들 때 ForeignKey로 Question 모델과 연결한 것이 기억나는가? 만약 삭제한 Question 모델 데이터에 2개의
Answer 모델 데이터가 등록된 상태라면 (1, {'pybo.Answer': 2, 'pybo.Question': 1})와 같이 삭제된 답변 개수도 함께 반환될 것이다.
```
## 삭제 확인하기
Question 모델 데이터가 정말로 삭제되었는지 확인해 보자.
- 명령 프롬프트
```python
>>> Question.objects.all()
<QuerySet [<Question: Django Model Question>]>
```
결과를 보면 첫 번째 질문은 삭제되고, 두 번째 질문만 남아 있다.
## 연결된 데이터 알아보기
```python
앞에서 Answer 모델을 만들 때 ForeignKey로 Question 모델과 연결한 내용이 기억날 것이다.
Answer 모델은 Question 모델과 연결되어 있으므로 데이터를 만들 때 Question 모델 데이터가 필요하다.
```
## Answer 모델 데이터 만들기
id가 2인 Question 모델 데이터를 얻은 다음, 이를 이용하여 Answer 모델 데이터를 만들어 보자.
- 명령 프롬프트
```python
>>> q = Question.objects.get(id=2)
>>> q
<Question: Django Model Question>
>>> from django.utils import timezone
>>> a = Answer(question=q, content='네 자동으로 생성됩니다.', create_date=timezone.now())
>>> a.save()
```
## id 확인하기
Answer 모델 데이터에도 id가 있다.
- 명령 프롬프트
```python
>>> a.id
1
```
## Answer 모델 데이터 조회하기
Answer 모델 데이터를 get 함수로 조회해 보자. 조건은 id를 사용한다.
- 명령 프롬프트
```python
>>> a = Answer.objects.get(id=1)
>>> a
<Answer: Answer object (1)>
```
## 연결된 데이터로 조회하기: 답변에 있는 질문 조회하기
```python
Answer 모델 데이터에는 Question 모델 데이터가 연결되어 있으므로 Answer 모델 데이터에 연결된 Question 모델 데이터를 조회할 수 있다.
```
- 명령 프롬프트
```python
>>> a.question
<Question: Django Model Question>
```
```python
Answer 모델 객체인 a에는 question 속성이 있으므로 a를 통해 질문을 찾는 것은 매우 쉽다.
그렇다면 반대로 질문을 통해 답변을 찾을 수 있을까?
Question 모델에는 답변 속성이 없어서 불가능할 것 같지만 실제로는 가능하다.
```
## 연결된 데이터로 조회하기: 질문을 통해 답변 찾기
다음처럼 answer_set을 사용하면 된다.
- 명령 프롬프트
```python
>>> q.answer_set.all()
<QuerySet [<Answer: Answer object (1)>]>
```
```python
Question 모델과 Answer 모델처럼 서로 연결되어 있으면 연결모델명_set과 같은 방법으로 연결된 데이터를 조회할 수 있다. 
그리고 아마 여러분은 연결모델명_set을 써야 하는 경우와 그렇지 않은 경우가 헷갈릴 것이다.
```
```python
이때는 질문과 답변이 달리는 게시판을 상식적으로 생각해 보자. 질문 1개에는 1개 이상의 답변이 달릴 수 있으므로 질문에 달린 답변은 q.answer_set으로 조회해야 한다
(답변 세트를 조회). 답변은 질문 1개에 대한 것이므로 애초에 여러 개의 질문을 조회할 수 없다. 다시 말해 답변 1개 입장에서는 질문 1개만 연결되어 있으므로 a.question만 실행할 수 있다.
1개의 답변으로 여러 개의 질문을 a.question_set으로 조회하는 것은 불가능하며,
상식적으로 생각해 보아도 이상하다. 연결모델명_set은 정말 신통방통한 장고의 기능이 아닐 수 없다. 연결모델명_set은 자주 사용할 기능이니 꼭 기억하자.
```

장고 Admin을 사용하려면 슈퍼 유저를 먼저 생성해야 한다. 슈퍼 유저는 쉽게 말해 장고 운영자 계정이라 생각하면 된다.
## 슈퍼유저 생성하기

명령 프롬프트에서 python manage.py cratesuperuser 명령을 실행하여 슈퍼 유저를 생성하자.
사용자 이름에는 admin을 입력하고(다른 것을 입력해도 된다.), 이메일 주소는 가상의 이메일 주소를 적는다.
비밀번호는 여러분이 기억하기 쉬운 것으로 입력하자. 이때 단순한 구성의 비밀번호를 입력하면 경고 메세지가 나올 텐데, 이를 무시하는 옵션으로 'Bypass password validation and crate user anyway?'의 질문에 y를 입력해 답하자.
여기서는 학습을 위해 비밀번호를 단순하게 입력했다. 만약 실제 사이트를 운영할 계획이라면 보안에 취약한 비밀번호는 사용하면 안되므로 주의하자.

- 명령프롬프트
```python


(mysite) c:\projects\mysite> python manage.py cratesuperuser
사용자  이름 (leave blank to use 'pahke'): admin
이메일 주소: admin@mysite.com
Password:
password (again):
비밀번호가 너무 짧습니다. 최소 8 문자를 포함해야 합니다.
비밀번호가 너무 일상적인 단어입니다.
비밀번호가 전부 숫자로 되어 있습니다.
Bypass password validation and crate user anyway? [y/N]: y
Superuser created successfully.

여기서는 다음과 같은 정보로 슈퍼 유저를 생성했다.

항목 값
사용자명 admin
이메일 주소 admin@mysite.com
Password 1111
```
## 장고 Admin에 접속해 로그인하기
1단계를 통해 슈퍼 유저가 생성되었으니 장고 개발 서버를 구동한 후 localhost:8000/admin에 접속해 보자.
![](/img/1224_1.png)

[장고 Admin 로그인 화면]

그리고 앞에서 입력한 사용자명과 비밀번호를 입력해 로그인까지 진행하면 다음과 같은 화면이 나타난다.
![](/img/1224_2.png)

[장고 Admin 로그인 후 볼 수 있는 화면]

장고 Admin에서는 현재 등록된 그룹 및 사용자에 대한 정보 확인과 수정을 할 수 있다. 물론 그룹은 아직 등록하지 않았으므로 클릭해서 조회해 보아도 아무것도 표시되지 않는다. 그러면 본격적으로 장고 Admin의 재미있는 기능을 알아보자.

## 장고 Admin 모델 관리하기
우리는 Question, Answer 모델을 만들었다. 이 모델들을 장고 Admin에 등록하면 손쉽게 모델을 관리할 수 있다. 쉽게 말해 장고 셸로 수행했던 데이터 저장, 수정, 삭제 등의 작업을 장고 Admin에서 할 수 있다.
장고 Admin에서 어떤 마법이 벌어지는지 살펴보자. pybo/admin.py 파일을 열고 다음과 같이 코드를 입력하여 Question 모델을 장고 Admin에 등록하자.

```python
[파일이름: C:/projects/mysite/pybo/admin.py

from django.contrib import admin
from .models import Question

# ---------------------------------- [edit] ---------------------------------- #
class QuestionAdmin(admin.ModelAdmin):
    search_fields = ['subject']

admin.site.register(Question, QuestionAdmin)
```
## 장고 Admin에서 데이터 검색해 보기
장고 Admin으로 돌아가서 새로고침을 하면 검색 기능이 추가되었음을 알수있따. 검색어로 '장고'를 입력하고 <검색>을 눌러보자.

![](/img/1224_3.png)

[장고 검색 시 볼 수 있는 화면]

그러면 제목에 '장고'가 포함된 Question 모델 데이터만 조회된다. 장고 Admin에는 이런 마법 같은 기능이 무궁무진하다.

장고 Admin의 기능이 궁금하다면 장고 공식 문서를 참고하자. 장고 공식 문서 주소(장고 Admin 기능):
docs.djangoproject.com/en/3.0/ref/contrib/admin

## 질문 목록 기능 구현하기
질문 목록 조회를 위해 pybo/views.py 파일을 열어 코드를 조금씩 수정해보자.

### [1] Question 모델 데이터 작성일시 역순으로 조회하기

Question 모델을 임포트해 Question 모델 데이터를 작성한 날짜의 역순으로 조회하기 위해 order_by 함수를 사용했다. 조회한 Question 모델 데이터는 context 변수에 저장했다. context 변수는 조금 후에 설명할 render 함수가 템플릿을 HTML로 변환하는 과정에서 사용되는 데이터이다.

```python
from django.http import HttpResponse
# ---------------------------------- [edit] ---------------------------------- #
from .models import Question
# ---------------------------------------------------------------------------- #

def index(request):
# ---------------------------------- [edit] ---------------------------------- #
    """
    pybo 목록 출력
    """

    question_list = Question.objects.order_by('-crate_date')
    context = {'question_list': question_list}
# ---------------------------------------------------------------------------- # 
    return HttpResponse("안녕하세요 pybo에 오신걸 환영합니다.")
```
order_by 함수는 조회한 데이터를 특정 속성으로 정렬하며, '-create_date'는 - 기호가 앞에 붙어 있으므로 작성일시의 역순을 의미한다.

### [2] render로 화면 출력하기

조회한 Question 모델 데이터를 템플릿 파일을 사용하여 화면에 출력할 수 있는 render 함수를 사용해 보자.

``` python
# ---------------------------------- [edit] ---------------------------------- #
from django.shortcuts import render
# ---------------------------------------------------------------------------- #
from .models import Question


def index(request):
    """
    pybo 목록출력
    """
    question_list = Question.objects.order_by('-create_date')
    context = {'question_list': question_list}
# ---------------------------------- [edit] ---------------------------------- #
    return render(request, 'pybo/question_list.html', context)
# ---------------------------------------------------------------------------- #
```
### [3] 템플릿을 모아 저장할 디렉터리 만들기

템플릿을 만들기 전에 템플릿을 저장할 디렉터리를 루트 디렉터리 바로 밑에 만든다.

* 루트디렉터리는 장고 프로젝트 디렉터리(C:/projects/mysite)를 의미한다.
```python
(mysite) c:\projects\mysite>mkdir templates
```

### [4] 템플릿 디렉터리 위치 config/settings.py에 등록하기

위에서 만든 템플릿 디렉터리르 장고 config/setting.py 파일에 등록하자. config/settings.py 파일을 열어 TEMPLATES 항목을 다음과 같이 수정한다.

```python
(... 생략 ...)
TEMPLATES = [
    {
        (... 생략 ...)
# ---------------------------------- [edit] ---------------------------------- #
        'DIRS': [BASE_DIR / 'templates'],
# ---------------------------------------------------------------------------- #
        (... 생략 ...)
    },
]
(... 생략 ...)
```
DIRS에는 템플릿 디렉터리를 여러 개 등록할 수 있다. 다만 현재 우리가 개발하는 파이보는 1개의 템플릿 디렉터리를 쓸 것이므로 BASE_DIR / 'templates'만 더 붙여 C:/projects/mysite/templates를 반환한다.

### [5] 템플릿 파일 만들기
위에서 만든 템플릿 디렉터리를 참고하여 qusetion_list.html 템플릿 파일을 mysite/templates/pybo/ 디렉터리에 생성하자. pybo 디렉터리를 templates 안에 새로 만들어 파일을 추가해야 한다.

![](img/2-04_1)

[templates/pybo/ 위치에 저장된 question list.html 파일]

그리고 템플릿 파일을 다음과 같이 작성한다.

```python
<!-- ------------------------------- [edit] -------------------------------- -->
{% if question in question_list %}
    <ul>
    {% for question in question_list %}
        <li><a href="/pybo/{{ question.id }}/">{{ question.subject }}</a></li>
    {% endfor %}
    </ul>
{% else %}
   <p>질문이 없습니다.</p>
{% endif %}
<!-- ----------------------------------------------------------------------- -->
```
{% if question_list %} 라는 문장이 눈에 띌 것이다. 바로 이것이 템플릿 태그이다. 템플릿 태그는 {% 와 %}로 둘러싸인 문장을 말한다.

다음 표에 정리한 템플릿 태그의 의미를 살펴보면 파이썬 문법과 크게 다르지 않음을 알 수 있다. 템플릿 태그는 따로 문법을 설명하지 않고 그때그때 필요할 때마다 설명하겠다.

- 템플릿 태그에서 사용된 question_list가 바로 render 함수에서 템플릿으로 전달한 Question 모델 데이터이다.
- 만약 템플릿 태그의 자세한 내용이 궁금하다면 장고 공식 문서를 참고하자.
- 템플릿 장고 공식 문서 주소:docs.djangoproject.com/en/3.0/topics/templates


- 템플릿 태그! 3가지 유형만 정리하면 끝!

장고의 템플릿 태그는 분기, 반복, 객체 출력이라는 3가지 유형만 알면 된다. 분기 템플릿 태그는 다음과 같다. 문법을 보면 알겠지만 파이썬의 if 문과 다르지 않다. 다만 if 문이 끝나는 부분에 {% endif %}를 사용하는 점만 다르다.

```python
{% if 조건문1 %}
    <p>조건문1에 해당되는 경우</p>
{% elif 조건문2 %}
    <p>조건문2에 해당되는 경우</p>
{% else %}
    <p>조건문1, 2에 모두 해당되지 않는 경우</p>
{% endif %}
```
반복 템플릿 태그는 다음과 같다. 이 역시 파이썬의 for 문과 다르지 않으며, 역시 for 문의 마지막은 {% endfor %}로 닫아야 한다.

```python
{% for item in list %}
    <p>순서: {{ forloop.counter }} </p>
    <p>{{ item }}</p>
{% endfor %}
```
또한 반복 템플릿 안에서는 forloop 객체를 사용할 수도 있다. forloop 객체는 반복 중 유용한 값을 제공한다.

- forloop.counter : for 문의 순서로 1부터 표시
- forloop.counter() : for  문의 순서로 0부터 표시
- forloop.first : for 문의 첫 번째 순서인 경우 True
- forloop.last : for 문의 마지막 순서인 경우 True

객체 출력 템플릿 태그는 다음과 같다. 객체에 속성이 있으면 파이썬과 동일한 방법으로 점(.) 연산자를 사용한다.

```python
{{ question }}
{{ question.id }}
{{ question.subject }}
```
### [6] 질문 목록이 잘 출력되는지 확인해 보기

템플릿 디렉터리를 추가한 상태이므로 장고 개발 서버를 다시 시작해 /pybo/에 접속하자. 장고 개발 서버를 다시 시작하지 않으면 장고가 템플릿 디렉터리를 인식하지 못해 오류가 발생한다.

![](/img/2-04_2.png)

[/pybo/에서 볼 수 있는 질문 목록]

화면을 보면 이전에 등록한 질문 2건이 보인다. 직접 장고 쏄이나 장고 Admin에서 다른 질문도 추가해 보면서 질문 목록이 잘 만들어지는지 테스트 해본다.

## 질문 상세 기능 구현하기

### [1] 질문 목록에서 아무 질문이나 눌러보기
질문 목록 화면에서 아무 질문(예를 들면 Django Model Question)이나 눌러 보자. 그러면 다음과 같은 오류 화면이 나타난다.

![](/img/2-04_3.png)

[질문 목록에서 질문을 눌러 이동한 화면(오류 화면)]

오류 화면이 나타난 이유는 /pybo/2/에 대한 URL 매핑을 추가하지 않았기 때문이다.

- 질문을 눌렀을 때 /pybo/2/와 같은 주소로 이동한 이유는 템플릿에서 href 엘리먼트에 link 속성을 <a href="/pybo/{{ question.id }}/">으로 지정했기 때문이다.

### [2] pybo
