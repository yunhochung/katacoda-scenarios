## 2.1 실습 소스 다운로드

`\rm -rf hedera-hashgraph && git clone https://github.com/yunhochung/hedera-hashgraph.git `{{execute}}

`cd hedera-hashgraph/hedera-token-service `{{execute}}

`ls -a `{{execute}}

## 2.2 Account 정보 설정

IDE 탭을 선택한 후 .env 파일을 오픈합니다. ***인터넷/PC 환경에 따라 IDE(VS Code) 로딩 시간이 1~2분 소요될 수 있습니다.***

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/20.png)

* 로딩 후 초기 화면

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hedera-token-service/images/1.png)

`.env `{{open}}

.env 파일에 [Step 1]에 복사해 놓은 Account 정보를 설정합니다.

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/5.png)

## 2.3 Node.js 패키지(라이브러리) 설치

실습에 필요한 패키지를 설치합니다.

* Hedera SDK 라이브러리 다운로드

`npm install --save @hashgraph/sdk `{{execute}}

* 유틸리티(js-joda, dotenv)  라이브러리 다운로드

`npm install --save js-joda dotenv `{{execute}}