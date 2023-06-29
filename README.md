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
Do not add the `-s` option with the `ln` command; you can't use symbolic links to `/etc/bluetooth`. If you use them, they will cause the permission error as follow:

```
src/main.c:load_config() Parsing /etc/bluetooth/main.conf failed: Permission denied
```

And it is highly recommended to make sure that there are no errors or warnings with `journalctl -u bluetooth` every time you change the settings.

## Troubleshooting
### `Failed to set power on: org.bluez.Error.Busy`
https://stackoverflow.com/questions/68728478/failed-to-set-power-on-org-bluez-error-blocked-problem
