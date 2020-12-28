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

- 질문을 눌렀을 때 /pybo/2/와 같은 주소로 이동한 이유는 템플릿에서 href 엘리먼트에 link 속성을 추가했기 때문이다.


### [2] pybo/views.py 열어 화면 추가하기
pyvo/views.py 파일을 열어 detail 함수를 추가한다.
```python
# ---------------------------------- [edit] ---------------------------------- #
def detail(request, question_id):
    """
    pybo 내용 출력
    """
    question = Question.objects.get(id=question_id)
    context = {'question': question}
    return render(request, 'pybo/question_detail.html', context)
# ---------------------------------------------------------------------------- #
```
추가된 내용은 앞에서 만든 index 함수와 크게 다르지 않다. detail 함수의 매개변수 question_id가 추가된 점이 다르다. 바로 이것이 URL 매핑에 있떤 question_id이다. 즉, /pybo/2/ 페이지가 호출되면 최종으로 detail 함수의 매개변수 question_id에 2가 전달된다.

![](/img/2-04_4.png)

/pybo/2/ 페이지호출 시 장고에서 벌어지는 일

### [4] pybo/question_detail.html 작성하기
위에서 render 함수가 question_detail.html 파일을 사용하고 있으므로 이에 대한 작업도 해야 한다. templates/pybo 디렉터리에 question_detail.html 파일을 만든 후 다음처럼 코드를 작성한다.
```python
<!-- ------------------------------- [edit] -------------------------------- -->
<h1>{{ question.subject }}</h1>

<div>
    {{ question.content }}
</div>
<!-- ----------------------------------------------------------------------- -->
```
{{ question.subject }}, {{ question.content }}의 question 객체는 detail 함수에서 render 함수에 전달한 context에 저장한 데이터이다.

### [5] 질문 상세 페이지에 접속해 보기
/pybo/2/에 접속해 보자. 그러면 질문 상세 화면이 나타난다! 축하한다!

![](/img/2-04_5.png)

[/pybo/2/에 제대로 접속된 화면]

## 오류 화면 구현하기
지금까지 질문 목록, 질문 상세 기능을 구현했다. 그런데 사용자가 잘못된 주소에 접속하면 어떻게 처리해야 할까?

### [1] 잘못된 주소에 접속해 보기
/pybo/30/에 접속해 보자. 그러면 다음과 같은 DoesNotExist 오류 화면이 나온다.

![](/img/2-04_6.png)

[/pybo/30/ 페이지 호출 시 나타나는 오류 화면]

당연한 오류이다. question_id가 30인 데이터를 조회하는 Question.object.get(id=30)에서 오류가 발생했기 때문이다.

![](/img/2-04_7.png)

- 참고로 현재는 config/settings.py의 DEBUG 항목이 True로 설정되어 있어 개발자에게 여러 정보를 알려 주는 오류 화면이 나타난다. 그런데 실제 서비스 화면에는 그런 중요한 정보가 표현되면 안 된다. 그래서 서비스를 할 때는 DEBUG 항목을 False로 설정한다.
- cofing/settings.py의 DEBUG 항목을 False로 설정하는 부분은 4장에서 자세히 다룬다.
### [2] 페이지가 존재하지 않음(404 페이지) 출력하기
존재하지 않는 페이지에 접속하면 오류 대신 404 페이지를 출력하도록 detail 함수를 수정하자. Question.objects.get(id=question_id)를 get_object_or_404(Question, pk=question_id)로 수정하면 된다.
```python
# ---------------------------------- [edit] ---------------------------------- #
from django.shortcuts import render, get_object_or_404
# ---------------------------------------------------------------------------- #

(... 생략 ...)

def detail(request, question_id):
    """
    pybo 내용 출력
    """
# ---------------------------------- [edit] ---------------------------------- #    
    question = get_object_or_404(Question, pk=question_id)
# ---------------------------------------------------------------------------- #    
    context = {'question': question}
    return render(request, 'pybo/question_detail.html', context)
```
get_object_or_404 함수는 모델의 기본키를 이용하여 모델 객체 한 건을 반환한다. pk에 해당하는 건이 없으면 오류 대신 404 페이지를 반환한다.

### [3] 404 페이지 출력 확인하기
/pybo/30/에 접속하면 404 페이지가 출력된다.

![](/img/2-04_8.png)

[get_object_or_404 함수로 나타나는 404 페이지]

웹 브라우저는 HTTP 요청을 하고, 장고는 그 요청에 응답을 한다. 보통의 경우에는 성공을 의미하는 200 응답 코드가 자동으로 반환된다. 하지만 요청하는 페이지가 없거나 서버에서 오류가 발생하면 다음과 같은 응답 코드가 반환된다.

200 : 성공

500 : 서버오류(Internal Server Error)

404 : 페이지 존재하지 않음(Not Found)

#### 장고 제네릭뷰 간단 소개
제네릭뷰(generic view)는 목록 조회나 상세 조회처럼 특정 패턴이 있는 뷰를 작성할 때 사용하는 매우 편리한 기능이다. 하지만 장고 입문자에게는 제네릭뷰의 실행 방식이 무척 이해하기 어렵다. 여러분에게는 제네릭뷰가 오히려 장고 학습에 혼란을 줄 수 있으므로 코너로 소개한다. 눈으로 코드를 살펴보기만 하자. 만약 우리가 views.py 파일에 작성한 index 함수나 detail 함수를 제네릭뷰로 변경하면 다음처럼 간략하게 작성할 수 있다.
```python
class IndexView(generic.ListView):
    """
    pybo 목록 출력
    """
    def get_queryset(self):
        return Question.objects.order_by('-create_date')


class DetailView(generic.DetailView):
    """
    pybo 내용 출력
    """
    model = Question
```
IndexView 클래스가 index 함수를 대체하고 DetailView 클래스가 detail 함수를 대체했다고 생각하면 된다. IndexView 클래스는 템플릿명이 명시적으로 지정되지 않으면 자동으로 모델명_list.html를 템플릿명으로 사용한다. 정리하자면 Question 모델을 사용하는 IndexView 클래스는 question_list.html, DetailView 클래스는 question_detail.html을 템플릿명으로 사용한다. 이어서 urls.py 파일은 다음과 같이 변경해야 한다.
```python
from django.urls import path

from . import views

app_name = 'pybo'
urlpatterns = [
    path('', views.IndexView.as_view()),
    path('<int:pk>/', views.DetailView.as_view()),
]
```
이렇듯 단순 모델의 목록 조회나 상세 조회는 제네릭뷰를 사용하면 매우 간편하다. 단 제네릭뷰는 복잡한 문제를 해결할 때 오히려 개발 난이도를 높이는 경우도 있으니 주의해야 한다.

