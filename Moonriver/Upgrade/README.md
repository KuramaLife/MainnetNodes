> If you want to update your client, you can keep the existing chain data intact and update only the binary file

## Stop the service

```bash
sudo systemctl stop moonriver.service
```

## Remove the old binary file

```bash
rm  /var/lib/moonriver-data/moonbeam
```

> Get the latest version of Moonbeam from the [Moonbeam GitHub Release page](https://github.com/PureStake/moonbeam/releases)

## Download the latest version of the binary file

```bash
wget https://github.com/PureStake/moonbeam/releases/download/<NEW VERSION TAG HERE>/moonbeam
```

## Move the binary to the data directory

```bash
mv ./moonbeam /var/lib/moonriver-data
```

## Navigate to the directory where the binary file is located and grant permissions

```bash
cd /var/lib/moonriver-data/moonbeam
chmod +x moonbeam
chown moonriver_service moonbeam
cd $HOME
```

## Register and start the service

```bash
systemctl enable moonriver.service 
systemctl start moonriver.service 
systemctl status moonriver.service
```

## Check the logs

```bash
journalctl -u moonriver.service -f -o cat
```
