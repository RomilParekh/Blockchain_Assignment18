# Blockchain_Assignment18
For this assignment we are required to work of proof of Authority algorithm. It requires pre-approvals of existing blocks in the network to approve a new transaction. 

Required steps. 
Step 1:
Generate 2 nodes for the above mentioned with 2 new addresses that will serve the required purpose of approvals of transactions. 
 

![image](https://user-images.githubusercontent.com/87787282/145321349-baa7c005-b385-4f6c-96eb-c19293343209.png)






Node 1: 
Password: Romil123
Public address of the key:   0x248CB1343cE922cd2496340f2cD06DaafCAE848f
Path of the secret key file: node1\keystore\UTC--2021-12-08T23-37-42.656352300Z--248cb1343ce922cd2496340f2cd06daafcae848f 
Node 2:
Password: Romil1234
Public address of the key:   0x683311540C19b16c269bC2DE77b3A798Dd3024Ec
Path of the secret key file: node2\keystore\UTC--2021-12-08T23-38-40.832394900Z--683311540c19b16c269bc2de77b3a798dd3024ec Step 2:  
./puppeth

Network Name: fintechhomework

parek@DESKTOP-63ROJEI MINGW64 ~/Downloads/FinTech-Lesson-Assignments/BlockChain-Tools
$ ./puppeth
+-----------------------------------------------------------+
| Welcome to puppeth, your Ethereum private network manager |
|                                                           |
| This tool lets you create a new Ethereum network down to  |
| the genesis block, bootnodes, miners and ethstats servers |
| without the hassle that it would normally entail.         |
|                                                           |
| Puppeth uses SSH to dial in to remote servers, and builds |
| its network components out of Docker containers using the |
| docker-compose toolset.                                   |
+-----------------------------------------------------------+

Please specify a network name to administer (no spaces, hyphens or capital letters please)
> fintechhomework

Sweet, you can set this via --network=fintechhomework next time!

←[32mINFO ←[0m[12-08|17:39:34.800] Administering Ethereum network           ←[32mname←[0m=fintechhomework
←[33mWARN ←[0m[12-08|17:39:34.801] No previous configurations found         ←[33mpath←[0m=C:\\Users\\parek\\.puppeth\\fintechhomework

What would you like to do? (default = stats)
 1. Show network stats
 2. Configure new genesis
 3. Track new remote server
 4. Deploy network components
> 2

What would you like to do? (default = create)
 1. Create new genesis from scratch
 2. Import already existing genesis
> 1

Which consensus engine to use? (default = clique)
 1. Ethash - proof-of-work
 2. Clique - proof-of-authority
> 2

How many seconds should blocks take? (default = 15)
> 10

Which accounts are allowed to seal? (mandatory at least one)
> 0x248CB1343cE922cd2496340f2cD06DaafCAE848f
> 0x

Which accounts should be pre-funded? (advisable at least one)
> 0x683311540C19b16c269bC2DE77b3A798Dd3024Ec
> 0x

Should the precompile-addresses (0x1 .. 0xff) be pre-funded with 1 wei? (advisable yes)
>

Specify your chain/network ID if you want an explicit one (default = random)
> 665
←[32mINFO ←[0m[12-08|17:41:55.214] Configured new genesis block

What would you like to do? (default = stats)
 1. Show network stats
 2. Manage existing genesis
 3. Track new remote server
 4. Deploy network components
> 2

 1. Modify existing configurations
 2. Export genesis configurations
 3. Remove genesis configuration
> 2

Which folder to save the genesis specs into? (default = current)
  Will create fintechhomework.json, fintechhomework-aleth.json, fintechhomework-harmony.json, fintechhomework-parity.json
>
←[32mINFO ←[0m[12-08|17:43:30.856] Saved native genesis chain spec          ←[32mpath←[0m=fintechhomework.json
←[31mERROR←[0m[12-08|17:43:30.857] Failed to create Aleth chain spec        ←[31merr←[0m="unsupported consensus engine"
←[31mERROR←[0m[12-08|17:43:30.857] Failed to create Parity chain spec       ←[31merr←[0m="unsupported consensus engine"
←[32mINFO ←[0m[12-08|17:43:30.859] Saved genesis chain spec                 ←[32mclient←[0m=harmony ←[32mpath←[0m=fintechhomework-harmony.json

What would you like to do? (default = stats)
 1. Show network stats
 2. Manage existing genesis
 3. Track new remote server
 4. Deploy network components


![image](https://user-images.githubusercontent.com/87787282/145322541-9b1ac7e8-8dc9-4794-ac05-ef749f82a469.png)

 


In a new GIT bash window initialize the  nodes:
./geth --datadir node1 init fintechhomework.json
./geth --datadir node2 init fintechhomework.json


 
![image](https://user-images.githubusercontent.com/87787282/145322558-c159ea9c-9d32-40e5-b893-0196ed1eb0cb.png)





Start mining
Another new GITBASH window is needed for it.
Use command: 
./geth --datadir node1 --mine -minerthreads 1
 
![image](https://user-images.githubusercontent.com/87787282/145322741-300d5bcc-6298-4126-94d5-ceedaf50ad31.png)


Copy 
enode://b73f8f24e9c016707118f8838c2b56499d3a7c7fbf4f34bdbc216d1a04340baaef7c768da0dc93783adcdca2076d1f9cad3ffcb1eb75aa10665009e7aeef958b@127.0.0.1:30303

Open another gitbash window for final step: 

./geth --datadir node2 --port 30304 --rpc --bootnodes "enode://b73f8f24e9c016707118f8838c2b56499d3a7c7fbf4f34bdbc216d1a04340baaef7c768da0dc93783adcdca2076d1f9cad3ffcb1eb75aa10665009e7aeef958b@127.0.0.1:30303" –ipcdisable

 
![image](https://user-images.githubusercontent.com/87787282/145322766-96df22ac-a88d-4363-bcea-9e00e3526bdb.png)



Go to MyCrypto App 

And Configure the custom Network

 


![image](https://user-images.githubusercontent.com/87787282/145322962-5f6c066d-83aa-42a6-ab01-5a6678b28a00.png)








Go to view and send 
Select nmenoic phrase and select the phrase from the account 

![image](https://user-images.githubusercontent.com/87787282/145322796-5ce81073-a52d-44fd-8bb0-81dae01e344c.png)

 

Do the same for the other account as well & initiate transaction

 ![image](https://user-images.githubusercontent.com/87787282/145322843-23c71229-e46c-4db9-b839-9cbf1e2a00c6.png)


Check the hash 

![image](https://user-images.githubusercontent.com/87787282/145322862-db78c86b-2bc0-4146-a855-0c9d064aaf29.png)

 


Transaction complete

![image](https://user-images.githubusercontent.com/87787282/145323068-bd4c6593-481a-43b4-a81b-775266f097e5.png)

 
