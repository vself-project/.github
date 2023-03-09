# vSelf Project

![](https://testnet.vself.app/vself.jpg)

## Navigation

1. vSelf smart contracts [vseld-dao](https://github.com/vself-project/vself-dao)
2. vSelf web application and API endpoints [vself-beta](https://github.com/vself-project/vself-beta)
3. vSelf npm package based on zero-knowledge proofs [vstudio-metabuild](https://github.com/vself-project/vstudio-metabuild)
5. vSelf referance documentation [vseld-dao](https://github.com/vself-project/vself-dao)

## Deployment 

### Staging (Testnet)

- [vSelf web application](https://testnet.vself.app)
- [vSelf event smart contract](https://explorer.testnet.near.org/accounts/events_v22.sergantche.testnet) deployed at events_v29.sergantche.testnet
- [vSelf community smart contract](https://explorer.testnet.near.org/accounts/communities_v6.sergantche.testnet) deployed at communities_v6.sergantche.testnet

### Production (Mainnet)

- [vSelf web application](https://vself.app)
- [vSelf smart-contract](https://explorer.near.org/accounts/v3.event.vself.near) deployed at v3.event.vself.near

### Mobile 
- [App Store](https://apps.apple.com/us/app/vself/id1631569446)
- [Google Play](https://play.google.com/store/apps/details?id=com.VSelf.vselfapp&gl=US)

### vSelf zkp SDK
[vSelf npm package](https://www.npmjs.com/package/@vself_project/shared-utils)

npm i @vself_project/shared-utils

```js
mimc_hash(bigint left, bigint right) => Commitment
prove_mimc_preimage(bigint secret, bigint salt) => Proof
verify_mimc_preimage(Commitment c, Proof p) => bool
prove_set_membership(Vec<Commitment> set, bigint secret, bigint salt) => MembershipProof
verify_set_membership(Vec<Commitment> set, MembershipProof p) => bool
```

- [vSelf API](http://vself-prod.web.app/api/)

### Documentation
- [Architecture overview](https://vself-project.gitbook.io/vself-project-documentation/v/technical-overview/)
- [Functionality](https://vself-project.gitbook.io/vself-project-documentation/)
- [Instructions](https://vself-project.gitbook.io/vself-project-documentation/v/instructions/)
- [Architecture model](https://github.com/vself-project/vself-dao/tree/master/docs)

## Functionality

vSelf application allows to:
- [Onboarding](https://vself-prod.web.app/onboard)  
- Creation of the custom [collection with SBT](https://vself-prod.web.app/add) rewards, distribution rewards trough [web app](https://vself-prod.web.app/dashboard) using claim link or trough mobile ([iOS](https://apps.apple.com/us/app/vself/id1631569446) & [Androind](https://play.google.com/store/apps/details?id=com.VSelf.vselfapp&gl=US))
app using QR-code, [analytics](https://vself-prod.web.app/dashboard) 
- [User profile](https://vself-prod.web.app/vranda) with on-chain data storage
- [Community toolkit](https://vself-prod.web.app/vstudio) with zero-knowledge proofs membership protection

## Design Rationale

Self-soveregnity and level of decentralization of the current generation of dApps are highly questionable, as Moxie Marlinspike has brilliantly demonstrated in [his piece](https://moxie.org/2022/01/07/web3-first-impressions.html). Many Web3 infrastructures are either prone to cancel culture or are politically centralized. The most successful dApp is still Satoshi's network, with others like Ethereum / Polkadot / NEAR building up momentum towards sovereignty and adoption.

Below you can see a birds eye view on the whole vSelf system:

1. (People) Community governance / legal => controls vSelf DAO and source code
1. (Law) vSelf DAO contracts / documents => controls operational expenses, controls cloud setup
1. (DevOps) vSelf Cloud => hosts vSelf services, delivers vSelf App
1. (UI/UX) vSelf App => stores personal data and creates user experience

This is probably the most generic setup for any dApp. In the beginning operational and tech desicionss are full responsibility of vSelf top level management, but this approach allows us to gradually evolve toward more political decentralization. as it allow us to make this DAO future compatible. We also understand that we have to be fully opensource and open to public scrutinity.

The other important part which is our adherence to open standarts and guidlines developed by international community of experts. That's why we look closely at DID and VC data models, which we use and adapt for our specific use cases.

## Blueprints

As we have already discussed what vSelf might look like eventually, in this section we will present our specific tech choices for the first product we are going to deliver. There are several resons and premises we based our architecture and tech choices off, let's see some. As we progress with design at every stage we try to keep it simple and rely only on open source software.

The main risk we want to avoid is dependence on service providers who can disrupt or censor our services for some reason without our consent. So we made particular choices for our codebase and tech stack to mitigate this kind of threat.

1. For the source of truth and governance / economic layer we have chosen NEAR technology as it's the best in class of carbon neutral scalable proof-of-stake blockchain.
1. For the communication layer AND database solution we chose to use GunDB peer-to-peer graph database.
1. For the large objects storage we are going to integrate different solutions (Google Storage, NEAR.Machina, Filecoin, Swarm).
1. Open source tech like Kubernetes + Docker is used for the cloud orchestration.

As we need to host our cloud services somewhere we currently use GCloud which poses kind of deplatforming threat. This can be addressed by incentivisation of cloud infrastructure providers and as well as making our cloud include more hosting providers with time.

Our codebase is stored on GitHub, and consists of the following:

- Cloud configuration, design documentation
- vSelf smart contracts (business logic)
- vSelf tooling (CLI) + TS/JS SDK for application developers
- vSelf progressiwe web application / identity wallet / API service (Next.js + tRPC)
- Dockerized vSelf node which contains proxy logic:
  1. DID and verifiable credentials registry
  1. GUN database / OrbitDB storage instances

![](https://testnet.vself.app/system.png)

![](https://testnet.vself.app/legend.png)

ZKP technology is an ivaluable buiding block for self-sovereign identity and we have been developing some practical applications of this tech. We are looking for the solution of proof-of-set-membership implementations. Our first iteration uses Bulletproofs which is well established zk-proof system without trusted setup (compared to some zkSNARKs). On top of Bulletproofs we build our R1CS circuit to prove set membership in zero-knowledge, so on-chain data doesn't reveal members identity. This is quite experimental and uses MiMC hash under the hood (as it has low multiplicative complexity and simple rust implementation). For the hash function we plan to consider modern ZK-friendly ones such as popular Poseidon and Reinforced Concrete (based on lookup arguments). For a constanst size accumulator we have options to explore in the near future: replacing explicit membership set with Merkle tree root (or even Verkle tree root). As for the proof system we consider Halo2 (zCash) also Bulletproof-based one, for even shorter proofs and lower verification costs.
