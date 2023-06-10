> If you want to update your client, you can keep the existing chain data intact and update only the binary file

## Stop the service
```bash
sudo systemctl stop bifrost.service
```

## Remove the old binary file
```bash
rm  /var/lib/bifrost-data/bifrost
```

> Get the latest version of Bifrost from the [Bifrost GitHub Release page](https://github.com/bifrost-finance/bifrost/releases)

## Download the latest version of the binary file
```bash
wget https://github.com/bifrost-finance/bifrost/releases/download/<NEW VERSION TAG HERE>/bifrost
```

## Move the binary to the data directory
```bash
mv ./bifrost /var/lib/bifrost-data
```

## Navigate to the directory where the binary file is located and grant permissions
```bash
cd /var/lib/bifrost-data
chmod +x bifrost
chown bifrost_service bifrost
cd $HOME
```

### Register and start the service
```bash
systemctl enable bifrost.service
systemctl start bifrost.service
systemctl status bifrost.service
```

### Check the logs
```bash
journalctl -u bifrost.service -f -o cat
```
