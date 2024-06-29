# vSelf 
### We help brands turn customers into loyal vibrant community

<img width="1150" alt="Screenshot 2024-06-29 at 21 34 54" src="https://github.com/vself-project/.github/assets/8280427/0ea40aed-58ae-489a-9a09-bc5f6fc862db">


## Overview
vSelf is a Web3 Community-as-a-Service platform with tools to boost engagement and p2p interaction. It helps brands host and tokenize their communities on Telegram and socials, unifying omnichannel interaction and bringing zero-party data to one place. vSelf provides gamification tools for exciting user quests, improved retention, and first-hand performance analytics.

Key features:

- **Customizable Campaign Management:** Clients can set up and customize their gamified campaigns through vSelf, and engage directly with their communities hosted on platforms like Telegram and other social media channels.
- **Interactive Tools:** The platform includes tools to construct engaging mini-games, quizzes, and tokenized rewards, creating a dynamic and exciting community experience.
- **Integrated CRM:** Under the hood, a powerful CRM system allows businesses to gather and analyze information, improving data integrity and targeting precision.
- **Native Telegram Integration:** One of the key focuses is Telegram, where the majority of community management functions are integrated into a single bot. This simplifies the interface between users and the platform, enhancing user experience and engagement.

## Functionality
- Creation of the custom [campaigns with SBT or NFT rewards on TON, NEAR, or Camino networks](https://vself.app/collection/create), distribution rewards through 
web app using claim link or QR-code, engagement analytics
- Telegram [vSelf Bot](https://t.me/vself_bot)
-  Web3 user profile with on-chain data statistics
- [Community toolkit](https://vself.app/vstudio) with zero-knowledge proofs for membership protection
- vSelf for brands: setting up [Camino SBT giveaways](https://brands.vself.app/add) and distribution rewards through [web app](https://brands.vself.app/dashboard)
- NEAR [onboarding](https://vself-prod.web.app/onboard)  

## Repositories

- vSelf smart contracts [vseld-dao](https://github.com/vself-project/vself-dao)
- vSelf web application & API endpoints [vself-beta](https://github.com/vself-project/vself-beta)
- vSelf npm package based on zero-knowledge proofs [vstudio-metabuild](https://github.com/vself-project/vstudio-metabuild)
- vSelf web application for brands [vself-brands](https://github.com/vself-project/vself-brands)

## Documentation
- [Architecture overview](https://vself-project.gitbook.io/vself-project-documentation/v/technical-overview/architecture)
- [Functionality](https://vself-project.gitbook.io/vself-project-documentation/)
- [Instructions](https://vself-project.gitbook.io/vself-project-documentation/v/instructions/)
- [Architecture model](https://github.com/vself-project/docs)

## User flow

### SBT collections & Web3 profiles
![](https://github.com/vself-project/docs/blob/main/UserFlowEvents.png)

### Referral campaigns with SBTs
![](https://github.com/vself-project/docs/blob/main/424.png)

### Zero-knowledge onboarding
![](https://github.com/vself-project/docs/blob/main/UserFlowZKP.png)


## Deployment 

### Development (NEAR Testnet)

- [vSelf web application](https://testnet.vself.app)
- [vSelf event smart contract](https://explorer.testnet.near.org/accounts/events_v33.sergantche.testnet) deployed at events_v33.sergantche.testnet
- [vSelf community smart contract](https://explorer.testnet.near.org/accounts/communities_v6.sergantche.testnet) deployed at communities_v6.sergantche.testnet

###  Staging (NEAR Mainnet)

- [vSelf web application](https://staging.vself.app/)
- [vSelf event smart contract](https://nearblocks.io/address/v4.event.vself.near) deployed at v4.event.vself.near
- [vSelf community smart contract](https://nearblocks.io/address/communities_v1.sergantche_dev.near) deployed at communities_v1.sergantche_dev.near

### Production (NEAR Mainnet)

- [vSelf web application](https://vself.app)
- [vSelf event smart contract](https://nearblocks.io/address/v4.event.vself.near) deployed at v4.event.vself.near
- [vSelf community smart contract](https://nearblocks.io/address/communities_v1.sergantche_dev.near) deployed at communities_v1.sergantche_dev.near

### Staging (Columbus Testnet)
- [vSelf web application](https://brands.vself.app/)
- [vSelf giveaway smart contract](https://suite.camino.network/explorer/columbus/c-chain/address/0x37d0924289a66687d7624963aa4f4bc2da1af36e)

### Mobile apps
- [App Store](https://apps.apple.com/us/app/vself/id1631569446)
- [Google Play](https://play.google.com/store/apps/details?id=com.VSelf.vselfapp&gl=US)

### vSelf zkp SDK for proof-of-membership
Package is availible at [npm registry](https://www.npmjs.com/package/@vself_project/shared-utils).

```js
npm install @vself_project/shared-utils
```

```js
mimc_hash(bigint left, bigint right) => Commitment
prove_set_membership(Vec<Commitment> set, bigint secret, bigint salt) => MembershipProof
verify_set_membership(Vec<Commitment> set, MembershipProof p) => bool
```
### vSelf API endpoints for SBT events

Mints SBT & returns reward metadata in JSON
```
https://vself-prod.web.app/api/checkin?eventid='0000000000'&nearid='alice.near'&qr='test_string'
```
View event & returns event metadata in JSON
```
http://vself-prod.web.app/api/event?eventid='0000000000'
```
View all upcomming events from white list in JSON
```
http://vself-prod.web.app/api/events
```

## System architecture
Here is the layers of vSelf system architecture.
Full description of used components is available:
- [Architecture overview](https://vself-project.gitbook.io/vself-project-documentation/v/technical-overview/architecture)
- [MVP architecture](https://vself-project.gitbook.io/vself-project-documentation/v/technical-overview/)
- [C4 model](https://github.com/vself-project/docs#vself-architecture-c4-model)

![](https://github.com/vself-project/docs/blob/main/architecture-short.png)


## Achievements 

- vSelf is Zero Knowledge Base Camp participant, Outlier Venture 2023.
- MVP on TON mainnet is supported by TON acceleration program (Q1 2024).
- Prototype was supported by NEAR Foundation grant and is live on the NEAR mainnet.
- Partnered with 25 Web3 projects and issued 7500+ SBTs in pilot collaborations.
- vSelf team won the Best Design Prize at MetaBUILD 2022 Hackathon & Bounty Prize NEARCON 2022 Hackathon.



## Social media

info@vself.app

[Telergam](https://t.me/vselfmeta)

[Linkedin](https://www.linkedin.com/company/vself/)

[Twitter](https://twitter.com/vself_meta)

[Medium](https://medium.com/@vSelf_Project)

[Instagram](https://www.instagram.com/vself_meta/)
