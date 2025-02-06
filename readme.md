# 자연어 처리 코랩 to 주피터 변환

- 코랩환경: 리눅스의 활용도가 높음

- jupyter: vscode 로 window/ 리눅스 둘다 활용 가능
  ; 이중 window 설정 실행

1.  selenium 설치 ( JAVA ,크로마 db, 크롬드라이버 설치 )

        - linux: # %%bash (코랩 환경)

        # apt-get update

        # apt-get install g++ openjdk-8-jdk python-dev python3-dev

        # pip3 install JPype1

        # pip3 install konlpy

        # import sys

        # !sudo add-apt-repository ppa:saiarcot895/chromium-beta

        # !sudo apt remove chromium-browser

        # !sudo snap remove chromium

        # !sudo apt install chromium-browser

        # !pip3 install selenium

        # !apt-get update

        # !apt install chromium-chromedriver

        # !cp /usr/lib/chromium-browser/chromedriver /usr/bin/

        1. -1 윈도우 : 직접 들어가서 설치 / 환경 변수 편집 필수

        사용데이터: 백석, 김수영 시집



        2.  리눅스 selenium 설정:
            ##Selenium 관련 환경 설정

        # import time

        # import selenium

        # from selenium import webdriver as driver

        # from selenium.webdriver.common.by import By

        # from selenium.webdriver.chrome.service import Service

        # from selenium.webdriver.support import expected_conditions as EC

        # # 인터넷 창이 안 뜨고 웹과 연결,

        # options = webdriver.ChromeOptions()

        # # 웹과 코랩 연동을 수월하게 하기 위해 보안을 약하게 만드는 코드.

        # options.add_argument("--headless")

        # options.add_argument("--no-sandbox")

        # # 공유 메모리를 \dev\shm 디렉터리를 사용하지 않고 바로 연결.

        # options.add_argument("disable-dev-shm-usage")

        # webdriver_service = Service("C\WebDriver\chromedriver")

        # driver = webdriver.Chrome(service=webdriver_service, options = options)

        2. -2 윈도우 selenium 설정

        ##Selenium 관련 환경 설정

        import time
        import selenium
        from selenium import webdriver
        from selenium.webdriver.common.by import By
        from selenium.webdriver.chrome.service import Service
        from selenium.webdriver.chrome.options import Options

        # 웹 크롤링(web crawling, 웹의 정보를 자동화된 방법으로 탐색하는 것)을 위한 크롬 드라이버 설정 코드이다.

        chromedriver_path = "C:/WebDriver/chromedriver.exe"

        # 인터넷 창이 안 뜨고 웹과 연결,

        options = webdriver.ChromeOptions()

        # 웹과 코랩 연동을 수월하게 하기 위해 보안을 약하게 만드는 코드.

        options.add_argument("--headless")
        options.add_argument("--no-sandbox")

        # 공유 메모리를 \dev\shm 디렉터리를 사용하지 않고 바로 연결.

        options.add_argument("disable-dev-shm-usage")

        # 크롬 드라이버를 실행하면 코랩과 웹이 연결.

        webdriver_service = Service(chromedriver_path)
        driver = webdriver.Chrome(service=webdriver_service, options=options)

## 데이터 평가: colab 과 jupyter 간의 로딩 차이는 존재하지만 큰 정확도 차이는 없음

---

2~3장 클래스 분류 / 문서 분류

분류법 : 기존의 데이터 분석과 크게 다를것 없음

나이브 베이지안 이산분류 : 확률 기반 분류;-> 빠르고 효율적이나 단어 상관관계가 없음
( 스팸 필터링, 감성 분석(긍정/부정), 주제 분류 같은 곳에 활용)

로지스틱 회귀 : 확률값 예측;-> 텍스트 기반 예측 모델(시그모이드 함수의 0~1사잇값)
(비선형 데이터는 성능이 떨어짐, 다중 클래스 분류에 추가 기법 필요(ex:소프트맥스))

라쏘 회귀 : L1 정규화를 추가한 선형 회귀(불필요한 특성을 제거함);-> 특정 단어의 가중치를 0으로 만듬 , 효과적인 과적합 방지
(단어가 많으면 가중치가 과도하게 떨어짐)

결정 트리 : 데이터를 여러 규칙으로 분할해 예측하는 모델 ;-> 어지간하면 잘나옴(과적합 가능성)
-> 텍스트 기반 질의응답 문서/ 문서 카테고리 분류 /챗봇의 의사 결정 시스템 영향 끼침

사용 가능성 ->

로지스틱 회귀

- 언어는 결정 트리

  +나이브 베이지안은 모르겠음?(쓸지를 모르겠음 )
