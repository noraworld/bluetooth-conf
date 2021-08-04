# bluetooth-conf
Bluetooth config files.

## Setup
```shell
cd bluetooth-conf
sudo rm -r /etc/bluetooth
sudo ln -s $PWD/bluetooth /etc/bluetooth
sudo systemctl enable bluetooth
```
