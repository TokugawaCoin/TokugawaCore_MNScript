# TokugawaCore_MNScript


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
