# Token Creation Guide for create_token.py by browolf, guide by FireBlastAn0n

This guide will walk you through the process of creating a token on the Pi Network testnet using browolf's create_token.py script.

## Operating System Requirements

This guide is based on Linux Mint.

## Installing Required Dependencies

### Python3, Pip and Stellar-SDK Installation

First, we will install the required dependencies to run create_token.py
```bash
sudo apt-get install -y python3 python3-pip
```
Next we need to install the stellar-sdk for use with browolf's script
```bash
pip install stellar-sdk
```
If you receive an error about system-wide applications the run the above command like this:
```bash
pip install stellar-sdk --break-system-packages
```

### Obtaining Issuer and Distributor Secret & Public Keys

Next we need to pull out our phone and open Pi Browser to generate 2 wallets with secret/public keys to do this:
```bash
1.) Open Pi Browser app.
2.) Navigate to the "Develop" app in Pi Browser.
3.) Create a new testnet app and name it "YourTokenName Issuer App"
4.) Create a second testnet app and name it "YourTokenName Distributor App"
5.) Click the wallet option in app configuration, and generate a wallet for each app.
6.) Once you generate the wallet, it will give you a public and secret key, and automatically issue 100 test-pi which will be needed for token creation.
7.) Save the Secret & Public Keys for both created apps, and send them to your PC/Laptop for easy copy/pasting.
```

### Editing the Script to Include Your Secret Keys & Token Info

Return to your PC/Laptop and open the create_token.py script and edit the following lines:
```bash
ASSET_CODE = "YourAssetName"
TOTAL_SUPPLY = "putanumberofcoins"  # not fixed; you can mint more later
TRUSTLINE_LIMIT = "putanumberofcoins"  # generous limit for distributor```

AND

def main():
    print("=== Pi Testnet: Create & Distribute Asset ===")
    issuer_secret = "IssuerWalletSecretKeyGoesHere"
    dist_secret   = "DistributorWalletSecretKeyGoesHere"
```

### Run The Script

Navigate to and run create_token.py
```bash
cd /path/to/create_token.py
python3 create_token.py
```

## All Done

All done, the script should now run properly and create your token, you can verify this by navigating to https://piscan.io/assets and searching your token name and it should be displayed.
