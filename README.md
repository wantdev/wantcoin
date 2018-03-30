# WantCoin
Shell script to install a [Want Coin Masternode](http://wantcoin.club/) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget -q https://raw.githubusercontent.com/zoldur/WantCoin/master/wantcoin_install.sh
bash wantcoin_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Want Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **1000** WANT to **MN1**. You need to send all 1000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs** 
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
masternode start-alias "MN1"
``` 
14. Login to your VPS and check your masternode status by running the following command:.
```
want-cli masternode status
```
***

## Usage:
```
want-cli mnsync status
want-cli masternode status  
want-cli getinfo
```
Also, if you want to check/start/stop **Want**, run one of the following commands as **root**:

```
systemctl status WantCoin #To check if Want service is running  
systemctl start WantCoin #To start Want service  
systemctl stop WantCoin #To stop Want service  
systemctl is-enabled WantCoin #To check if Want service is enabled on boot  
```  
***

## Donations

Any donation is highly appreciated

**WANT**: D3q9JjZ5TGovsufm9j26Z3JurqseyuyDSV  
**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x26B9dDa0616FE0759273D651e77Fe7dd7751E01E  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB  
