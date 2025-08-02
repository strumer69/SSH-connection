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
* --> ssh -V
* it will show the version of the ssh client on your laptop. the more recent the version the better. for example mine is as follow:
  - (base) shahram@shahram-X556UB:~$ ssh -V
  - OpenSSH_9.6p1 Ubuntu-3ubuntu13.13, OpenSSL 3.0.13 30 Jan 2024
*  ### common options:
*  -->ssh -h
*  ssh has lots of optiones , but you will use only few of them on a regular basis.
*  for more detailed explanation:
*  --> man ssh --> or search the internet
*  ### connect:
*  --> ssh -l (user) ()hostname --> example:
*  --> ssh -l  di49zop lxlogin.lrz.de
*  more info also:
*  https://doku.lrz.de/access-and-login-to-the-linux-cluster-10745974.html
*  
*  
