## 2.1 실습 소스 다운로드

`\rm -rf meetup && git clone https://github.com/hlkug/meetup.git`{{execute}}

`cd meetup/202010/hands-on/getting_started `{{execute}}

`ls `{{execute}}

## 2.2 Account 정보 설정

.env 파일에 [Step 1]에 복사해 놓은 Account 정보를 설정합니다.

`.env `{{open}}

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/getting-started-with-hashgraph/images/5.png)

## 2.3 Node.js 패키지(라이브러리) 설치

VS Code에서 Terminal 창을 오픈한 후 실습에 필요한 패키지를 설치합니다.

* 초기화

`npm init -y `{{execute}}

* Hedera SDK 라이브러리 다운로드

`npm install --save @hashgraph/sdk `{{execute}}

* dotenv 라이브러리 다운로드

`npm install --save dotenv `{{execute}}