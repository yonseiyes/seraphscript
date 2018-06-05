# SERAPHcoin

Shell script to install a [Seraph Masternode] on a Linux server running Ubuntu 16.04. Use it on your own risk.  

***

## Installation:  
Copy & Paste below in Command line of VPS server & Press 'Enter'

    git clone https://github.com/yonseiyes/seraphscript.git ; cd seraphscript ; chmod +x seraphscript ; ./seraphscript ;

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the SeraphCoin Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN01**  
3. Send **5000** SERA to **MN01**.  
4. Wait for 15 confirmations.  
5. Go to **Tools -> "Debug Console"**  
6. Type the following command: **masternode outputs**  
7. Open **Masternodes.conf** file  
8. fill the next items ( They should be on one line )
* Alias: **MN01** 
* Address: **VPS_IP:PORT**  
* Privkey: **Masternode Private Key**   **which is shown by typing 'masternode genkey' on debug console of desktop wallet.**
* TxHash: **First value from Step 6**  
* Output index:  **Second value from Step 6**  

For example :

MN01 144.217.161.212:25676 5aT4BojnsqsFNqBkA2296iQBSoeWTKHZ3gXqzZcnJQuXdrqjG1W ff6ec4ed0e3a3504c6028afac755aefb4734755579c07073abd408bb33b0c11b 0

9. Save & Exit **Masternode.conf** 
10. Restart Seraph Wallet  
11. Click **Start All** in Masternode tab
12. (optional but preferable) If you want to work in the debug console, type "startmasternode alias 0 MN01"
13. If you encounter some error messages, please check 'masternode.conf' in desktop wallet


***
## Update 
    cd ~/seraph
    git pull
    cd src
    ./seraph-cli stop
    make -f makefile.unix

and Run daemon

    ./seraphd

That's all! Enjoy your Masternode!! - written by 돔말(dommal)