## URL 더 똑똑하게 사용하기
이번에는 템플릿에서 사용한 URL 하드 코딩을 없애는 방법에 대해 알아보자. 그나저나 URL 하드 코딩이란 무엇일까? 잠시 question_list.html 템플릿에 사용된 href값을 보자.
```python
<li><a href="/pybo/{{ question.id }}/">{{ question.subject }}</a></li>
```
/pybo/{{ question.id }}는 질문 상세를 위한 URL 규칙이다. 하지만 이런 URL 규칙은 프로그램을 수정하면서 /pybo/question/2/ 또는 /pybo/2/question/으로 수정될 가능성도 있다. 이런 식으로 URL 규칙이 자주 변경된다면 템플릿에 사용된 모든 href값들을 일일이 찾아 수정해야 한다. URL 하드 코딩의 한계인 셈이다. 이런 문제를 해결하려면 해당 URL에 대한 실제 주소가 아닌 주소가 매핑된 URL 별칭을 사용해야 한다.

## URL 별칭으로 URL 하드 코딩 문제 해결하기
그러면 URL 별칭을 파이보에 적용해 보자.

### [1] pybo/urls.py 수정하여 URL 별칭 사용하기
템플릿의 href에 실제 주소가 아니라 URL 별칭을 사용하려면 우선 pybo/urls.py 파일을 수정해야 한다. path 함수에 있는 URL 매핑에 name 속성을 부여하자.
```python
from django.urls import path

from . import views

urlpatterns = [
# ---------------------------------- [edit] ---------------------------------- #
    path('', views.index, name='index'),
    path('<int:question_id>/', views.detail, name='detail'),
# ---------------------------------------------------------------------------- #    
]
```
이렇게 수정하면 실제 주소 /pybo/는 index라는 URL 별칭이, /pybo/2/는 detail이라는 URL 별칭이 생긴다.

### [2] pybo/question_list.html 템플릿에서 URL 별칭 사용하기
1단계에서 만든 별칭을 템플릿에서 사용하기 위해 /pybo/{{ question.id }}를 {% url 'detail' question.id %}로 변경하자.
- question.id는 URL 매핑에 정의된 <int: question_id>를 의미한다.
```python
(... 생략 ...)
    {% for question in question_list %}
<!-- ------------------------------- [edit] -------------------------------- -->
        <li><a href="{% url 'detail' question.id %}">{{ question.subject }}</a></li>
<!-- ----------------------------------------------------------------------- -->
    {% endfor %}
(... 생략 ...)
```
## URL 네임스페이스 알아보기
여기서 한 가지 더 생각할 문제가 있다. 현재의 프로젝트에서는 pybo 앱 하나만 사용하지만, 이후 pybo 앱 이외의 다른 앱이 프로젝트에 추가될 수도 있다. 이때 서로 다른 앱에서 같은 URL 별칭을 사용하면 중복 문제가 생긴다.

![](/img/2-05_1.png)

이 문제를 해결하려면 pybo/urls.py 파일에 네임스페이스(namespace)라는 개념을 도입해야 한다. 네임스페이스는 쉽게 말해 각각의 앱이 관리하는 독립된 이름 공간을 말한다.

### [1] pybo/urls.py에 네임스페이스 추가하기
pybo/urls.py 파일에 네임스페이스를 추가하려면 간단히 app_name 변수에 네임스페이스 이름을 저장하면 된다.
```python
from django.urls import path

from . import views

# ---------------------------------- [edit] ---------------------------------- #
app_name = 'pybo'
# ---------------------------------------------------------------------------- #

urlpatterns = [
    path('', views.index, name='index'),
    path('<int:question_id>/', views.detail, name='detail'),
]
```
네임스페이스 이름으로 'pybo'를 저장했다.

### [2] 네임스페이스 테스트하기 - 오류 발생!
/pybo/에 접속해 보자. 그러면 다음과 같은 오류가 발생한다.

![](/img/2-05_2.png)

[/pybo/ 페이지 요청 시 발생하는 네임스페이스 오류]

### [3] pybo/question_list.html 수정하기
오류가 발생한 이유는 템플릿에서 아직 네임스페이스를 사용하고 있지 않기 때문이다. {% url 'detail' question.id %}을 {% url 'pybo:detail' question.id %}으로 바꾸자.
```python
(... 생략 ...)
    {% for question in question_list %}
<!-- ------------------------------- [edit] -------------------------------- -->
        <li><a href="{% url 'pybo:detail' question.id %}">{{ question.subject }}</a></li>
<!-- ----------------------------------------------------------------------- -->        
    {% endfor %}
(... 생략 ...)
```
detail에 pybo라는 네임스페이스를 붙여준 것이다.

#### URL 별칭은 여러 곳에서 사용된다.
URL 별칭은 템플릿 외에도 여러 곳에서 사용된다. 예를 들어 URL 별칭은 redirect 함수에도 사용된다. 다음은 redirect 함수에서 pybo:detail을 사용한 예이다. 지금은 눈으로 살펴보고 넘어가자.
```python
redirect('pybo:detail', question_id=question.id)
```
## 답변 등록 기능 만들기
앞에서 질문 등록, 조회 기능을 만들었다. 이번에는 답변 등록과 답변을 보여주는 기능을 만들어 보자.

## 답변 저장하고 표시하기
### [1] 질문 상세 템플릿에 답변 등록 버튼 만들기

질문 상세 템플릿 pybo/question_detail.html 파일을 수정하자. form 엘리먼트 안에 textarea 엘리먼트와 input 엘리먼트를 포함시켜 답변 내용, 답변 등록 버튼을 추가하자.

- 장고 개발 시 form 데이터를 전송할 때는 보통 장고의 폼을 이용한다. 장고의 폼을 이용하는 방법은 조금 더 공부한 후 설명하겠다.
```python
<h1>{{ question.subject }}</h1>

<div>
    {{ question.content }}
</div>

<!-- ------------------------------- [edit] -------------------------------- -->
<form action="{% url 'pybo:answer_create' question.id %}" method="post">
{% csrf_token %}
<textarea name="content" id="content" rows="15"></textarea>
<input type="submit" value="답변등록">
</form>
<!-- ----------------------------------------------------------------------- -->
```
<답변 등록> 버튼을 누를 때 호출되는 URL은 action 속성에 있는 {% url 'pybo:answer_create' question.id %}이다. 그리고 form 엘리먼트 바로 아래에 있는 {% csrf_token %}이 눈에 띌 것이다. 이 코드는 보안 관련 항목이니 좀 더 자세히 설명하겠다. {% csrf_token %}는 form 엘리먼트를 통해 전송된 데이터(답변)가 실제로 웹 브라우저에서 작성된 데이터인지 판단하는 검사기 역할을 한다. 그러므로 <form ...> 태그 바로 밑에 {% csrf_token %}을 항상 입력해야 한다. 해킹처럼 올바르지 않은 방법으로 데이터가 전송되면 서버에서 발행한 csrf_token값과 해커가 보낸 csrf_token값이 일치하지 않으므로 오류를 발생시켜 보안을 유지할 수 있다.

