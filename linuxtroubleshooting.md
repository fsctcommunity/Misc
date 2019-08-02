# Setting up Remote Inspection of Linux Devices
Forescout can inspect Linux devices remotely via SSH and there is some confusion in the documentation on how to set this up. This is done via a trusted ssh key. This guide will cover two ways:
- Manual deployment
- Scripted deployment

NOTE: This information was provided to the Slack Forescout Community and put together for all to see/use.

## Manual Deployment of the SSH Keys
### Creation of the SSH User
Forescout uses a specific user and a trusted SSH key to make the remote connection to a server. For this we will be using a use called "fsuser".
- Connect to the Linux device you would like to use
- Add a user called "fsuser"
    - su -
    - useradd fsuser
    - passwd
- Change to the fsuser account
    - su - fsuser
- Create the .ssh folder if it does not exist
    - mkdir /home/fsuser/.ssh/
- Copy the SSH key from the Forescout Console into the authorized keys file
    - echo "ssh public key from console" > /home/fsuser/.ssh/authorized_keys
- Change the permissions on both the folder and the authroized keys file
    - chmod 600 /home/fsuser/.ssh/authorized_keys
    - chmod 700 /home/fuser/.ssh
- Validate you can login to the Linux box with the SSH Key
    - SSH to the CounterACT box
    - NOTE: If you are using CLIADMIN you  will need to escape to the shell first
    - Login to the Linux machine via ssh
        - ssh -i /usr/local/forescout/plugin/linux/ssh/keys/ssh_key fsuser@IPADDRESS 
## Scripted Deployment of the SSH Keys


/usr/local/forescout/plugin/linux/ssh/keys/ssh_key.pub

 ssh -i /usr/local/forescout/plugin/linux/ssh/keys/ssh_key fsuser