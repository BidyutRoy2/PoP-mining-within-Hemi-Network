<h2 align=center> Hemi PoP Mining Guide </h2>

## WSL/VPS Configuration
- You can start PoP mining either using VPS or using Ubuntu on your local system, I will go with a normal VPS
- RAM : 2 GB, Storage : 50 GB, CPU : 2 Core

## If You Already Installed Delete File (Command)
```
rm heminetwork_v0.4.3_linux_amd64.tar.gz hemixyz.sh
```
```
rm -rf heminetwork_v0.4.3_linux_amd64
```

## Installation
```bash
[ -f "Latesthemixyz.sh" ] && rm Latesthemixyz.sh; wget -q https://raw.githubusercontent.com/BidyutRoy2/PoP-mining-within-Hemi-Network/refs/heads/main/Latesthemixyz.sh && chmod +x Latesthemixyz.sh && ./Latesthemixyz.sh
```

### Import Your Hemi Testnet Wallet Private Key

- **Copy all these details and save it somewhere**
```bash
cat ~/popm-address.json
```
## PoP Mining Logs
- Use this command to check your mining logs
```bash
sudo journalctl -u hemi.service -f -n 50
```

## Overall stats
- Visit [this website](https://testnet.popstats.hemi.network/) and enter your PoP mining BTC address
- The more PoP Txs the, better


- Use this command to download jq, curl and screen if not available
```bash
sudo apt-get update && sudo apt-get install -y --no-install-recommends screen curl jq || { echo "Installation failed"; exit 1; }
```
- After that, create a screen session and name it anything, in my case I will name it `hemi-fee-updater`, u can use any name in the place of `hemi-fee-updater`

```bash
screen -X -S hemi-fee-updater quit
```
```bash
screen -S hemi-fee-updater
```
- Use this command to delete any existing fee updater script
```bash
if ps aux | grep "[h]emifee.sh" > /dev/null; then
    ps aux | grep "[h]emifee.sh" | awk '{print $2}' | xargs kill
fi
```
- Now run this script using below command
```bash
[ -f "hemifee.sh" ] && rm hemifee.sh; curl -sSL -o hemifee.sh https://raw.githubusercontent.com/BidyutRoy2/PoP-mining-within-Hemi-Network/refs/heads/main/Update2/hemifee.sh && chmod +x hemifee.sh && ./hemifee.sh
```
- **Now press `Ctrl` + `A` + `D` (VERY IMP) after that u can close your VPS**
- DONE, it will automatically fetch the fee and will update in the service file in every 10 mins
