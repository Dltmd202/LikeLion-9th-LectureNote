# 👨🏽‍💻14주차!

## 14.1 배포 사전준비

### 14.1.1 환경변수

* 시스템에 저장되어 있는 변수
* 보통 비밀키 등 유출되면 안되는 정보
* 또는 환경에 차이를 둘 때 사용
* os.environ 에서 dict 형식으로 불러올 수 있다.
* os.environ.get('변수명', '기본값')



### 14.1.2 requirements

* 내 파이썬 앱을 실행하기 위해 설치되어야 하는 패키지들
* Django, Pillow 등
* 패치지명 == 버전으로 저장
* 보통 requirement.txt 파일에 저장
* pip freeze 명령어는 해당 환경에 설치된 모든 패키지를 보여줌
* \> 는 프로그램의 출력을 파일에 저장한다는 뜻
* Pip freeze \> requirements.txt로 생성



### 14.1.3 IAM

* Identity and Access Management의 줄임말
* IAM에서 계정을 만든 후 해당 계정 로그인 정보(엑세스 키 & 시크릿 키)를 이용하여 AWS의 API활용
* 보안을 위해 권한을 최대한 보수적으로 잡음



## 14.1.4 S3

* Simple Stroge Service의 줄임말
* AWS에서 제공하는 구글드라이브 정도
* 최초 용량 지정 없이 사용한 만큼만 과금되므로 용량 예측 필요 x
* 여러 서버에서 동시에 접속 가능 (부하 분산 유리)

## 14.1.4 S3

settings.py

```python
SECRET_KET = os.environ.get('비밀키')
DEFAULT_FILE_STORAGE = 'storages.backends.s3boto3.S3Boto3Storage'

AWS_ACCESS_KEY_ID = '아이디'
AWS_SECRET_ACCESS_KEY = '접근 코드'
AWS_STORAGE_BUCKET_NAME = '버킷이름'
AWS_S3_SIGNATURE_VERSION = "s3v4"
AWS_S3_REGION_NAME = "ap-northeast-2"
AWS_S3_CUSTOM_DOMAIN = ""
```

terminal

```bash
pip install django-storges
pip install boto3
pip freeze > requirements.txt
```

