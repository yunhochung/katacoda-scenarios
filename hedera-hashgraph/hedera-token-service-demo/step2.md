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

**UI URL - http://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com**

접속 후 초기화 과정이 진행됩니다. (**인터넷/PC 환경에 따라 초기화 시간이 1~10초 소요될 수 있습니다.**)

정상적으로 초기화가 되면 화면 상단에 아래와 같이 3개의 계정(Account)가 생성됩니다.

* 아래 예에서는 0.0.145966(OWNER), 0.0.145967, 0.0.145968 계정이 생성되었습니다.

  *<u>**계정은 화면이 초기화가 될때마다 새로운 값으로 생성됩니다.**</u>*

*<u><img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/3.png" alt="3" style="zoom:50%;" /></u>*

* UI 사용법 동영상 - https://youtu.be/t4FF1iepsYk?t=2713

* ***원활하게 UI 접속 또는 3개의 계정이 생성 되지 않는 경우 아래 URL을 통해서 실습하시면 됩니다.***

  * **http://hts-demo.yhchung.com:8080** 
  
  

화면 우측 상단에 있는 아이콘(메뉴)은 다음과 같은 기능이 있습니다.

* (1) 토큰 생성
* (2) 토큰 생성 마법사
* (3) 트랜잭션 히스토리
* (4) 초기화

<img src="https://github.com/yunhochung/katacoda-scenarios/raw/master/hedera-hashgraph/hedera-token-service-demo/images/4.png" alt="4" style="zoom:50%;" />