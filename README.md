
# 🏛️ Project Vision:

Universities offer the perfect environment for the development and experimentation with DAOs.  The University of British Columbia will use the DAO developed on SKALE for the purposes of managing club activities.  A best practices for DAO management will be a targeted outcome through an iterative process of experimentation, research, and collaboration with existing DAOs 

The best practices will incorporate aspects of DAO technological implementations (backend), user experience (Front end), and DAO use principles.  

The clubs core executive team will remain at a fixed size of 5 for the foreseeable future.  However, numerous subcommittees will be formed to solve specific problems or as a result of club expansion through new hires for example.  It is likely that the development of these subcommittees will result in scenarios of uneven numbers of subcommittee members.  SKALE offers an ideal solution to address these issues throughs it safe random number generator.  For example, in scenarios where the are 4 members on a committee and the vote on an issue results in a stale-mate, i.e. 2 nay and 2 yay votes, the stalemate will be resolved through a coin toss.

Scaffold-Eth allows for the easy onboarding of junior developers in our community to get them hands on experience with building and developing DAOs.  It allows for the quick prototyping of new DAO features on both the front and back-end and the implementation of smart contracts across a range of protocols.  It will play a critical role in onboarding developers from web2 and traditional programming into web3.

The longer term goal of the DAO will be to get buy in from the broader student community outside of the club.  This will be achieved through the demonstrated effectiveness of the DAO in managing our club activities.  TheGraph will be used to examine DAO use and an analysis will be performed to compare DAO outcomes against traditional approaches to governance.  But above this, the sheer success of our club and its likely attribution of that success by our club community to the use of DAOs will be key in getting buy in from the larger student body – in a particular social science students who may dissatisfied with the current approach to running campus wide student elections and governance systems. 

We aim to get students involved in governance decisions for the right reasons, not for the purposes of political prestige. Doing this on campus will ensure the next generation of political leaders will be born  out of the principles of DAO use.

This DAO has also been deployed on Harmony.  One submission can benefit from an ecosystem dedicated to the best use of the core tech of the project (DAOs).  And another submission can benefit from a core tech of an ecosystem which solves a fundamental problem in the use of DAOs.

longer term goals are -  support from protocols in the form of funding rewards for participation in the DAO and contributing to good governance.  Similar to Joseph’s talk the past day where he discussed the prototypical DAO that originated in the coffee shop.  We want to reward students for their engagement, we want to incentive blockchain research by providing grant and funding opportunities that relate to DAO work.  And those funding allocations will be based decisions made by those who have demonstrated expertise in the use of DAOs and participation in their development.  

It may seem like oh you are trying to cover as much breadth as you can, but there is more to it than that.  it comes down to why I was able to cover such breadth, and the reason for this is because I was able to utilize the power of Eth-Scaffold, created by Austin-Griffith.  Using this platform truly does allow for the quick development and prototyping of both back end and front end deck in unified framework.  No jumping from one application to the next to bring your idea to life, it really is all right there!

An additional longer term initiative could be to integrate skales secure randomness into harmony where there has been an concerted effort to support the development of DAOS and there exists a high level of DAO expertise. 

# 🏛 Modifying important files in Scaffold-Eth To Connect with SKALE

1. copy an entry in 



# 🏛️ Simple DAO Description

> Quickly spin up a DAO smart contract where you choose the initial group of members.

![PowDAO Dashboard](https://scaffold-eth-readme-images.s3.amazonaws.com/Screenshot+2022-02-10+174055.png)

## 📘 DAO Specifics

Quickly initiate a DAO by sending an array of address in the constructor of this contract on deploy. DAO proposals can be created by anyone, but only voted on by members. Members can create proposals to add or kick members. Members cannot withdraw their deposited funds once they are deposited. All deposited funds will be used for the good of the DAO.

Public Goods...
This type of DAO can be used by sports teams to pay for field time, equipment, travel, etc. Another use case is for public contruction or maintenance projects. 
A neighborhood/ town/ governoment can deposit a bunch of funds which can be democratically voted on and invoices can be submitted by the contractors.  

## ⭐ Bonus

A re-entrancy proxy contract has been created to verify the security of the PowDAO contract withdraw function. This contract can be found in `packages/hardhat/contracts`. To mimic a re-entrancy attack, uncomment the file in the deploy script `packages\hardhat\deploy\00_deploy_your_contract.js` and uncomment the 2 function calls in the contract itself ('powdao.getPayoutUnsafe(address(this));'). On deploy, this 'attacking' smart contract will create a proposal and if the proposal is approved by DAO members the proposer can withdraw the funds. To create a re-entrancy attack when you are withdrawing your funds, use the 'getPayoutUnsafe' function versus 'getPayout' which does not have the re-entrancy vulnerability. 

Re-entrancy is caused by repeatedly calling the a fallback function in the proxy contracts receive function. This will create a loop which will be executed until it runs out of gas making repeated function calls. Try for yourself!

[Info on Re-Entrancy Attack](https://quantstamp.com/blog/what-is-a-re-entrancy-attack)

## 🏄‍♂️ Quick Start

Prerequisites: [Node](https://nodejs.org/en/download/) plus [Yarn](https://classic.yarnpkg.com/en/docs/install/) and [Git](https://git-scm.com/downloads)

> clone/fork 🏗 scaffold-eth:

```bash
git clone https://github.com/austintgriffith/scaffold-eth.git simple-proposal-DAO-re-entrancy-ex

cd simple-proposal-DAO-re-entrancy-ex

git checkout simple-DAO-proposals
```

> install and start your 👷‍ Hardhat chain:

```bash
cd simple-proposal-DAO-re-entrancy-ex
yarn install
yarn chain
```

> in a second terminal window, start your 📱 frontend:

```bash
cd simple-proposal-DAO-re-entrancy-ex
yarn start
```

> in a third terminal window, 🛰 deploy your contract:

```bash
cd simple-proposal-DAO-re-entrancy-ex
yarn deploy
```

🔏 Edit your smart contract `PowDAO.sol` in `packages/hardhat/contracts`

📝 Edit your frontend `App.jsx` in `packages/react-app/src`

💼 Edit your deployment scripts in `packages/hardhat/deploy`

📱 Open http://localhost:3000 to see the app
