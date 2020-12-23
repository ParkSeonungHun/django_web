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
