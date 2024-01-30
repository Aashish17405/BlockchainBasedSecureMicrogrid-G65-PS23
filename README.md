
# Cyber security enabled smart control for grid connected microgrid

Our innovation integrates a user-friendly website for seamless microgrid element access,a robust blockchain infrastructure for secure data storage and an advanced simulator to replicate and analyze the dynamic microgrid setup.

## Aim
Aim of the project is to develop a cybersecurity-enabled smart controller for grid- connected microgrids. The smart controller will play a crucial role in ensuring the secure and efficient operation of the microgrid by:

- Securing communication between the smart controller and other components within the microgrid using robust encryption protocols.

- Creating an access control mechanism to regulate user access based on roles and privileges.

- Developing a logging system to track all activities.

- Developing a user-friendly interface for the smart controller to enable efficient monitoring,configuration,and management of the microgrid's cybersecurity settings.

## Prerequisites

Before running the project, ensure you have the following prerequisites in place:

Install Geth: Visit [Geth](https://geth.ethereum.org/docs/getting-started/installing-geth) Installation and follow the instructions to install Geth on your PC.
Install Nodejs: Visit [Nodejs](https://nodejs.org/en/download) Installation and follow the instructions to install Nodejs on your PC.
Create an Account in [Twilio](https://www.twilio.com/login) for the OTP verification feature. This usually includes your email address, password, and account type.

### Commands to run the project
#### Blockchain
To create nodes, use the following command:
```bash
geth --datadir "./data" account new
```
To create bootnode
```bash
bootnode -genkey { NAME_OF_THE_KEY }.key
```
To start bootnode
```bash
bootnode -nodekey { KEY_NAME } -verbosity 7 -addr "127.0.0.1:30301"
```
To start Node1
```bash
geth --datadir "./data"  --port 30304 --bootnodes enode://{ YOUR_VALUE } --authrpc.port 8547 --ipcdisable --allow-insecure-unlock  --http --http.corsdomain="https://remix.ethereum.org" --http.api web3,eth,debug,personal,net --networkid { NETWORK_ID } --unlock { ADDRESS_NODE1 } --password { PASSWORD_FILE_NAME_EXTENSION }  --mine --miner.etherbase= { SIGNER_ADDRESS }
```
To start node2
```bash
geth --datadir "./data"  --port 30306 --bootnodes enode://{ YOUR_VALUE }  -authrpc.port 8546 --networkid { NETWORK_ID } --unlock { ADDRESS_NODE2 } --password { PASSWORD_FILE_WITH_EXTENSION }
```
####  Simulator
To install the libraries in python run this command in the command prompt or powershell.
```bash
pip install {library_name}
```

#### React App
This project was bootstrapped with Create React App.
To create a new React application,run this command in the powershell or command prompt. Note that you need to have Nodejs installed in your pc.
```bash
npx create-react-app my-react-app
```
To install any library in the application
```bash
npm install {library_name}
```
To run the application
In the project directory, you can run:
```bash
npm start
```
The command runs the app in the development mode.Open http://localhost:3000 to view it in your browser.
The page will reload when you make changes.
You may also see any lint errors in the console.
To run the backend server,just run the backend python code.


## Tech stack
- Frontend
    - React 
    - Bootstrap
    - CSS
- Backend
    - Flask
    - Twilio
    - Python
- Database
    - mongoDB

We used python to simulate the microgrid setup and a private blockchain based on Go Ethereum for secure and decentralized data storage and transactions.

![Screenshot 2024-01-23 233943](https://github.com/Aashish17405/cybersite/assets/140961189/73fae3d3-5207-48a2-8e77-0f93a3fb32f4)
## Frontend
### React App
The webiste provides three different user interfaces for three different hierachial roles namely Power system operator,Data analyst and microgrid consumer.The login page is common for everyone and they get redirected to their respective pages just as they enter their username,password and OTP which is sent to their registered mobile number.Anyone who wants to register as a new user should send a feedback through the ContactUs page.

##### Power System Operators
Their responsibilities include ensuring a harmonious balance between power supply and demand. With elevated privileges,Power System Operators can not only oversee the microgrid elements but also play a pivotal role in shaping the system's dynamics. Their dashboard provides a comprehensive set of features,including the ability to register new users,update genset costs for efficient budget management,and access detailed graphical representations of microgrid elements. These visualizations empower Power System Operators with valuable insights for making informed decisions and maintaining optimal grid performance.

##### Data Analysts
Data Analysts bring their analytical prowess to the platform,extracting valuable insights from the extensive data generated by different components of the microgrid. Their dashboard provides graphical information about various components of the microgrid.
##### Microgrid Consumers
For Microgrid Consumers,the platform offers a user-friendly interface tailored to their consumption needs. They can easily access information related to their individual microgrid consumption patterns in the form of graph and table,enabling them to make informed decisions about their energy usage. The interface provides insights into energy consumption trends,empowering consumers to contribute to a more sustainable and efficient energy ecosystem.
[Prerequisite Code](#react-app)

### Workflow of React App
![Screenshot 2024-01-23 234550](https://github.com/Aashish17405/cybersite/assets/140961189/1794602c-8581-4243-98c2-c83fae7f289c)

## Backend
### Blockchain
We used a private blockchain based on Go-Ethereum for secure and 
decentralized data storage and transactions. These are the commands we used to create a blockchain using Go-Ethereum.

The components within the microgrid ecosystem dynamically engage with the smart contract embedded in the blockchain,facilitating secure and transparent transactions to persistently store data. This mechanism ensures the integrity of the stored information,guarding against any potential tampering or unauthorized alterations. The interaction is made using the we3.py python library.
[Prerequisite Code](#blockchain)

### Simulator
We used python to simulate the micgrogrid setup. To mimic a smartcontroller of a microgrid,we used a flask server which takes inputs and sends the commands to the elements of the microgrid.All microgrid communication with the smart controller is secured through encryption,implemented using the [cryptography.fernet](https://cryptography.io/en/latest/fernet/) Python library. A key is used to create a "Fernet" cipher suite. There are functions encrypt_message and decrypt_message that use the cipher suite to encrypt and decrypt messages,respectively. Fernet is a simple symmetric encryption algorithm that provides a high level of security and is suitable for encrypting small pieces of data,such as tokens or messages. Important info about the performance of the elements is stored in the blockchain so that this info can't be tampered. To get this functionality we used [web3.py](https://web3py.readthedocs.io/en/stable/) Python library. web3.py allows us to interact with the Ethereum blockchain and build applications that leverage blockchain functionalities.
[Prerequisite Code](#simulator)
### Workflow of Simulator
![Screenshot 2024-01-23 232829](https://github.com/Aashish17405/cybersite/assets/140961189/6d44b7de-d418-43b0-b0f9-146b73b25220)


## Contributors
Aashish [@Aashish17405](https://github.com/Aashish17405)

Rahul [@kotterahul](https://github.com/kotterahul)

Saranya [@leelasaranyaM](https://github.com/leelasaranyaM)

Anjali [@anjalikavade](https://github.com/anjalikavade)

Amog [@Ahealier](https://github.com/heailer)

Sai Krishna [@Saikrishna200501](https://github.com/Saikrishna200501)