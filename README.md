# SSH-connection
* https://doku.lrz.de/ssh-tutorial-10746941.html
* ref https://smarty.userweb.mwn.de/movies/Firstlogin.mp4
## first connecetion
* imagine you want to work on a remotely located server, by yourlaptop or PC **securely** trhough the network. that is you want to sent Commands trhough the network to that Machine and receive back the results of the command.to do so you need to have few things:
* 1- you and the remote machine must bu connected to network.
* 2- SSH client on your laptop or PC. on most machines Open_SSH is available from the terminal.
* 3- the remote machine must have a **Running SSH_Server** .
* 4- credential --> userID and Password
* 5- the name of the machine --> 1xlogin.lrz.de or (IP : 129.187.20.101)
### check the version of the ssh in client machine:
* --> **ssh -V**
* it will show the version of the ssh client on your laptop. the more recent the version the better. for example mine is as follow:
  - (base) shahram@shahram-X556UB:~$ ssh -V
  - OpenSSH_9.6p1 Ubuntu-3ubuntu13.13, OpenSSL 3.0.13 30 Jan 2024
### common options:
*  -->ssh -h
*  ssh has lots of optiones , but you will use only few of them on a regular basis.
*  for more detailed explanation:
*  --> man ssh --> or search the internet
### connect:
*  --> ssh -l (user) ()hostname --> example:
*  --> ssh -l  di49zop lxlogin.lrz.de --> alternate --> ssh user@lxlogin.lrz.de --> or--> ssh user@IP_address
*  more info also:
*  https://doku.lrz.de/access-and-login-to-the-linux-cluster-10745974.html
*  **ssh -Y cool.hpc.lrz.de -l (user)**
*  enter the pass
*  then you need a second factor authentication
### ECDSA key fingerprint:
*  is a unique identifier for an Elliptic Curve Digital Signature Algorithm (ECDSA) public key, used in SSH and other applications to verify the identity of a server or user. It's a shorter, more manageable representation of a potentially long public key, created by applying a cryptographic hash function to the key.
*  ### commandsafter connection:
*  suppose you are successfully connected. in the following you will see some common commands:
*  --> hostname --> to see the host name
*  --> logout --> to log out -- > alternative --> CTRL + D
*  XXXX~> nslookup  lxlogin.lrz.de --> to see the IP Adress of the server
- Server:		10.156.33.53
- Address:	10.156.33.53#53
* alternative way for connecting --> ssh user@IP_address
## ----------------------------------------------------------------------------------

## some convenient:
* ### vim editor:
  - vim notes.txt - Open file
  - i - Start editing
  - Type your text
  - Esc - Stop editing
  - :w    save text
  - :q quit
  - :wq - Save and exit
* ### config file:
* Config file, store setting for applications. when we use a ready to copy config file to increase the speed of working
* --> man ssh_config --> to know more about how to use config file
* example:
* touch config --> create an empty config file
* vim config --> go and write the following lines in it:
  - alias 11='echo hallo '
  - alias 12='echo wie gehts?'
* --> save the file
* --> source ~/config --> from now, if you call 11 or 12 you will receive the following messages:
* 11 --> hallo
* 12 --> wie gehts?
## ----------------------------------------------------------------------------------
##   Simple troubleshooting
* there may be different possibilities for bug or failiur in connction.
* the first check can be (ping command) to check the availability of the server.
* --> ping lrz.de
## SSH key handeling
* link: https://smarty.userweb.mwn.de/movies/Sshkeyhandling.mp4
* **public key**:  I share it with the server to encript my messages. but I will keep the **Private key** with my self. in this way (only me) can decrypt the messages. because I have the both public and private key.--> so we can use these key pairs instead of (user and password) credentials.
## ----------------------------------------------------------------------------------
## ssh key generation:
* first step is to create these pair of key. --> we can use it for one session and then trough it a way . for anither session we will create another pair.
### step1 
* **ssh-keygen** --> command for creating a general key
* It will ask where to save the key --> just press Enter to use the **default location**.
* then It will ask for a passphrase: --> try to remember it :)
* This creates two files:
-  ~/.ssh/id_rsa → your private key
-  ~/.ssh/id_rsa.pub → your public key
### step2: Copy the public key to the remote server:
-  **ssh-copy-id -i ~/.ssh/id_rsa.pub username@lx1.lrz.de**--> replace (lx1.lrz.de)  with the appropriate LRZ server.
-  here we will be asked for the last time for the main password for set up the key
### now you can login with less challenge:
-  ssh username@cool.hpc.lrz.de
* I could not login with this method , but I think I learned it :)
## SSH agent handling
* to be continued from the following link:
* https://doku.lrz.de/ssh-tutorial-10746941.html
# GWDG:
* in germany: --> Gesellschaft für wissenschaftliche Datenverarbeitung mbH Göttingen
* translated to --> Society for Scientific Data Processing mbH Göttingen
* 
