# CoinClix masternode setup
Shell script to install a CoinClix Masternode on a Linux server running Ubuntu 16.04.
Use at your own risk.
***

## VPS installation
```
wget -N https://raw.githubusercontent.com/CoinClix/CoinClix/blob/master/node_install/coinclix_install.sh
bash coinclix_install.sh
```
***

## Desktop wallet setup

After the Masternode is up and running, you will need to configure the desktop wallet. Follow these steps:
1. Open the CoinClix Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **10000** CLX to **MN1**. You need to send all 10000 coins in one single transaction.
4. Wait for 20 confirmations.
5. Go to **Help -> "Debug Window - Console"**
6. Type the following command: **masternode outputs**
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
startmasternode alias 0 MN1
```
14. Login to your VPS and check your masternode status by running the following command to confirm your MN is running:
```
coinclix-cli masternode status
```
***

## Usage:
```
coinclix-cli masternode status #To check your MN status
coinclix-cli getinfo #To get general info such as CoinClix version and current block number
coinclix-cli mnsync status #To check if your MN is synced.
```
If you want to check/start/stop **CoinClix**, run one of the following commands as **root**:

```
systemctl status coinclix #To check if the CoinClix service is running
systemctl start coinclix #To start the CoinClix service
systemctl stop coinclix #To stop coinclix service
systemctl is-enabled coinclix #To check if CoinClix service is enabled on boot
```
***
