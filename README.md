# [Fracctal Monsters #ALGO](https://twitter.com/fracctal_nft) [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social&logo=twitter)](https://twitter.com/fracctal_nft)

![fracctal_monsters](https://user-images.githubusercontent.com/3107701/142519398-a9388acc-6ce0-4143-916c-396d313b7c1d.gif)


Fracctal Monsters sets out to be an advanced monster taming game on the Algorand blockchain. 
 
As a monster taming game, you will need to feed and take care of your pet for it to grow and evolve. An unhappy fracctal monster will not grow into it's next form.

The site's frontend is built with Angular with a NodeJS backend. The full game will be built within the Unity game engine, with an ASP.NET backend. 

## Road Map
![roadmap](https://user-images.githubusercontent.com/3107701/142560234-11e05fcb-a637-485c-8dba-f70f82a94722.JPG)


## Quick start

Quick start options:

## Terminal Commands
Angular
1. Install NodeJs from [NodeJs Official Page](https://nodejs.org/en).
2. Open Terminal
3. Go to your file project
4. Run in terminal: ```npm install -g @angular/cli```
5. Then: ```npm install```
6. And: ```ng serve```
7. Navigate to: [http://localhost:4200/](http://localhost:4200/)

Node Server
1. Run in terminal: ```node app.js```

Known Issue #1: 

Issue with MyAlgo Wallet and Webpack. 
You must add "window.Buffer = window.Buffer || require('buffer').Buffer" to /node_modules/@randlabs/myalgo-connect/lib/main.js.
![image](https://user-images.githubusercontent.com/3107701/143340800-afa41e1c-1d67-490a-8fff-3f5ed95814a0.png)

Known Issue #2: 

You may have issues with write permissions. In this case, make sure to create a folder called static in the root directory, with a subfolder called contracts. This is where smart contracts are created and referrenced by the backend. 

![image](https://user-images.githubusercontent.com/3107701/143508067-acd0f5f6-992a-4715-80ff-1a31d9ac9b11.png)


## Algo Test Environment
This project relies on the MyAlgo Connect API

You will want at least two TestNet wallet accounts for testing buying/opening packs
https://wallet.myalgo.com/access

Once you have created at least two TestNet wallets, you will want to fund them using the following service:
https://bank.testnet.algorand.network/

Use one of the TestNet wallets as the "Dev" account in which you can mint packs. 

Step 1: Using a TestNet wallet, mint an NFT which represents a pack

Unit Name should be fracpack in order to show up on dashboard
![image](https://user-images.githubusercontent.com/3107701/143321299-a6e4d70d-70d1-4ae5-906e-48c261e062e5.png)

Step 2: Mint a few NFT monsters using the same minting tool. 
Unit Name should include FM0 to show up on the dashboard (example: FM00001) 

Step 3: Setup backend code  to point to your new pack and dev test account. This should be done with a config file later. 
\smartcontracts\limitorder.js
Line 39 (add Dev Account Secret Phrase) 
Line 58 (add Asset ID of created Pack) 

buy_nft_packs.component.ts
Line 47 (add Asset ID of created Pack) 

Step 4: Logout of your current "Dev" TestNet account, and login another TestNet Wallet. Ensure only one wallet is selected at a time.
![image](https://user-images.githubusercontent.com/3107701/143320615-d71ca274-4f37-492c-8261-19f73035da33.png)

Step 5: 
Buy a pack, navigate to the dashboard, find your pack, then click "Open Pack". 
The backend will check the available pool of monsters from your dev account to transfer to the buyer account opening the pack. 
During this process, the selected Monser is transfered to an escrow account. The buyer will then send the payment to the escrow account, the escrow account will use a smart contract to make sure everything is correct, and if so, sends the monster NFT to the buyer, and the payment to the Dev creator account. 
![image](https://user-images.githubusercontent.com/3107701/143321633-88432ba9-2e37-452b-979c-deda77e08620.png)
Success Pack Opened
![image](https://user-images.githubusercontent.com/3107701/143321913-5c259628-b3eb-412b-9db9-f43439705547.png)


## License

https://github.com/Fraccas/FracctalMonsters/blob/main/LICENSE
