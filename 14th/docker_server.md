# 👨🏽‍💻14주차!

## 14.6 Docker 배포하기

### 14.5.1 Docker Setting

1. Docker 설치

   `curl -fsSL https://get.docker.com | bash`

2. Docker Compose 설치

   `sudo curl -L "https://github.com/docker/compose/releases/download/1.28.5/docker -compose -$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`

   `sudo chmod +x /usr/local/bin/docker-compose`

3. 앱 설치 폴더 지정

   `sudo mkdir /opt/[AppName]`

   `cd /opt/[AppName]`

4. docker-compose.yml 생성

   `vi docker-compose.yml`

   ![스크린샷 2021-07-12 오후 6.00.48](/Users/mac/Library/Application Support/typora-user-images/스크린샷 2021-07-12 오후 6.00.48.png)

* 저 내용을 그대로 터미널에 복사 붙여넣기 할 경우 문제 발생 가능
  * 따라서 pastebin.com 등의 서비스에 업로드 후 wget 사용 추천
  * `sudo wget https://pastbin.com/raw/[wget 주소]`
* .env 파일 생성

```
DB_NAME = []
DB_USER = []
DB_PASSWARD = []
DEBUG = False
```

5. DB 최초 생성

`sudo docker -compoase up db`

6. 작동 테스트

`sudo docker -compose up`

7. 백그라운드 모드로 전환

`sudo docker -compose up -d`