#### csrf_token은 장고의 기본 기능이다
csrf_token을 사용하려면 장고에 CsrfViewMiddleware라는 미들웨어를 추가해야 한다. 하지만 이 미들웨어는 장고 프로젝트 생성 시 자동으로 config/settings.py 파일의 MIDDLEWARE라는 항목에 추가되므로 여러분이 직접 입력할 필요는 없다.
```python
(... 생략 ...)
MIDDLEWARE = [
    (... 생략 ...)
    'django.middleware.csrf.CsrfViewMiddleware',
    (... 생략 ...)
]
(... 생략 ...)
```
혹시라도 csrf_token을 사용하고 싶지 않다면 config/settings.py 파일의 MIDDLEWARE 항목에서 해당 코드를 주석 처리하면 되겠지만, csrf_token 기능을 굳이 제외할 필요는 없다.

### [2] 질문 상세 페이지에 접속해 보기
위의 단계를 마친 다음 pybo/2에 접속해 보자. 그러면 아마도 'answer_create를 찾을 수 없다'는 오류 화면이 나타날 것이다.

![](/img/2-06_1.png)

오류 발생 이유는 1단계에서 입력한 form 엘리먼트의 action 속성에 있는 {% url 'pybo:answer_create' question.id %}에 해당하는 URL 매핑이 없기 때문이다.

### [3] 답변 등록을 위한 URL 매핑 등록하기
pybo/urls.py 파일에 답변 등록을 위한 URL 매핑을 등록하자.

```python
(... 생략 ...)
urlpatterns = [
    path('', views.index, name='index'),
    path('<int:question_id>/', views.detail, name='detail'),
# ---------------------------------- [edit] ---------------------------------- #
    path('answer/create/<int:question_id>/', views.answer_create, name='answer_create'),
# ---------------------------------------------------------------------------- #    
]
(... 생략 ...)
```
이 코드는 사용자가 상세 화면에서 <질문답변> 버튼을 눌렀을 때 작동할 form 엘리먼트의 /pybo/answer/create/2/에 대한 URL 매핑을 추가한 것이다.

### [4] answer_create 함수 추가하기
form 엘리먼트에 입력된 값을 받아 데이터베이스에 저장할 수 있도록 answer_create 함수를 pybo/views.py 파일에 추가하자.

```python
from django.shortcuts import render, get_object_or_404
from .models import Question
# ---------------------------------- [edit] ---------------------------------- #
from django.utils import timezone

(... 생략 ...)

def answer_create(request, question_id):
    """
    pybo 답변등록
    """
    question = get_object_or_404(Question, pk=question_id)
    question.answer_set.create(content=request.POST.get('content'), create_date=timezone.now())
# ---------------------------------------------------------------------------- #
```
answer_create 함수의 question_id 매개변수에는 URL 매핑 정보값이 넘어온다. 예를 들어 /pybo/answer/create/2가 요청되면 question_id에는 2가 넘어온다. request 매개변수에는 pybo/question_detail.html에서 textarea에 입력된 데이터가 파이썬 객체에 담겨 넘어온다. 이 값을 추출하기 위한 코드가 바로 request.POST.get('content')이다. 그리고 Question 모델을 통해 Answer 모델 데이터를 생성하기 위해 question.answer_set.create를 사용했다.

- request.POST.get('content')는 POST 형식으로 전송된 form 데이터 항목 중 name이 content인 값을 의미한다.
- Answer 모델이 Question 모델을 Foreign Key로 참조하고 있으므로 question.answer_set 같은 표현을 사용할 수 있다.

#### Answer 모델을 통해 데이터를 저장할 수도 있다
본 실습에서는 Answer 모델 데이터 저장을 위해 Question 모델을 사용했다. 하지만 Answer 모델을 직접 사용해도 Answer 모델 데이터를 저장할 수 있다.

[Answer 모델로 Answer 모델 데이터 저장하는 예]
```python
question = get_object_or_404(Question, pk=question_id)
answer = Answer(question=question, content=request.POST.get('content'), create_
date=timezone.now())
answer.save()
```

### [5] 답변 등록 후 상세 화면으로 이동하게 만들기
답변을 생성한 후 상세 화면을 호출하려면 redirect 함수를 사용하여 코드를 작성하면 된다. redirect 함수는 함수에 전달된 값을 참고하여 페이지 이동을 수행한다. redirect 함수의 첫 번째 인수에는 이동할 페이지의 별칭을, 두 번째 인수에는 해당 URL에 전달해야 하는 값을 입력한다.

```python
# ---------------------------------- [edit] ---------------------------------- #
from django.shortcuts import render, get_object_or_404, redirect
# ---------------------------------------------------------------------------- #
from .models import Question
from django.utils import timezone

(... 생략 ...)

def answer_create(request, question_id):
    """
    pybo 답변등록
    """
    question = get_object_or_404(Question, pk=question_id)
    question.answer_set.create(content=request.POST.get('content'), create_date=timezone.now())
# ---------------------------------- [edit] ---------------------------------- #    
    return redirect('pybo:detail', question_id=question.id)
# ---------------------------------------------------------------------------- #
```
질문 상세 페이지에 다시 접속해 보자. 그러면 다음처럼 답변을 등록할 수 있는 창과 <답변등록> 버튼이 보인다.

![](img/2-06_2.png)

화면이 조금 엉성하다고 실망할 것 없다. 일단 핵심 기능을 완성한다 생각하고 넘어가자. 화면 다듬기는 기능을 완성한 후 진행할 것이다.

텍스트 창에 아무 값이나 입력하고 <답변등록>을 눌러 보자. 아마 아무런 변화가 없을 것이다. 왜냐하면 아직 등록한 답변을 표시하는 기능을 추가하지 않았기 때문이다. 이어서 답변 표시 기능을 만들어 보자.

### [6] 등록된 답변 표시하기
질문 상세 화면에 답변을 표시하려면 pybo/question_detail.html 파일을 수정해야 한다.
```python
<h1>{{ question.subject }}</h1>

<div>
    {{ question.content }}
</div>

<!-- ------------------------------- [edit] -------------------------------- -->
<h5>{{ question.answer_set.count }}개의 답변이 있습니다.</h5>
<div>
    <ul>
    {% for answer in question.answer_set.all %}
        <li>{{ answer.content }}</li>
    {% endfor %}
    </ul>
</div>
<!-- ----------------------------------------------------------------------- -->

<form action="{% url 'pybo:answer_create' question.id %}" method="post">
{% csrf_token %}
<textarea name="content" id="content" rows="15"></textarea>
<input type="submit" value="답변등록">
</form>
```
question.answer_set.count는 답변 개수를 의미한다. 질문 내용과 답변 입력 창 사이에 답변 표시 영역을 추가했다. 코드를 위처럼 수정한 후에 질문 상세 페이지에 접속하면 다음과 같은 화면을 볼 수 있다.

