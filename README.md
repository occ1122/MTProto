# mtg-dist
Oneline distbute and install script for mtg ( https://github.com/9seconds/mtg ).

## Note

mtg 2.0+ supports FakeTLS mode only.
Re-run this script to upgrade.

# Install
```
bash <(wget -qO- https://raw.githubusercontent.com/occ1122/MTProto/main/install.sh)
```

## Offline Install

For machines have difficulties visiting github, download the following files:

- `mtg-dist.bin` from [release](https://github.com/occ1122/MTProto/releases)
- `mtg-2.x.x-linux-amd64.tar.gz` from [mtg/release](https://github.com/9seconds/mtg/releases)

then run: 
```
sh mtg-dist.bin mtg-2.0.1-linux-amd64.tar.gz
```

# Uninstall

```
systemctl disable mtg 
systemctl stop mtg 
rm -f /usr/local/bin/mtg /etc/systemd/system/mtg.service /etc/mtg.toml   
```

## for version 0.0.6 and prior
```
systemctl disable mtg 
systemctl stop mtg 
rm -f /usr/local/bin/mtg /lib/systemd/system/mtg.service /etc/mtg.conf    
```

# Customize

The configure file is at `/etc/mtg.toml`, refer to the offcial document for whatever you want to custom.

- https://github.com/9seconds/mtg 
- https://github.com/9seconds/mtg/blob/master/example.config.toml

After edited just restart the mtg service:

```
systemctl restart mtg 
```

# Compile
This project uses `makeself` to generate a `.bin` file.

```
./makebin.sh
```
