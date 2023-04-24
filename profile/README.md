# vSelf 
### We help brands turn customers into loyal vibrant community

![](https://testnet.vself.app/vself.jpg)

## Overview
vSelf is Web3 platform for growth hacking and community engagement.

We are focused on Community-as-a-Service tools witch creates a trustful interaction channel between organizations and their customers. vSelf provides brands with easy-to-use toolkit to leverage Web3 data and elevate loyalty programs, customer relationship management, and digital marketing. 

Our solution includes a Web3 studio, which allows companies to issue and manage collections of digital certificates (SBTs and verifiable credentials) and an identity application for users to create their Web3 personas. vSelf makes next-generation community engagement accessible to a general audience. 

## Functionality

- NEAR [onboarding](https://vself-prod.web.app/onboard)  
- Creation of the custom [collection with SBT](https://vself-prod.web.app/add) rewards, distribution rewards through [web app](https://vself-prod.web.app/dashboard) using claim link or through mobile ([iOS](https://apps.apple.com/us/app/vself/id1631569446) & [Androind](https://play.google.com/store/apps/details?id=com.VSelf.vselfapp&gl=US))
app using QR-code, engagement [analytics](https://vself-prod.web.app/dashboard)
- [Web3 user profile](https://vself-prod.web.app/vranda) with on-chain data storage
- [Community toolkit](https://vself-prod.web.app/vstudio) with zero-knowledge proofs for membership protection


## Navigation

- vSelf smart contracts repo [vseld-dao](https://github.com/vself-project/vself-dao)
- vSelf web application & API endpoints for events repo [vself-beta](https://github.com/vself-project/vself-beta)
- vSelf npm package based on zero-knowledge proofs repo [vstudio-metabuild](https://github.com/vself-project/vstudio-metabuild)

## Documentation
- [Architecture overview](https://vself-project.gitbook.io/vself-project-documentation/v/technical-overview/architecture)
- [Functionality](https://vself-project.gitbook.io/vself-project-documentation/)
- [Instructions](https://vself-project.gitbook.io/vself-project-documentation/v/instructions/)
- [Architecture model](https://github.com/vself-project/docs)

## User flow
![](https://github.com/vself-project/docs/blob/main/238.png)


## Deployment 

### Staging (Testnet)

- [vSelf web application](https://testnet.vself.app)
- [vSelf event smart contract](https://explorer.testnet.near.org/accounts/events_v22.sergantche.testnet) deployed at events_v29.sergantche.testnet
- [vSelf community smart contract](https://explorer.testnet.near.org/accounts/communities_v6.sergantche.testnet) deployed at communities_v6.sergantche.testnet

### Production (Mainnet)

- [vSelf web application](https://vself.app)
- [vSelf event smart contract](https://explorer.near.org/accounts/v3.event.vself.near) deployed at v3.event.vself.near
- [vSelf community smart contract](https://explorer.near.org/accounts/communities_v1.sergantche_dev.near) deployed at communities_v1.sergantche_dev.near

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
- MVP got supported by NEAR Foundation grant and is live on the NEAR mainnet.
- Partnered with 25 Web3 projects and issued 7500+ SBTs in pilot collaborations.
- vSelf team won the Best Design Prize at MetaBUILD 2022 Hackathon & Bounty Prize NEARCON 2022 Hackathon



## Social media

info@vself.app

[Telergam](https://t.me/vself_townhall)

[Linkedin](https://www.linkedin.com/company/vself/)

[Twitter](https://twitter.com/vself_meta)