![](img/2-06_3.png)

축하한다! 파이보의 답변 저장, 답변 조회 기능을 완성했다.

지금까지 질문과 답변을 등록하고 조회하는 기능을 만들었다. 그런데 그럴싸한 화면이 아니라서 아쉽다. 여기서는 스타일시트를 이용해 웹 페이지에 디자인을 적용하는 방법을 알아본다.

## 웹 페이지에 스타일시트 적용하기
웹 페이지에 디자인을 적용하려면 스타일시트(CSS)를 사용해야 하며, 스타일시트를 파이보에 적용하려면 CSS 파일이 스태틱(static) 디렉터리에 있어야 한다.
- CSS 파일은 장고에서 정적(static)파일로 분류한다. 정적 파일은 주로 이미지(.png, .jpg)나 자바스크립트(.js), 스타일시트(.css) 같은 파일을 의미한다.
### [1] 설정 파일에 스태틱 디렉터리 위치 추가하기
config/settings.py 파일을 열어 STATICFILES_DIRS에 스태틱 디렉터리 경로를 추가하자. BASE_DIR / 'static'은 C:/projects/mysite/static을 의미한다.
```python
(... 생략 ...)
STATIC_URL = '/static/'
# ---------------------------------- [edit] ---------------------------------- #
STATICFILES_DIRS = [
    BASE_DIR / 'static',
]
# ---------------------------------------------------------------------------- #
```
### [2] 스태틱 디렉터리 만들고 스타일시트 작성하기
프로젝트 루트 디렉터리에 static이라는 이름의 디렉터리를 생성하자. 루트 디렉터리는 C:/ projects/mysite를 의미한다.

```python
(mysite) C:/projects/mysite>mkdir static
```
#### 스태틱 디렉터리를 관리하는 방법
pybo 앱 디렉터리 바로 아래에 static이라는 디렉터리를 만들어도 장고에서 스태틱 디렉터리로 인식된다. 즉, 다음과 같이 static 디렉터리를 만들어도 된다.

[static 디렉터리 구성]
```python
C:/projects/mysite/pybo/static
```
하지만 이 방법 역시 템플릿 디렉터리를 구성할 때 설명했듯 프로젝트 관리를 불편하게 만든다. 이 책에서는 스태틱 디렉터리도 템플릿 디렉터리처럼 한곳으로 모아서 관리할 것이다.

static 디렉터리를 만들었으면 그곳에 style.css 파일을 만들어 다음 코드를 작성하자. 여기서는 답변을 등록할 때 사용하는 textarea를 100%로 넓히고, <답변등록> 버튼 위에 margin을 10px 추가했다.

```python
/* ---------------------------------- [edit] --------------------------------- */
textarea {
    width:100%;
}

input[type=submit] {
    margin-top:10px;
}
/* --------------------------------------------------------------------------- */
```

- CSS를 활용하면 이보다 더 예쁘게 만들 수 있다. 그것은 필자보다 디자인 감각이 뛰어난 독자 여러분 몫으로 남겨 둔다. 그 대신 다음 절에서 부트스트랩을 이용해 좀 더 예쁘게 만드는 방법을 소개한다.

### [3] 질문 상세 템플릿에 스타일 적용하기
pybo/question_detail.html 파일에 style.css 파일을 적용해 보자. 스태틱 파일을 사용하기위해 템플릿 파일 맨 위에 {% load static %} 태그를 삽입하고, link 엘리먼트 href 속성에 {% static 'style.css' %}를 적자.

```python
<!-- ------------------------------- [edit] -------------------------------- -->
{% load static %}
<link rel="stylesheet" type="text/css" href="{% static 'style.css' %}">
<!-- ----------------------------------------------------------------------- -->
<h1>{{ question.subject }}</h1>
(... 생략 ...)
```
추가한 코드는 static 디렉터리의 style.css 파일을 연결한다는 의미다. 질문 상세 화면은 다음과 같이 바뀔 것이다. 만약 아무런 변화가 없다면 개발 서버를 종료했다가 다시 실행해 보자.

- 개발 서버를 종료하려면 <Ctrl+C>를 누르면 된다.

![](img/2-07_1.png)

축하한다. 이제 조금은 그럴싸한 화면을 출력할 수 있게 되었다.

## 부트스트랩으로 더 쉽게 화면 꾸미기
웹 디자이너 없이 웹 프로그램을 만들다 보면 화면 디자인 작업을 하는 데 얼마나 많은 시간과 고민이 필요한지 알 수 있을 것이다. 이번에 소개하는 부트스트랩(Bootstrap)은 개발자 혼자서도 화면을 괜찮은 수준으로 만들 수 있게 도와주는 도구다. 부트스트랩은 트위터를 개발하면서 만들어졌고 지속적으로 관리되고 있는 오픈소스 프로젝트이다.

## 파이보에 부트스트랩 적용하기
파이보에 부트스트랩을 적용해 멋진 모습으로 변신시켜 보자.
### [1] 부트스트랩 설치하기
웹 브라우저를 열고 다음 URL에 접속한 다음 <Download>를 눌러 부트스트랩 설치 파일을 내려받자.

- 부트스트랩 4.5.3 버전 다운로드: getbootstrap.com/docs/4.5/getting-started/download
- 이 책에 실린 코드는 부트스트랩 버전5에서 정상 동작하지 않는다. 혹시 실습한 내용이 동일하게 보이지 않으면 부트스트랩 버전이 5가 아닌지 확인해 보자. 이 책은 부트스트랩 4.5.3 버전(버전 4의 마지막 버전)을 기준으로 실습을 진행한다.
- 부트스트랩은 2020년 12월 7일 기준으로 버전 5.0(베타)가 출시되었다.

![](/img/2-08_1.png)

그러면 bootstrap-4.5.3-dist.zip 파일이 다운로드된다. 내려받은 파일의 압축을 해제하면 많은 파일이 들어 있다. 이 중에서 bootstrap.min.css 파일만 복사해서 mysite/static 디렉터리에 저장하자.

- 압축파일내 경로 : bootstrap-4.5.3-dist.zip\bootstrap-4.5.3-dist\css\bootstrap.min.css
- 카피한 경로 : C:\projects\mysite\static\bootstrap.min.css

### [2] 질문 목록 템플릿에 부트스트랩 적용하기
pybo/question_list.html 파일에 부트스트랩을 적용하기 위해 {% load static %} 태그와 link 엘리먼트를 추가하자.

```python
<!-- ------------------------------- [edit] -------------------------------- -->
{% load static %}
<link rel="stylesheet" type="text/css" href="{% static 'bootstrap.min.css' %}">
<!-- ----------------------------------------------------------------------- -->
{% if question_list %}
(... 생략 ...)
```
이어서 부트스트랩을 이용하여 템플릿을 다음과 같이 재구성하자. 여기서 사용된 container, my-3, thead-dark 등이 바로 부트스트랩이 제공하는 클래스이다.

