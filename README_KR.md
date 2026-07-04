# Mossverse (Mossland Metaverse)

> 🇺🇸 For the English notice, see [README.md](./README.md).

> [!WARNING]
> **이 저장소는 더 이상 유지보수되지 않는 보관용(deprecated) 저장소입니다.**
>
> **`meta.moss.land`** 에서 운영되던 초기 **모스버스(Mossverse)** 메타버스 코드입니다 — 자체 제작 클라이언트 스택(Nx 모노레포, React + three.js 렌더러, NestJS 백엔드, Luniverse/Klaytn 블록체인 연동).
>
> 현재 모스버스는 **[WorkAdventure](https://workadventu.re/)** 기반으로 새로 구축되어 **[`wa.moss.land`](https://wa.moss.land)** 에서 운영되고 있습니다.
>
> - 🗺️ 현재 월드 및 맵 소스: **[MosslandOpenDevs/mossverse-wa-map](https://github.com/MosslandOpenDevs/mossverse-wa-map)**
>
> 아래 내용은 히스토리 참고용으로만 보존되며, 현재 운영 중인 서비스와는 무관합니다.

모스랜드의 메타버스 프로젝트 ‘모스버스’ Repository 입니다. 모스랜드(Mossland)는 현실과 가상 세계를 잇는 블록체인 기반 메타버스 프로젝트로 초연결 세상의 구현을 추구합니다.
모스버스는 오픈소스로 개발되고 있으며 누구나 아이디어 제안과 개발에 참여할 수 있습니다.

## 모스버스 개요

유저는 모스버스 내에서 제공되는 다양한 콘텐츠를 통해 Point(PT)를 쌓고 점수에 따라 리워드를 얻습니다. 리워드는 NFT(Non-fungible Token)과 MetaMOC(MM)이 될 예정입니다.

- 화폐 시스템: 화폐는 Point (PT)와 MetaMOC (MM) 두 종류가 제공됩니다.
  - Point (PT): 매주 월요일 0점으로 리셋되는 점수로 게임을 통해 점수를 쌓을 수 있습니다.
  - MetaMOC (MM): MOC와 1:1 교환되는 메타버스내의 가상 통화입니다.
    
- 유저 인증 시스템: 메타마스크를 통한 로그인을 지원합니다.
    - 메타마스크의 Ethereum 체인이 아니라 Luniverse 체인을 연동한 상태여야 합니다.
    - 로그인시 자동으로 Luniverse Address를 ID로 DB에 사용자 등록합니다.
    
- 유저 프로필 페이지
  - Kaikas 지갑 연동: Luniverse 주소 하나당 Klaytn 주소 하나를 맵핑 시킬 수 있습니다.
  - 닉네임 변경 등 기본적인 유저정보 관리 기능을 제공합니다.
  
- 메타버스 공간에서의 건물: 메타버스 다양한 기능은 건물로 구현됩니다.
  - 투표소: Mossland DAO의 투표기능이 구현된 건물입니다.
    - 투표 리스트 및 상세 보기
      - 마감된 투표와 예정된 투표, 진행중인 투표 리스트 뷰
      - 마감된 투표와 예정된 투표, 진행중인 투표의 상세 내용 보는 뷰
      - 마감된 투표는 마감되었다고 뜨고, 결과 공시 상태인 투표는 결과 공시 뷰가 떠야합니다.
    - 투표 참여 기능
      - 지갑에 MOC 소유 여부 확인
      - MOC 소유 수량에 따라 행사하는 투표수 차별
      - 연동된 Metamask 지갑으로 루니버스 체인에 올라간 투표 컨트랙에 투표 함수 호출하여 투표

  - 마켓 플레이스: 유저가 가상의 재화를 구매하거나 거래하는 건물입니다.
    - Exchange: MM과 MOC를 교환
      - 출금: 사용자가 가진 MM을 차감하고 사용자의 Luniverse 지갑으로 MOC 출금
      - 입금: MOC를 입금하면 MM을 충전
    - Purchase: MM으로 기프티콘과 NFT를 구매
      - 기프티콘
      - NFT
        - Luniverse NFT
        - Klaytn NFT: Klaytn NFT는 Klaytn 지갑 주소를 연동한 사용자만 구매 가능
    - Airdrop: 이벤트성 에어드롭을 받을 수 있는 곳
      - Luniverse NFT 드롭 요청
      - Klaytn NFT 드롭 요청
      
  - NFT P2P 마켓플레이스: 유저들간 P2P NFT거래가 일어나는 건물로 결제 화폐는 MM 입니다.
    - 판매 등록: Klaytn, Luniverse NFT를 판매 등록
    - 구매
    
- Dapp (Mini-game): 메타버스 내의 다양한 콘텐츠는 Dapp (Mini-game)으로 구현되며 메타버스 내의 건물로 표현됩니다.
  - 모스버스 해커톤을 통해 모스버스 안에 다양한 콘텐츠를 오픈소스로 개발하고 공급하는 것이 목표입니다. 해커톤은 공개된 GitHub Repository에서 진행되며 누구나 아이디어를 제안하고 개발에 참여할 수 있습니다. [GitHub - mossland/Hackathon](https://github.com/mossland/Hackathon)
  - 게임이 추가될 때마다 건물이 하나씩 생깁니다. 
  - 게임의 결과에 따라 사용자에게 PT를 적립해 줍니다.

- 인벤토리 시스템: ERC-20, 휘발성포인트, 내부 재화 기능

![image](https://user-images.githubusercontent.com/38033515/182839903-560fdbe9-d146-480d-8298-e6a5d4d2fe25.png)

![image](https://user-images.githubusercontent.com/38033515/182496602-1d910539-8e58-4d5a-8a2e-e2381e4b2625.png)


## Architecture

### MonoRepo

![image](https://user-images.githubusercontent.com/4978617/183641614-2a5562a6-1bf3-48c5-b04a-a38a00984628.png)


## 모스버스 개발 마일스톤
(2022년 8월 9일 개발 현황)
| Type | Name | Date |
| - | - | - |
| Task | 모스코인 재화 | August 4, 2022 |
| Sub Task | 모스코인 연동 아이템 | August 4, 2022 | 
| Dev Ticket | 관리자 페이지에서 모스코인 아이템 추가 | August 4, 2022 |
| Dev Ticket | client 모스코인 아이템 불러오기 | August 4, 2022 | 
| Sub Task | 메타버스내 재화 아이템 | August 4, 2022 | 
| Dev Ticket | 관리자 페이지에서 메타모스코인 아이템 추가 | August 4, 2022 | 
| Dev Ticket | client 메타모스코인 아이템 불러오기 | August 4, 2022 | 
| Task | 포인트 시스템 | August 4, 2022 | 
| Sub Task | 포인트 기능 추가 | August 4, 2022 | 
| Dev Ticket | 관리자 페이지에서 포인트 아이템 추가 | August 4, 2022 | 
| Dev Ticket | client 모스코인 포인트 아이템 불러오기 | August 4, 2022 | 
| Sub Task | 포인트 초기화 | August 12, 2022 | 
| Dev Ticket | 일주일 지나면 포인트 초기화 하는 batch 생성 | August 12, 2022 | 
| Sub Task | 포인트 보상 시스템 | August 12, 2022 | 
| Dev Ticket | 게임 완료시 포인트 리렌더 | August 12, 2022 | 
| Task | 로그인 시스템 | August 12, 2022 | 
| Sub Task | 메타마스크 luniverse 로그인 | August 12, 2022 | 
| Dev Ticket | 메타마스크 luniverse 네트워크 확인 | August 12, 2022 | 
| Dev Ticket | 메타마스크 luniverse  연동 | August 12, 2022 | 
| Task | 프로필 | August 19, 2022 | 
| Sub Task | 프로필 인터페이스 구현 | August 19, 2022 | 
| Dev Ticket | 프로필 UI 구현 | August 19, 2022 | 
| Dev Ticket | 오픈 프로필 UI 구현 | August 19, 2022 | 
| Sub Task | 카이카스 지갑 연동 | August 19, 2022 | 
| Dev Ticket | 카이카스 지갑 추가 UI 구현 | August 19, 2022 | 
| Dev Ticket | 카이카스 지갑 추가 기능 구현 | August 19, 2022 | 
| Sub Task | 닉네임 변경 | August 19, 2022 | 
| Dev Ticket | 닉네임 변경 기능 구현 | August 19, 2022 | 
| Dev Ticket | 닉네임 변경시 재화 소모? | August 19, 2022 | 
| Dev Ticket | 닉네임 변경 UI 구현 | August 19, 2022 | 
| Task | 투표소 | August 19, 2022 | 
| Dev Ticket | 웹뷰 띄우기 | August 19, 2022 | 
| Dev Ticket | 투표 기능 연동 | August 12, 2022 | 
| Dev Ticket | 투표소 별도 페이지 구현 | August 12, 2022 | 
| Dev Ticket | 투표 리스트 단순 뷰 구현 | August 12, 2022 | 
| Dev Ticket | 투표 상세 정보 뷰 UI 구현 | August 12, 2022 | 
| Dev Ticket | 투표하기 기능 구현 | August 12, 2022 | 
| Task | 환전소 | August 19, 2022 | 
| Sub Task | 코인 환전 기능 | August 19, 2022 | 
| Dev Ticket | 모스코인 저금 컨트랙 작성 | August 19, 2022 | 
| Dev Ticket | 넣은만큼 게임내 컨트랙 재화 지금 | August 19, 2022 | 
| Sub Task | 상품 구매 기능 | August 19, 2022 | 
| Sub Task | 유저간 토큰 거래 기능 | August 19, 2022 | 


# MosslandMetaverse

This project was generated using [Nx](https://nx.dev).

<p style="text-align: center;"><img src="https://raw.githubusercontent.com/nrwl/nx/master/images/nx-logo.png" width="450"></p>

🔎 **Smart, Fast and Extensible Build System**

## Adding capabilities to your workspace

Nx supports many plugins which add capabilities for developing different types of applications and different tools.

These capabilities include generating applications, libraries, etc as well as the devtools to test, and build projects as well.

Below are our core plugins:

- [React](https://reactjs.org)
  - `npm install --save-dev @nrwl/react`
- Web (no framework frontends)
  - `npm install --save-dev @nrwl/web`
- [Angular](https://angular.io)
  - `npm install --save-dev @nrwl/angular`
- [Nest](https://nestjs.com)
  - `npm install --save-dev @nrwl/nest`
- [Express](https://expressjs.com)
  - `npm install --save-dev @nrwl/express`
- [Node](https://nodejs.org)
  - `npm install --save-dev @nrwl/node`

There are also many [community plugins](https://nx.dev/community) you could add.

## Generate an application

Run `nx g @nrwl/react:app my-app` to generate an application.

> You can use any of the plugins above to generate applications as well.

When using Nx, you can create multiple applications and libraries in the same workspace.

## Generate a library

Run `nx g @nrwl/react:lib my-lib` to generate a library.

> You can also use any of the plugins above to generate libraries as well.

Libraries are shareable across libraries and applications. They can be imported from `@mossland-metaverse/mylib`.

## Development server

Run `nx serve my-app` for a dev server. Navigate to http://localhost:4200/. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `nx g @nrwl/react:component my-component --project=my-app` to generate a new component.

## Build

Run `nx build my-app` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `nx test my-app` to execute the unit tests via [Jest](https://jestjs.io).

Run `nx affected:test` to execute the unit tests affected by a change.

## Running end-to-end tests

Run `nx e2e my-app` to execute the end-to-end tests via [Cypress](https://www.cypress.io).

Run `nx affected:e2e` to execute the end-to-end tests affected by a change.

## Understand your workspace

Run `nx graph` to see a diagram of the dependencies of your projects.

## Further help

Visit the [Nx Documentation](https://nx.dev) to learn more.



## ☁ Nx Cloud

### Distributed Computation Caching & Distributed Task Execution

<p style="text-align: center;"><img src="https://raw.githubusercontent.com/nrwl/nx/master/images/nx-cloud-card.png"></p>

Nx Cloud pairs with Nx in order to enable you to build and test code more rapidly, by up to 10 times. Even teams that are new to Nx can connect to Nx Cloud and start saving time instantly.

Teams using Nx gain the advantage of building full-stack applications with their preferred framework alongside Nx’s advanced code generation and project dependency graph, plus a unified experience for both frontend and backend developers.

Visit [Nx Cloud](https://nx.app/) to learn more.
