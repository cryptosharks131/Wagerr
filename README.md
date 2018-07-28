# Seather
Shell script to install a [Seather Masternode](http://seather.online/) on a Linux server running Ubuntu 16.04.  
This will require a VPS, I use [Vultr](https://www.vultr.com/?ref=7310394).  I recommend using a $5 server.
This script will install **Seather Core 1.0.0**.
***

## Installation:
Log into the server using ssh (Putty for windows or terminal for Mac users) and run the following commands:
```
wget -q https://raw.githubusercontent.com/cryptosharks131/Seather/master/seather_install.sh
bash seather_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows/Mac Wallet:
1. Open the Seather Core Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **10000** **STR** to **MN1**.
4. Wait for 15 confirmations before starting the node.
5. Go to **Help -> "Debug window - Console"**
6. Type the following command: **masternode outputs**
7. Open masternode.conf from the following folder %appdata%\seather (windows) or ~/Library/Application Support/ (hidden folder for Mac users)
8. Add the following entry:
```
Alias Address Genkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:22500**
* Genkey: **Masternode GenKey**
* TxHash: **First value from Step 6** 
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. Click OK and exit the Wallet.
10. Open Seather Core Wallet, go to **Masternode Tab**.
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All** or **Start Alias**
11. If you are not able to see your **Masternode**, try to close and open your desktop wallet.
***

## Usage:
```
seather-cli getinfo
seather-cli masternode status
```
Also, if you want to check/start/stop **Seather** , run one of the following commands as **root**:
```
systemctl status Seather #To check the service is running.
systemctl start Seather #To start Seather service.
systemctl stop Seather #To stop Seather service.
systemctl is-enabled Seather #To check whetether Seather service is enabled on boot or not.
```
***

## Updating Seather
The first line (rm seather_update.sh) is not required the very first time you update the node and will return an error if you run it.  This is fine, continue with the update script.
```
rm seather_update.sh*
wget -q https://raw.githubusercontent.com/cryptosharks131/Seather/master/seather_update.sh
bash seather_update.sh
```
***

## Donations:  

**STR**: Sai7kjUqumjzhZU5bQs8YmcJLq1pcgDT16  
**BTC**: 1FJvtLBszQgY2eKBawov48RwSYy2yqEvn1  
**ETH**: 0x39acE9917e25E2A04643d30319cF34449A72441B  
**LTC**: LR1Mmchr6Zz1vj51xecTiEdS1WHfJTVg5t