```python
<!-- ------------------------------- [edit] -------------------------------- -->
{% load static %}
<link rel="stylesheet" type="text/css" href="{% static 'bootstrap.min.css' %}">
<div class="container my-3">
    <table class="table">
        <thead>
        <tr class="thead-dark">
            <th>번호</th>
            <th>제목</th>
            <th>작성일시</th>
        </tr>
        </thead>
        <tbody>
        {% if question_list %}
        {% for question in question_list %}
        <tr>
            <td>{{ forloop.counter }}</td>
            <td>
                <a href="{% url 'pybo:detail' question.id %}">{{ question.subject }}</a>
            </td>
            <td>{{ question.create_date }}</td>
        </tr>
        {% endfor %}
        {% else %}
        <tr>
            <td colspan="3">질문이 없습니다.</td>
        </tr>
        {% endif %}
        </tbody>
    </table>
</div>
<!-- ----------------------------------------------------------------------- -->
```
기존에는 질문 목록을 ul 엘리먼트로 간단히 표시했지만, 여기서는 table 엘리먼트로 바꾸고 질문의 일련번호와 작성일시 항목도 추가했다. 질문의 일련번호는 {{ forloop.counter }}를 이용하여 표시했다. {{ forloop.counter }}는 {% for ... %}에서 반복 시 자동으로 매겨지는 순섯값을 의미한다.

웹 브라우저에서 /pybo에 접속하면 부트스트랩이 적용된 화면을 볼 수 있다.

![](/img/2-08_2.png)

- 앞으로 다른 화면을 만들 때도 부트스트랩을 사용할 것이다. 그러나 이 책의 주제는 부트스트랩이 아니므로 간단히 설명한다. 혹시 자세한 내용이 궁금하다면 부트스트랩 공식 문서를 읽어 보기를 권한다.
- 부트스트랩 공식 문서: getbootstrap.com/docs/4.5/getting-started/introduction

### [3] 질문 상세 템플릿에 부트스트랩 사용하기
질문 상세 템플릿도 다음과 같이 부트스트랩을 적용하자.

```python
<!-- ------------------------------- [edit] -------------------------------- -->
{% load static %}
<link rel="stylesheet" type="text/css" href="{% static 'bootstrap.min.css' %}">
<div class="container my-3">
    <h2 class="border-bottom py-2">{{ question.subject }}</h2>
    <div class="card my-3">
        <div class="card-body">
            <div class="card-text" style="white-space: pre-line;">{{ question.content }}</div>
            <div class="d-flex justify-content-end">
                <div class="badge badge-light p-2">
                    {{ question.create_date }}
                </div>
            </div>
        </div>
    </div>
    <h5 class="border-bottom my-3 py-2">{{question.answer_set.count}}개의 답변이 있습니다.</h5>
    {% for answer in question.answer_set.all %}
    <div class="card my-3">
        <div class="card-body">
            <div class="card-text" style="white-space: pre-line;">{{ answer.content }}</div>
            <div class="d-flex justify-content-end">
                <div class="badge badge-light p-2">
                    {{ answer.create_date }}
                </div>
            </div>
        </div>
    </div>
    {% endfor %}
    <form action="{% url 'pybo:answer_create' question.id %}" method="post" class="my-3">
        {% csrf_token %}
        <div class="form-group">
            <textarea name="content" id="content" class="form-control" rows="10"></textarea>
        </div>
        <input type="submit" value="답변등록" class="btn btn-primary">
    </form>
</div>
<!-- ----------------------------------------------------------------------- -->
```
질문, 답변은 하나의 뭉치에 해당되므로 부트스트랩의 card 컴포넌트를 사용했고, 질문 내용과 답변 내용은 style 속성으로 white-space: pre-line을 적용하여 텍스트의 줄바꿈을 정상적으로 보이게 만들었다. 부트스트랩 클래스 my-3은 상하 마진값 3을 의미한다. py-2는 상하 패딩값 2, p-2는 상하좌우 패딩값 2를 의미한다. d-flex justify-content-end는 컴포넌트 오른쪽 정렬을 의미한다.

- 부트스트랩 공식 문서(card 컴포넌트) : getbootstrap.com/docs/4.5/components/car

### [4] 질문 상세 화면 확인하기
질문 상세 화면이 어떻게 바뀌었는지 확인해 보자.

![](/img/2-08_3.png)

부트스트랩을 사용하면 정말 빠르게 만족스러운 화면을 만들 수 있다.

## 표준 HTML과 템플릿 상속 사용해 보기
혹시 눈치챘는지 모르겠지만, 지금까지 작성한 질문 목록과 질문 상세 템플릿 파일은 표준 HTML 구조가 아니다. 어떤 운영체제나 웹 브라우저를 사용하더라도 웹 페이지가 동일하게 보이고 정상적으로 작동 하게 하려면 반드시 웹 표준을 지키는 HTML 문서를 작성해야 한다.

## 표준 HTML 구조는 어떻게 생겼을까?
표준 HTML 문서의 구조는 다음과 같이 html, head, body 엘리먼트가 있어야 하며, CSS 파일은 head 엘리먼트 안에 있어야 한다. 또한 head 엘리먼트 안에는 meta, title 엘리먼트 등이 포함되어야 한다.

[표준 HTML 구조 예]

```python
{% load static %}
<!doctype html>
<html lang="ko">
<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" type="text/css" href="{% static 'bootstrap.min.css' %}">
    <!-- pybo CSS -->
    <link rel="stylesheet" type="text/css" href="{% static 'style.css' %}">
    <title>Hello, pybo!</title>
</head>
<body>

(... 생략 ...)

</body>
</html>
```

## 템플릿을 표준 HTML 구조로 바꾸기
앞에서 작성한 템플릿 파일을 표준 HTML 구조로 수정해 보자. 그런데 모든 템플릿 파일을 표준 HTML 구조로 변경하면 body 엘리먼트 바깥 부분은 모두 같은 내용으로 중복된다. 그리고 CSS 파일 이름이 변경되거나 새로운 CSS 파일이 추가되면 head 엘리먼트의 내용을 수정하려고 템플릿 파일을 일일이 찾아다녀야 하는 불편함도 있다.

장고는 이런 불편함을 해소하기 위한 템플릿 상속(extends) 기능을 제공한다. 여기서는 단순히 템플릿을 표준 HTML 구조로 바꾸는 것이 아니라 템플릿 상속 기능까지 사용할 것이다. 그러면 파일을 하나씩 수정해 보자.

### [1] 템플릿 파일의 기본 틀 작성하기
우선 템플릿 파일의 기본 틀인 base.html 템플릿을 작성하자. 모든 템플릿에서 공통으로 입력할 내용을 여기에 포함한다고 생각하면 된다.

