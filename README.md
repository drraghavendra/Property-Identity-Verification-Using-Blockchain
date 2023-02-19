# Property-Identity-Verification-Using-Blockchain

<a href="LICENSE"><img src="https://img.shields.io/static/v1?label=license&message=MIT&color=green"></a>
<img src="https://img.shields.io/badge/Ethereum-20232A?style=for-the-badge&logo=ethereum&logoColor=white">
<img src="https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white">
## Land Registration using Blockchain
## Problem it Solves:
   Real Estate industry is a very big and complex industry for any person. This situation happens due to factors like number of paper work, frauds, money laundering and generation of black money. Registration and real estate deals take days to months to years to settle. This can cause a huge inconvinience to any individual. We abstract those tedious process and provide safe and secure environment for users to connect and offer deals with potential buyers without worrying about any paperwork. We store everything on chain and therefore there is perfect data integrity and transparency.
Real Estate inndustry is also a major black money generator industry. Due to low transparency and intermediatary involvement, a large sum of black money cashflows in the market and therefore affecting the nations economy. We tried to minimize that possibility by implmenting on chain communication using Push and on chain dealing so that transparency is maintained and no funny business can be hidden from the eyes of governing bodies.

Challenges I ran into

Polygon ID
We needed to build a custom issuer portal so that an authority (say government) can issue claims for their holders and send them via email or any other communicating medium. The process up till creation of the issuerID and schema was relatively easier but we faced a lot of difficulty implementing the Verifier contract (ref. ERC20Verifier contract according to the polygon ID docs) on-chain.
The smart contracts were quite difficult to understand and relied on a number of local imports. Due to which usage of the smart contract was difficult and required a lot of effort to fork it. Finally, we could create a basic working model and generate claims. This was like an achievement for our whole team.

Gnosis Safe
We thought of implementing Gnosis Safe for renting purposes. The idea was when a person wants to rent a Real Estate Property, the owner can transfer the property to the safe and give credentials to the tenant as well. As it is in the Safe both the users and the tenant can leverage the benefits of the NFTs. We faced issues while implementing the Module and Guard smart contract. The docs for Gnosis Safe felt insufficient for a newcomer like myself. It is very high in complexity and a better documented procedure could have helped a lot. I was able to connect to the Safe SDK and create a Safe for myself but the later steps were quite challenging for me.
We implemented the contract system using the wallet address but that was not completely enough to validate the user on organization point of view. So for a general validation of user introduced Soul Bond Token(SBT). Which gives a new form of digital identity to all users. Soul bond tokens are Non Transferable erc-721 token which solidifies the ownership of the contract. Integration sbt in the pre made contract was a huge challenge we ran into. Due to which all my transaction was getting reverted. After struggling with it we found that at one place _uri was define as string and other it was defined as memory (array).
Debugging and validating the smart contract is itself a tedious process of deploying and testing everytime we make any change. To overcome this issue we started using tenderly by forking a polygon


1. The elimination of middlemen: The elimination of middlemen or brokers makes the process of land registration less expensive. Brokers who try to defraud uninformed people will be unable to do so any longer. Brokers frequently take a long time to finish procedures, thus our project will help people save time.
3. A distributed tamper-proof ledger that prohibits ownership fraud.
4. IPFS is used to store important property registration papers in a secure manner.

## Technology Stack:
1. Ethereum Blockchain
2. Polygon/Matic
3. Web3Dart
4. IPFS
5. Flutter
6. Metamask

