# Guide-in-Moonbeam-network-validator-
In this guide you will find a detailed description of how to create a validator on the Moonbeam network 
# Official Links
[Website](https://moonbeam.network/) [Twitter](https://twitter.com/MoonbeamNetwork) [Discord](https://discord.gg/moonbeam)

# Explorer
[Explorer](https://telemetry.polkadot.io/#list/0xfe58ea77779b7abda7da4ec526d14db9b1e9cd40a217c34892af80a9b332b76d)
# Install Node Guide 
### Setting up variables
First you need to download the binary file of the current version
```bash
wget https://github.com/PureStake/moonbeam/releases/download/v0.27.1/moonbeam
```
### To verify that you have downloaded the correct version, you can run  moonbeam in your terminal, you should receive the following output:
```bash
sha256sum
```
### you should receive the following output:
```bash
b497f3e9f6f9c1e8591fbcbde5c18e24a5a5b4cdb98bc641ac7e643890a523fe
```


### Setup the Service

### The following commands will set up everything regarding running the service.

### 1. Create a service account to run the service:
```bash
adduser moonbeam_service --system --no-create-home
```
### 2. Create a directory to store the binary and data
```bash
mkdir /var/lib/moonbeam-data
```
### 3. Move the binary built in the last section to the created folder
```bash
mv ./moonbeam /var/lib/moonbeam-data
```
### 4. Make sure you set the ownership and permissions accordingly for the local directory that stores the chain data:
```bash
sudo chown -R moonbeam_service /var/lib/moonbeam-data
```
### Create the Configuration File
The next step is to create the systemd configuration file. If you are setting up a collator node, make sure to follow the code snippets for Collator. Note that you have to:
   ### -  Replace YOUR-NODE-NAME in two different places
   ### -  Replace <50% RAM in MB> for 50% of the actual RAM your server has. For example, for 32 GB RAM, the value must be set to 16000. The minimum value is 2000, but          it is below the recommended specs
   ### -  Double-check that the binary is in the proper path as described below (ExecStart)
   ### -  Double-check the base path if you've used a different directory
 
### Create file 
```bash
nano /etc/systemd/system/moonbeam.service
```