```python
<!-- ------------------------------- [edit] -------------------------------- -->
{% load static %}
<!doctype html>
<html lang="ko">
<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" type="text/css" href="{% static 'bootstrap.min.css' %}">
    <!-- pybo CSS -->
    <link rel="stylesheet" type="text/css" href="{% static 'style.css' %}">
    <title>Hello, pybo!</title>
</head>
<body>
<!-- 기본 템플릿 안에 삽입될 내용 Start -->
{% block content %}
{% endblock %}
<!-- 기본 템플릿 안에 삽입될 내용 End -->
</body>
</html>
<!-- ----------------------------------------------------------------------- -->
```
body 엘리먼트에 {% block content %}와 {% endblock %} 템플릿 태그가 있다. 바로 이 부분이 이후 base.html 템플릿 파일을 상속한 파일에서 구현해야 하는 영역이 된다. 이제 question_list.html 템플릿을 다음과 같이 변경하자.

### [2] 질문 목록 템플릿 수정하기
질문 목록을 나타내는 question_list.html 파일을 다음과 같이 수정하자.

```python
<!-- ------------------------------- [edit] -------------------------------- -->
{% extends 'base.html' %}
{% block content %}
<!-- ----------------------------------------------------------------------- -->
<div class="container my-3">
    <table class="table">
        (... 생략 ...)
    </table>
</div>
<!-- ------------------------------- [edit] -------------------------------- -->
{% endblock %}
<!-- ----------------------------------------------------------------------- -->
```
base.html 템플릿 파일을 상속받고자 {% extends 'base.html' %} 템플릿 태그를 사용했다. 그리고 {% block content %}와 {% endblock %} 사이에 question_list.html 파일에서만 사용할 내용을 작성했다. 이제 question_list.html은 base.html을 상속받았으므로 표준 HTML 구조를 갖추게 되었다.

### [3] 질문 상세 템플릿 수정하기

```python
<!-- ------------------------------- [edit] -------------------------------- -->
{% extends 'base.html' %}
{% block content %}
<!-- ----------------------------------------------------------------------- -->
<div class="container my-3">
    <h2 class="border-bottom py-2">{{ question.subject }}</h2>
    (... 생략 ...)
    </form>
</div>
<!-- ------------------------------- [edit] -------------------------------- -->
{% endblock %}
<!-- ----------------------------------------------------------------------- --
```
### [4] 기존 스타일 파일 내용 비우기
부트스트랩을 사용하게 되었으니 style.css 파일의 내용을 비우자. 이 파일은 이후 부트스트랩으로 표현할 수 없는 스타일을 위해 사용할 것이므로 파일 자체를 삭제하지는 말고 내용만 삭제하자.

```python
/* ---------------------------------- [edit] --------------------------------- */
/* 내용을 전부 삭제하자. */
/* --------------------------------------------------------------------------- */
```
## 질문 등록 기능 만들기
지금까지는 질문을 등록하기 위해 장고 셸이나 장고 Admin을 사용했다. 이번에는 파이보 서비스를 통해 질문을 등록하는 기능을 만들어 보자.

질문 목록 화면 아래에 질문 등록 버튼을 만든 다음, 질문 등록 기능을 완성해 보자. 참고로 질문 등록 기능은 이 장 끝까지 진행해야 완벽하게 작동한다.

### [1] 질문 등록 버튼 만들기
우선 다음처럼 질문 목록 템플릿을 열고 </table> 태그 아래에 질문 등록 버튼을 생성하자.

```python
    (... 생략 ...)
    </table>
<!-- ------------------------------- [edit] -------------------------------- -->
    <a href="{% url 'pybo:question_create' %}" class="btn btn-primary">질문 등록하기</a>
<!-- ----------------------------------------------------------------------- -->    
</div>
{% endblock %}
```
a 엘리먼트에 href 속성으로 질문 등록 URL을 {% url 'pybo:question_create' %}처럼 추가하고 부트스트랩 클래스 "btn btn-primary"를 지정했다.

### [2] URL 매핑 추가를 위해 pybo/urls.py 수정하기
위에서 {% url 'pybo:question_create' %}이 추가되었으니 pybo/urls.py 파일에 URL 매핑을 추가하자.

```python
(... 생략 ...)
urlpatterns = [
    (... 생략 ...)
# ---------------------------------- [edit] ---------------------------------- #
    path('question/create/', views.question_create, name='question_create'),
# ---------------------------------------------------------------------------- #
]
```

### [3] pybo/views.py 수정하기
그리고 URL 매핑에 의해 실행될 views.question_create 함수를 작성하자

```python
# ---------------------------------- [edit] ---------------------------------- #
from .forms import QuestionForm
# ---------------------------------------------------------------------------- #

(... 생략 ...)

# ---------------------------------- [edit] ---------------------------------- #
def question_create(request):
    """
    pybo 질문등록
    """
    form = QuestionForm()
    return render(request, 'pybo/question_form.html', {'form': form})
# ---------------------------------------------------------------------------- #
```
question_create 함수는 QuestionForm 클래스로 생성한 객체 form을 사용할 것이다. 여기서 QuestionForm 클래스는 질문을 등록하기 위해 사용하는 장고의 폼이다. render 함수에 전달한 {'form': form}은 템플릿에서 폼 엘리먼트를 생성할 때 사용한다. 템플릿을 작성할 때 자세히 알아보겠다.

- QuestionForm을 아직 작성하지 않아 파이참에서는 오류가 표시될 것이다. QuestionForm은 곧 만들 것이니 일단은 오류가 나오는 상태로 놔두자.

### [4] pybo/forms.py에 장고 폼 작성하기
pybo 디렉터리 바로 아래에 forms.py 파일을 새로 만들어 ModelForm을 상속받은 QuestionForm 클래스를 작성하자. QuestionForm 클래스 안에 내부 클래스로 Meta 클래스를 작성하고, Meta 클래스 안에는 model, fields 속성을 다음과 같이 작성하자

```python
# ---------------------------------- [edit] ---------------------------------- #
from django import forms
from pybo.models import Question


class QuestionForm(forms.ModelForm):
    class Meta:
        model = Question
        fields = ['subject', 'content']
# ---------------------------------------------------------------------------- #
```
이 같은 클래스를 장고 폼이라 한다. 장고 폼은 사실 2개의 폼으로 구분할 수 있는데, forms.Form을 상속받으면 폼, forms.ModelForm을 상속받으면 모델 폼이라 부른다. 여기서는 form.ModelForm을 상속받아 모델 폼을 만들었다. 모델 폼은 말 그대로 모델과 연결된 폼이며, 모델 폼 객체를 저장하면 연결된 모델의 데이터를 저장할 수 있다. 아직 모델 폼 객체를 저장한다는 의미가 잘 이해되지는 않겠지만, 곧 질문 등록 기능을 완성하며 이 내용을 자세히 설명하겠다. 내부 클래스로 선언한 Meta 클래스가 눈에 띌 것이다. 장고 모델 폼은 내부 클래스로 Meta 클래스를 반드시 가져야 하며, Meta 클래스에는 모델 폼이 사용할 모델과 모델의 필드들을 적어야 한다. QuestionForm 클래스는 Question 모델과 연결되어 있으며, 필드로 subject, content를 사용한다고 정의했다.