## Demo
Our Dapp is demonstrated in this video [here](https://youtu.be/0Coz_ivOaHs)

## Run Application on deployed website
Check out the deployed website [here](https://landregistry.live/)

https://landregistry.live/

This is for demonstration purposes only. With this key, you can log in as Land Inspector:
 <pre><b>6b86cddfedbec68ed2a1c7e14b993840a0848595ba5787aec9e8a38b18f0d96a</b></pre>
For user: <pre><b>3ed4aff1a8ff8e28df3cd307112f9166886edcc85a27136908e3b1687b111f89</b></pre>\
You can also use your own Ethereum wallet key as a user.

#### Check new Smart contract At Polygon Testnet: [here](https://mumbai.polygonscan.com/address/0xbc6d9e15255533C19f1589A7e9fbB60440a539e0)

#### Check Smart contract At (discontinued) Ropsten Ethereum Testnet: [here](https://ropsten.etherscan.io/address/0x702058ba021cd4e4f847b40f32b58aa5be3a4661)

## To Run Application Locally
1. Clone the github repository and cd to the folder
2. Install the flutter 3.0.2, nodejs
3. Install ganache and truffle as shown below:
```
npm install -g truffle
```
4. Open Ganache and keep it running in the Background
5. Install the Metamask chrome extension, choose the local network and import the accounts
6. Compile and run our migrations from the command line as shown below:
```
truffle compile
truffle migrate
```
6 .Copy contract address as seen in the image below and paste in variable `contractAddress` located in the file `./lib/constant/constant.dart`
<pre>
2_deploy_migration.js
=====================

   Replacing 'Land'
   ----------------
   > transaction hash:    0x427b2b402f767ac6a90334ab3c687b086b274de747fe10d6e194743b15057d78
   > Blocks: 0            Seconds: 0
   <b>>contract address:    0xed690C24C60A48F8A9819c9A15AD75B70CFBEa5a</b>
   > block number:        3
   > block timestamp:     1650602828
   > account:             0x33e94e4619f0AecDf81e9676Eb82c109FBa53356
   > balance:             99.9154895
   > gas used:            3996227
   > gas price:           20 gwei
   > value sent:          0 ETH
   > total cost:          0.07992454 ETH
</pre>
7. In `constant.dart` file, change the value of the variable `chainId` to `'1337'` and change the value of the variable `rpcUrl` to `"http://127.0.0.1:7545"`
8. Run the flutter web app
```
flutter pub get

flutter run -d web-server --web-port 5555
```
9. Open the browser and the dapp will be running in http://localhost:5555/
10. Create mapbox api key from https://www.mapbox.com/ and Replace it with `mapBoxApiKey`in `constant.dart` file
## Project Flowchart
<img src="screenshots/flowchart.png" height="450">

## Screenshots
Home Page                   |                   Wallet connect/Login
:---------------------------------:        |      :------------------------------:
<img src="screenshots/Screenshot1.png" height="225">  |<img src="screenshots/Screenshot7.png" height="225">

Contract Owner Dashboard               |                   User Registration
:---------------------------------:        |      :------------------------------:
<img src="screenshots/Screenshot10.png" height="225">  |<img src="screenshots/Screenshot12.png" height="225">

Land Inspector Dashboard                   |                  User Verification 
:---------------------------------:        |      :------------------------------:
<img src="screenshots/Screenshot11.png" height="225">     |<img src="screenshots/Screenshot5.png" height="225">

User Dashboard               |                  Adding land on Map    
:---------------------------------:        |      :------------------------------:
<img src="screenshots/Screenshot2.png" height="225">     |<img src="screenshots/Screenshot8.png" height="225">

Land Gallery                |                   Land Details    
:---------------------------------:        |      :------------------------------:
<img src="screenshots/Screenshot3.png" height="225">     |<img src="screenshots/Screenshot9.png" height="225">

Received Request           |                   Make Payment  
:---------------------------------:        |      :------------------------------:
<img src="screenshots/Screenshot6.png" height="225">     |<img src="screenshots/Screenshot4.png" height="225">

Transfer ownership,Seller,buyer photo capture   |                Witness info,photo capture,transfer ownership 
:---------------------------------:        |      :------------------------------:
<img src="screenshots/Screenshot14.png" height="225">     |<img src="screenshots/Screenshot13.png" height="225">
