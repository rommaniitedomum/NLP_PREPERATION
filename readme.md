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
