## 2.1 데모 소스 다운로드

`\rm -rf hedera-hts-demo && git clone https://github.com/yunhochung/hedera-hts-demo.git `{{execute}}

`cd hedera-hts-demo `{{execute}}

`cp .env.sample .env `{{execute}}

`ls -a `{{execute}}

## 2.2 Account 정보 설정

IDE 탭을 선택한 후 .env 파일을 오픈합니다. ***인터넷/PC 환경에 따라 IDE(VS Code) 로딩 시간이 1~2분 소요될 수 있습니다.***

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/getting-started-with-hashgraph/images/20.png)

* 로딩 후 초기 화면

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/1.png)

`.env `{{open}}

.env 파일에 [Step 1]에 복사해 놓은 Account와 Network 정보를 설정합니다.

* VUE_APP_OPERATOR_ID: Account ID
* VUE_APP_OPERATOR_KEY: Private Key
* VUE_APP_NETWORK: http://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com

![1](https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/2.png)

## 2.3 빌드 & 실행

* 빌드 - 빌드 시간이 수분에서 10분이상 소요됩니다.

`docker-compose build `{{execute}}

* 실행

`docker-compose up `{{execute}}

## 2.4 UI 접속

https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com