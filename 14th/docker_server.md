# ๐จ๐ฝโ๐ป14์ฃผ์ฐจ!

## 14.6 Docker ๋ฐฐํฌํ๊ธฐ

### 14.5.1 Docker Setting

1. Docker ์ค์น

   `curl -fsSL https://get.docker.com | bash`

2. Docker Compose ์ค์น

   `sudo curl -L "https://github.com/docker/compose/releases/download/1.28.5/docker -compose -$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`

   `sudo chmod +x /usr/local/bin/docker-compose`

3. ์ฑ ์ค์น ํด๋ ์ง์ 

   `sudo mkdir /opt/[AppName]`

   `cd /opt/[AppName]`

4. docker-compose.yml ์์ฑ

   `vi docker-compose.yml`

   ![แแณแแณแแตแซแแฃแบ 2021-07-12 แแฉแแฎ 6.00.48](/Users/mac/Library/Application Support/typora-user-images/แแณแแณแแตแซแแฃแบ 2021-07-12 แแฉแแฎ 6.00.48.png)

* ์  ๋ด์ฉ์ ๊ทธ๋๋ก ํฐ๋ฏธ๋์ ๋ณต์ฌ ๋ถ์ฌ๋ฃ๊ธฐ ํ  ๊ฒฝ์ฐ ๋ฌธ์  ๋ฐ์ ๊ฐ๋ฅ
  * ๋ฐ๋ผ์ pastebin.com ๋ฑ์ ์๋น์ค์ ์๋ก๋ ํ wget ์ฌ์ฉ ์ถ์ฒ
  * `sudo wget https://pastbin.com/raw/[wget ์ฃผ์]`
* .env ํ์ผ ์์ฑ

```
DB_NAME = []
DB_USER = []
DB_PASSWARD = []
DEBUG = False
```

5. DB ์ต์ด ์์ฑ

`sudo docker -compoase up db`

6. ์๋ ํ์คํธ

`sudo docker -compose up`

7. ๋ฐฑ๊ทธ๋ผ์ด๋ ๋ชจ๋๋ก ์ ํ

`sudo docker -compose up -d`