### [5] pybo/question_form.html 만들어 장고 폼 사용
질문 등록을 위해 pybo/question_form.html 파일을 생성하고 다음과 같이 작성하자.

```python
<!-- ------------------------------- [edit] -------------------------------- -->
{% extends 'base.html' %}

{% block content %}
<div class="container">
    <h5 class="my-3 border-bottom pb-2">질문등록</h5>
    <form method="post" class="post-form my-3">
        {% csrf_token %}
        {{ form.as_p }}
        <button type="submit" class="btn btn-primary">저장하기</button>
    </form>
</div>
{% endblock %}
<!-- ----------------------------------------------------------------------- -->
```
코드의 {{ form.as_p }}에서 form이 바로 question_create 함수에서 전달한 QuestionForm 객체이다. 여기서 {{ form.as_p }}는 모델 폼과 연결된 입력 항목 subject, content에 값을 입력할 수 있는 HTML 코드를 자동으로 만들어 준다.

### [6] 질문 등록 화면 확인하기
이제 웹 브라우저에서 지금까지 작업한 내용의 결과를 확인해 보자. /pybo/ 페이지를 요청해 보자. 그러면 <질문 등록하기> 버튼이 표시될 것이다. <질문 등록하기> 버튼을 누르자.

![](img/2-10_1.png)

그러면 다음과 같은 질문 등록 화면이 나타나고 질문 등록 화면에는 템플릿에 작성한 {{ form.as_p }}에 의해 나타난 입력 항목 subject, content를 확인할 수 있다. 값을 입력하고 <저장하기> 버튼을 눌러 보자.

![](img/2-10_2.png)

그런데 아무런 반응이 없다. 왜냐하면 pybo/views.py 파일에 정의한 question_create 함수에 입력 데이터를 저장하기 위한 코드를 작성하지 않았기 때문이다. 이제 입력 데이터를 저장하는 방법에 대해 알아보자.

### [7] 입력 데이터 저장하기
pybo/views.py 파일의 question_create 함수를 수정하자. 코드가 꽤 기니 주의해서 입력하자.

```python
def question_create(request):
    """
    pybo 질문등록
    """
# ---------------------------------- [edit] ---------------------------------- #
    if request.method == 'POST':
        form = QuestionForm(request.POST)
        if form.is_valid():
            question = form.save(commit=False)
            question.create_date = timezone.now()
            question.save()
            return redirect('pybo:index')
    else:
        form = QuestionForm()
    context = {'form': form}
    return render(request, 'pybo/question_form.html', context)
# ---------------------------------------------------------------------------- #
```
가장 눈에 띄는 부분은 동일한 URL 요청을 POST, GET 요청 방식에 따라 다르게 처리한 부분이다. 질문 목록 화면에서 <질문 등록하기> 버튼을 누르면 /pybo/question/create/가 GET 방식으로 요청되어 질문 등록 화면이 나타나고, 질문 등록 화면에서 입력값을 채우고 <저장하기> 버튼을 누르면 /pybo/question/create/가 POST 방식으로 요청되어 데이터가 저장된다.

그리고 QuestionForm 객체도 GET 방식과 POST 방식일 경우 다르게 생성한 것에 주목하자. GET 방식의 경우 QuestionForm()과 같이 입력값 없이 객체를 생성했고 POST 방식의 경우에는 QuestionForm(request.POST)처럼 화면에서 전달받은 데이터로 폼의 값이 채워지도록 객체를 생성했다. form.is_valid 함수는 POST 요청으로 받은 form이 유효한지 검사한다. 폼이 유효하지 않다면 폼에 오류가 저장되어 화면에 전달될 것이다.

그리고 question = form.save(commit=False)는 form으로 Question 모델 데이터를 저장하기 위한 코드이다. 여기서 commit=False는 임시 저장을 의미한다. 즉, 실제 데이터는 아직 저장되지 않은 상태를 말한다. 이렇게 임시 저장을 사용하는 이유는 폼으로 질문 데이터를 저장할 경우 Question 모델의 create_date에 값이 설정되지 않아 오류가 발생하기 때문이다(폼에는 현재 subject, content 필드만 있고 create_date 필드는 없다). 이러한 이유로 임시 저장을 한 후 question 객체를 반환받아 create_date에 값을 설정한 후 question.save()로 실제 저장하는 것이다.

- form.save(commit=False) 대신 form.save()를 수행하면 create_date 속성값이 없다는 오류 메시지가 나타난다.

### [8] 질문 등록 기능 확인하기
웹 브라우저에서 질문 등록 기능을 확인해 보자. /pybo에 접속하여 <질문 등록하기> 버튼을 눌러 질문 등록 화면으로 이동하자.

![](img/2-10_3.png)

웹 브라우저에서 질문 등록 기능을 확인해 보자. /pybo에 접속하여 <질문 등록하기> 버튼을 눌러 질문 등록 화면으로 이동하자.

![](img/2-10_4.png)

[값 입력 후 <저장하기> 버튼 누르기]

![](img/2-10_5.png)

[질문 등록 완료]

### [9] 폼에 부트스트랩 적용하기
여기까지 진행하면 질문 등록 화면에 부트스트랩이 적용되지 않아서 아쉬움이 느껴질 것이다. 그렇다. {{ form.as_p }} 태그는 form 엘리먼트와 입력 항목을 자동으로 생성해 주므로 편리하기는 하지만 부트스트랩을 적용할 수 없다는 단점이 있다. 이 문제를 해결할 수는 없을까? 완벽하지는 않지만, QuestionForm 클래스 내부에 있는 Meta 클래스에 widgets 속성을 다음과 같이 추가하면 이 문제를 해결할 수 있다.

```python
from django import forms
from pybo.models import Question


class QuestionForm(forms.ModelForm):
    class Meta:
        model = Question
        fields = ['subject', 'content']
# ---------------------------------- [edit] ---------------------------------- #
        widgets = {
            'subject': forms.TextInput(attrs={'class': 'form-control'}),
            'content': forms.Textarea(attrs={'class': 'form-control', 'rows': 10}),
        }
# ---------------------------------------------------------------------------- #
```
다시 질문 등록 화면을 요청해 보면 다음과 같이 부트스트랩이 적용된 화면을 볼 수 있다.

![](img/2-10_6.png)

### [10] label 속성 수정하여 Subject, Content 한글로 변경하기
화면의 'Subject', 'Content'를 영문이 아니라 한글로 표시하고 싶다면 label 속성을 지정하면 된다.

