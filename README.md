# bluetooth-conf
Bluetooth config files.

## Setup
```shell
cd bluetooth-conf
sudo rm -r /etc/bluetooth
sudo mkdir /etc/bluetooth
sudo ln $PWD/bluetooth/* /etc/bluetooth
sudo systemctl enable bluetooth
```

### Important note
You can't use symbolic links to `/etc/bluetooth`. If you use them, they will cause the permission error as follow:

```
src/main.c:load_config() Parsing /etc/bluetooth/main.conf failed: Permission denied
```

You can see the above error on `journalctl -u bluetooth`. So do not add the `-s` option with the `ln` command.
