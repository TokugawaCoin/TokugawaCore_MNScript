# Tokugawa Masternode setup 

Masternode setup needs:
One cold wallet hosted on Ubuntu 16.04 and (always to be kept online so buy VPS)
One Windows controller hot wallet that has your coins in it. (can be kept offline... once the Ubuntu wallet starts)

wget -q https://raw.githubusercontent.com/TokugawaCoin/TokugawaCore_MNScript/master/tokinstall.sh

sudo chmod +x tokinstall.sh

./tokinstall.sh

When prompted to Enter your tokugawa Masternode GEN Key.

Paster your Masternode GEN Key and press enter

Wait till Node is fully Synced with blockchain. For check enter below command.

tokugawa-cli getinfo

When Node Fully Synced enter below command for check masternode status.

tokugawa-cli masternode status

---------------------------------------------------------------------------

After the above Masternode is up and running, you need to configure the desktop wallet also. Here are the steps for Windows Wallet

1. Open the Tokugawa Coin Desktop Wallet.
2. Go to File -> RECEIVE and create a New Address: MN1
3. Send exact 10000 TOK coins to MN1.
4. Wait for 15 confirmations.
5. Go to Tools -> "Debug console - Console"
6. In "Debug console - Console" type and copy following command: Masternode outputs
7. When the VPS script finishes executing, it will provide you with the Masternode genkey that you will need for the next step.
8. Go to ** Tools -> "Open Masternode Configuration File"
9. Add the following entry in the config file:

Alias Address Privkey TxHash Output_index

- Alias: MN1
- Address: VPS_IP:7119
- Privkey: Masternode Genkey from step 7
- TxHash: First value from Step 6
- Output index: Second value from Step 6

10. Save and close the config file.
11. Close and reopen the QT wallet so it loads the new config you just wrote.
12. Go to Masternode Tab. If you tab is not shown, please enable it from: Settings - Options - Wallet - Show Masternodes Tab
Click Update status to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
13. Right click on the masternode and click start alias.
The active timer will start ticking after 3 hours.


----------------------------------------------------------------------------------------------------------
Multiple Masternode setup:


You can use the above steps for the first masternode, for setting up more masternodes, you need to purchase more Linunx ubuntu 16.04 VPS. Only one Windows-controller-hot wallet is needed, while multiple Linux VPS are needed if you want to setup multiple Masternodes.

All the above steps are to be followed for multiple masternodes, while doing so... in above step 6 and step 7 you will get new masternode output and new masternode private key. 
Example file for 3 masternodes in 3 VPS and single Windows controller wallet.

Alias Address Privkey TxHash Output_index
replaced by

- MN1 145.245.222.111:7119 JKHDGJDFHGKDF8DFJKGHDFK98DKFJ87783JK 9I5I464I56K45J6K45N 1
- MN2 205.141.121.212:7119 UWYERUWYRUIWYERUIWYEURYWUERY878WEUYR 6WERJWHIWEURIWE87WE 0

Save exit the conf file, restart wallet. In masternodes section, you will see new masternode waiting to be enabled. Right click on this new masternode and click Start Alias.

The active timer will start ticking only after 3 hours.