```python
from django import forms
from pybo.models import Question


class QuestionForm(forms.ModelForm):
    class Meta:
        model = Question
        fields = ['subject', 'content']
        widgets = {
            'subject': forms.TextInput(attrs={'class': 'form-control'}),
            'content': forms.Textarea(attrs={'class': 'form-control', 'rows': 10}),
        }
# ---------------------------------- [edit] ---------------------------------- #
        labels = {
            'subject': '제목',
            'content': '내용',
        }
# ---------------------------------------------------------------------------- #
```
그러면 'Subject'는 '제목'으로 'Content'는 '내용'으로 변경된다.

![](img/2-10_7.png)

- 장고 폼에 대한 자세한 내용은 장고 공식 문서를 참고하자.
- 장고 공식 문서(폼): docs.djangoproject.com/en/3.0/topics/forms

### [11] 수작업으로 폼 작성하기
{{ form.as_p }}를 사용하면 빠르게 템플릿을 만들 수 있지만 HTML 코드가 자동으로 생성되므로 디자인 측면에서 많은 제한이 생기게 된다. 예를 들어 특정 태그를 추가하거나 필요한 클래스를 추가하는 작업에 제한이 생긴다. 또 디자인 영역과 서버 프로그램 영역이 혼재되어 웹 디자이너와 개발자의 역할을 분리하기도 애매해진다. 이번에는 자동으로 HTML 코드를 생성하지 말고 수작업으로 HTML 코드를 작성해 보자. 우선 forms.py 파일의 widget 항목을 제거하자.

```python
from django import forms
from pybo.models import Question


class QuestionForm(forms.ModelForm):
    class Meta:
        model = Question
        fields = ['subject', 'content']
        labels = {
            'subject': '제목',
            'content': '내용',
        }
# ---------------------------------- [edit] ---------------------------------- #
        # widget 항목 삭제
# ---------------------------------------------------------------------------- #
```
그런 다음 질문 등록 템플릿을 다음과 같이 수정하자.

```python
{% extends 'base.html' %}

{% block content %}
<div class="container">
    <h5 class="my-3 border-bottom pb-2">질문등록</h5>
    <form method="post" class="post-form my-3">
        {% csrf_token %}
<!-- ------------------------------- [edit] -------------------------------- -->
        <!-- 오류표시 Start -->
        {% if form.errors %}
            <div class="alert alert-danger" role="alert">
            {% for field in form %}
                {% if field.errors %}
                <strong>{{ field.label }}</strong>
                {{ field.errors }}
                {% endif %}
            {% endfor %}
            </div>
        {% endif %}
        <!-- 오류표시 End -->
        <div class="form-group">
            <label for="subject">제목</label>
            <input type="text" class="form-control" name="subject" id="subject"
                   value="{{ form.subject.value|default_if_none:'' }}">
        </div>
        <div class="form-group">
            <label for="content">내용</label>
            <textarea class="form-control" name="content"
                      id="content" rows="10">{{ form.content.value|default_if_none:'' }}</textarea>
        </div>
<!-- ----------------------------------------------------------------------- -->
        <button type="submit" class="btn btn-primary">저장하기</button>
    </form>
</div>
{% endblock %}
```
{{ form.as_p }}에 의해 자동 생성되는 HTML 대신 제목과 내용을 위한 HTML을 직접 작성했다. 그리고 question_create 함수에서 form.is_valid()가 실패했을 때 오류를 표시하기 위해 오류 표시 영역도 추가했다. 제목의 value에는 {{ form.subject.value|default_if_none:'' }}을 대입했는데, 이는 오류 발생 시 기존 입력값을 유지하기 위함이다. |default_if_none:''는 form.subject.value에 값이 없으면 'None'이라는 문자열이 표시되는데, 이를 공백으로 표시하기 위해 사용한 템플릿 필터이다. 수정 후 질문 등록 화면으로 돌아가 제목만 입력하고 <저장하기> 버튼을 누르면 다음 화면을 볼 수 있다.

![](img/2-10_8.png)

필수 항목인 내용을 입력하지 않았으니 '내용을 입력하라'는 오류 메시지를 볼 수 있다. 또한 오류가 발생해도 이미 입력한 제목에 해당되는 값은 value 설정으로 인해 그대로 유지되는 것도 확인할 수 있다.

## 답변 등록 기능에 장고 폼 적용하기
### [1] AnswerForm 클래스 추가하고 answer_create 함수 수정하기
질문 등록 기능에 장고 폼을 적용한 것처럼 답변 등록 기능에도 장고 폼을 적용하자. 답변을 등록할 때 사용할 AnswerForm 클래스를 pybo/forms.py 파일에 다음과 같이 작성하자.

```python
from django import forms
# ---------------------------------- [edit] ---------------------------------- #
from pybo.models import Question, Answer
# ---------------------------------------------------------------------------- #

(... 생략 ...)

# ---------------------------------- [edit] ---------------------------------- #
class AnswerForm(forms.ModelForm):
    class Meta:
        model = Answer
        fields = ['content']
        labels = {
            'content': '답변내용',
        }
# ---------------------------------------------------------------------------- #
```
그런 다음 pybo/views.py 파일의 answer_create 함수를 수정하자. answer_create 함수는 question_create 함수와 거의 동일하므로 자세한 설명은 생략한다.

```python
(... 생략 ...)
# ---------------------------------- [edit] ---------------------------------- #
from .forms import QuestionForm, AnswerForm
# ---------------------------------------------------------------------------- #
(... 생략 ...)

def answer_create(request, question_id):
    """
    pybo 답변등록
    """
    question = get_object_or_404(Question, pk=question_id)
# ---------------------------------- [edit] ---------------------------------- #
    if request.method == "POST":
        form = AnswerForm(request.POST)
        if form.is_valid():
            answer = form.save(commit=False)
            answer.create_date = timezone.now()
            answer.question = question
            answer.save()
            return redirect('pybo:detail', question_id=question.id)
    else:
        form = AnswerForm()
    context = {'question': question, 'form': form}
    return render(request, 'pybo/question_detail.html', context)
# ---------------------------------------------------------------------------- #
```
### [2] 질문 상세 템플릿에 오류 표시 영역 추가하기
질문 상세 템플릿에 오류 표시 영역을 추가하자.

```python
(... 생략 ...)
<form action="{% url 'pybo:answer_create' question.id %}" method="post" class="my-3">
    {% csrf_token %}
<!-- ------------------------------- [edit] -------------------------------- -->
    {% if form.errors %}
    <div class="alert alert-danger" role="alert">
    {% for field in form %}
        {% if field.errors %}
        <strong>{{ field.label }}</strong>
        {{ field.errors }}
        {% endif %}
    {% endfor %}
    </div>
    {% endif %}
<!-- ----------------------------------------------------------------------- -->
    (... 생략 ...)
</form>
(... 생략 ...)
```
이렇게 수정하고 답변 내용 없이 답변을 등록하려고 하면 오류 메시지가 그림처럼 나타난다.

![](img/2-10_9.png)
