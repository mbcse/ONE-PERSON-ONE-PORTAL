# ONE-PERSON-ONE-PORTAL

Testnet Used:

Testrpc
	– This is a local network running on your compuetr. 10 free wallet
	accounts with test ether is allocated. 

Wallet

Wallets are very
important part of a smart contract. It serves 2 purposes:

- It serves as
	client to ethereum wallet. To make a transaction on network ether
	has to be spent and you can authorize these payments using this. 
- To
	communicate with a blockchain and to deploy, you need to either have
	a full node or a wallet cleint of the network.  A wallet can
	facilitate the communication with the network. 
Note: We have used testrpc which provides us with 10 free accounts with their private keys and 100 ethers are linked to each account.It is these accounts which we are using for transaction. Tp run it go to : cmd/testrpc

Deployment

To deploy a contract
the following steps are to be taken:

- Compile the
	code and get necessary bytecodes and ABIcodes
- Select a
	network to migrate to 
- Make a
	deployment with a wallet address as transaction sender 
- Authenticate
	the transaction form the wallet and pay the transaction cost. 

Your contract will
be deployed and will be assigned a public address which can be used
to access it.

Web
Interface

A web app can be
used to work with the contract. A backend  javascript framework,
**web3.js**, can intract with the blockchain. It can connect to
the network, identify the contract and perform transactions. There
are two kinds of transaction operation on a contract:



Web App

1. Open  src/js/app.js file. This is the javascript file
that interacts with the contract.

2. Paste your contract address replacing  'contract_address
in “web3.eth.contract(abi).at('contract_address');

3. Go to remix page.
In the compile section go to details tab. In the ABI
section click on copy button to copy your ABI code.

4. Go to 
src/js/app.js file and paste it replacing abi_array
in   var abi = abi_array ;

5. Open
src/index.html to open the web app.

Interacting
on web App

Fill up the user
details and click add user or add admin. You will find block being created and ether being reduced in remix ide from the account we are using which got 100 free ethers.

In the command window you can see block being created. 

Different Operations In the App

1.Intialising Contract

Output

- msg.sender is made as creatorAdmin
- msg.sender is made as superAdmin
- msg.sender is made as verified user

2.Create a new Property

parameters

- CreateProperty- property Id, propoerty value, property owner address

prerequisites

- msg.sender should be admin
- property owner should be verified user

Output

 mark property Id, Status as Pending, propoerty value, property owner address

3.Approve the new Property.

parameters

- approveProperty- property Id

prerequisites

- msg.sender should be superadmin
- current owner should not be msg.sender

Output

mark property Satus as Approved

4.Reject the new Property.

parameters

- rejectProperty- property Id

prerequisites

- msg.sender should be superadmin
- current owner should not be msg.sender

Output

Mark property Satus as Rejected

5. Request Change of Ownership.

parameters

- changeOwnership- property Id, new owner address

prerequisites

- msg.sender should be the current owner
- new owner should be verified user
- current owner is not the new owner
- No pending ownership change request should exist.

Output

mark property Ownership change request

6.Approve change in Onwership.

parameters

- ApproveChangeOwnership- property Id

prerequisites

- msg.sender should be superadmin
- ownership change request must exist

Output

mark new owner address as current owner

7.Change the price of the property.

parameters

- changeValue- propoerty Id, new property value

prerequisites

- msg.sender should be the current owner
- No pending ownership change request should exist.

Output

change property value

8.Get the property details.

parameters

- GetPropertyDetails- propoerty Id

Output

Status, propoerty value, property owner address

9.Add new user.

parameters

- addNewUser- address

prerequisites

- msg.sender should be admin
- No pending request for the address should exist.(user or admin or superadmin)
- address should not be a verified user.(user or admin or superadmin)

Output
mark address as user

10.Add new admin.

parameters

- AddNewAdmin- address

prerequisites

- msg.sender should be superadmin
- No pending request for the address should exist.(user or admin or superadmin)
- address should not be a verified user.(user or admin or superadmin)

Output

mark address as Admin

11.Add new SuperAdmin

parameters

- addNewSuperAdmin- address

prerequisites

- msg.sender should be superadmin
- No pending request for the address should exist.(user or admin or superadmin)
- address should not be a verified user.(user or admin or superadmin)

Output

mark address as SuperAdmin

12. Approve Pending User.

**parameters**

- approveUsers- address

**prerequisites**

- msg.sender should be superadmin
- Pending request should exist for address

**Output**

mark address as Verified user



