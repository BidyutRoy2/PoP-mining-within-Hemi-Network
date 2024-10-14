<h2 align=center> Hemi PoP Mining Guide </h2>

## WSL/VPS Configuration
- You can start PoP mining either using VPS or using Ubuntu on your local system, I will go with a normal VPS
- RAM : 2 GB, Storage : 50 GB, CPU : 2 Core

## Installation
```bash
[ -f "Latesthemixyz.sh" ] && rm Latesthemixyz.sh; wget -q https://raw.githubusercontent.com/BidyutRoy2/PoP-mining-within-Hemi-Network/refs/heads/main/Latesthemixyz.sh && chmod +x Latesthemixyz.sh && ./Latesthemixyz.sh
```

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
