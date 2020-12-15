# MasternodeSetup

### Required:

1. Emoji Coin for Collateral <br>
(You can buy Emoji from exchange for collateral) <br>
*** <br>
Exchange: Graviex - coming shortly
<br>***

2. Download your Local Wallet: https://github.com/emojiproject/wallets

- You can see daily income and collateral info here: https://emojiproject.net


3. You will need also VPS with Ubuntu 16.04 or 18.04

**VPS WALLET:**

1. After you longin on your VPS , with this command you will download masternode-installer.   
`wget https://raw.githubusercontent.com/`  
 

2. With this command you will make masternode-install-ubuntu.sh executable.  
`sudo chmod +x masternode-install-ubuntu.sh` <br>



3. Now install your masternode.  
`./masternode-install-ubuntu.sh`




**LOCAL WALLET:**

Send the collateral
Open your wallet and wait until your wallet has downloaded the blockchain.

Go to “Tools”.
Click “Debug console”.
This is the console where you will execute all commands.

Create a new masternode private key.

```
createmasternodekey
```

Example output

7fa6vHSfGB2LRwpzoVHHT2D3z59JxVQgvCRiJuaBdFQJxUSNhVU

Show your collateral address.
```
getaccountaddress "MN01"
```

Example output

EHSdLnPeH2Z7FoKfvn7VDwJ8jBmhnq2vVZ
```
Transfer the required amount of coins to the “collateral address” that you created using the command “getaccountaddress "MN1"”.
```
Wait until the transaction has the required masternode confirmations.

Go to “Tools”.
Click “Debug console”.
Enter the following command.
```
getmasternodeoutputs
```
```
Example output


[
  {
    "txhash": "256a242ccbfdw155bcd9cff5f4041752c911f39cb2905acc83ccfe0cf2348d0C",
    "outputidx": 0
  }
]
```

Modify the following line in your masternode.conf file and paste it into:
```
MN01 VPSIP:15452 7fa6vHSfGB2LRwpzoVHHT2D3z59JxVQgvCRiJuaBdFQJxUSNhVU 256a242ccbfdw155bcd9cff5f4041752c911f39cb2905acc83ccfe0cf2348d0C 0
```
MN01 - Alias for your masternode.

VPSIP- External IP address of your VPS.

15452 - The port  

7fa6vHSfGB2LRwpzoVHHT2D3z59JxVQgvCRiJuaBdFQJxUSNhVU - Masternode private key from the command “createmasternodekey”.

256a242ccbfdw155bcd9cff5f4041752c911f39cb2905acc83ccfe0cf2348d0C - Value “txhash” from the command “getmasternodeoutputs”.

0 - Value “outputidx” from the command “getmasternodeoutputs”.


Save the file and close.

Close your wallet.

Restart your wallet! 
On Masternode tab in your wallet - Start the masternode!
