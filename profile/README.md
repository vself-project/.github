# vSelf Project

![](https://testnet.vself.app/vself.jpg)

## Navigation

1. vSelf smart contracts [vseld-dao](https://github.com/vself-project/vself-dao)
2. vSelf web application and API endpoints [vself-beta](https://github.com/vself-project/vself-beta)
3. vSelf npm package based on zero-knowledge proofs [vstudio-metabuild](https://github.com/vself-project/vstudio-metabuild)

## Documentation
- [Architecture overview](https://vself-project.gitbook.io/vself-project-documentation/v/technical-overview/)
- [Functionality](https://vself-project.gitbook.io/vself-project-documentation/)
- [Instructions](https://vself-project.gitbook.io/vself-project-documentation/v/instructions/)
- [Architecture model](https://github.com/vself-project/vself-dao/tree/master/docs)

## Deployment 

### Staging (Testnet)

- [vSelf web application](https://testnet.vself.app)
- [vSelf event smart contract](https://explorer.testnet.near.org/accounts/events_v22.sergantche.testnet) deployed at events_v29.sergantche.testnet
- [vSelf community smart contract](https://explorer.testnet.near.org/accounts/communities_v6.sergantche.testnet) deployed at communities_v6.sergantche.testnet

### Production (Mainnet)

- [vSelf web application](https://vself.app)
- [vSelf smart-contract](https://explorer.near.org/accounts/v3.event.vself.near) deployed at v3.event.vself.near

### Mobile apps
- [App Store](https://apps.apple.com/us/app/vself/id1631569446)
- [Google Play](https://play.google.com/store/apps/details?id=com.VSelf.vselfapp&gl=US)

### vSelf zkp SDK for proof-of-membership
[npm package](https://www.npmjs.com/package/@vself_project/shared-utils)
```js
npm install @vself_project/shared-utils
```

```js
mimc_hash(bigint left, bigint right) => Commitment
prove_set_membership(Vec<Commitment> set, bigint secret, bigint salt) => MembershipProof
verify_set_membership(Vec<Commitment> set, MembershipProof p) => bool
```
### vSelf API endpoints for SBT events

Claim SBT
```js
https://vself-prod.web.app/api/checkin?eventid='0000000000'&nearid='alice.testnet'&qr='test_string'
```
Event metadata in JSON
```js
http://vself-dev.web.app/api/event?eventid='0000000000'
```
Upcomming events white list 
```js
http://vself-dev.web.app/api/events
```

## Functionality

vSelf application allows to:
- [Onboarding](https://vself-prod.web.app/onboard)  
- Creation of the custom [collection with SBT](https://vself-prod.web.app/add) rewards, distribution rewards trough [web app](https://vself-prod.web.app/dashboard) using claim link or trough mobile ([iOS](https://apps.apple.com/us/app/vself/id1631569446) & [Androind](https://play.google.com/store/apps/details?id=com.VSelf.vselfapp&gl=US))
app using QR-code, [analytics](https://vself-prod.web.app/dashboard) 
- [User profile](https://vself-prod.web.app/vranda) with on-chain data storage
- [Community toolkit](https://vself-prod.web.app/vstudio) with zero-knowledge proofs membership protection

## Overview

Problem: vSelf focuses on the lack of real ownership and portability of the personal data and credentials for users and the dependence of businesses on big tech companies for data processing. We narrowed down this problem to the inefficiency of particular data pipelines in web3, where we see a gap between issued attributes for digital identities and the ability to utilize them as web3 CV for funding, gated access, or talent acquisition.

Solution: What we propose is an IDaaS platform that allows users to manage their digital provenance on their side, making it composable and portable, and to connect with organizations in a trustful way. Companies, on their side, get a tool to mark any significant event of their interaction with users with a digital certificate and set up incentives.

vSelf is in MVP stage that is live on NEAR mainnet. It is built for the workflow, where each digital certificate has a non-transferable NFT standard.  It has  several key elements:
Web3 Studio - to set up and manage collections of NFT rewards that can be distributed through QR codes or claimable links. 
Identity Wallet - web and mobile applications to collect and manage personal provenance of NFT rewards.
vRanda - public profile, where users can present their digital identity with text description, links, and NFT rewards collections.  
Our goal is to bring the benefits of the blockchain world to the general public and make web3 products more inclusive and user-friendly.  

## Social media

info@vself.app

[Telergam](https://t.me/vself_townhall)

[Linkedin](https://www.linkedin.com/company/vself/)

[Twitter](https://twitter.com/vself_meta)

## System architecture

![](https://github.com/vself-project/docs/blob/main/architecture.png)
