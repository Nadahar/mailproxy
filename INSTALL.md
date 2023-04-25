# Service Installation
The service installation must be performed "manually" by placing the files in the required location.

## `config.ini`
After editing `config.ini` with at least 'SMTP server address', 'username' and 'password', create folder '/etc/mailproxyd' and put `config.ini` in this folder.

#### Example:
```powershell
> sudo mkdir /etc/mailproxyd
> sudo cp config.ini /etc/mailproxyd/.
```

## `mailproxy.service`
This file should normally be placed in the `/etc/systemd/system` folder.

#### Example:
```powershell
> sudo cp mailproxy.service /etc/systemd/system/.
```

## `mailproxyd`
This is the python script itself, and it can be placed in any folder included in the "systemd path", for example `/usr/local/bin` and given execute permission.

#### Example:
```powershell
> sudo cp mailproxyd /usr/local/bin/.
> sudo chmod 755 /usr/local/bin/mailproxyd
```

# Control
Once the files are in place, it can be controlled like any other systemd service. To start it, use:
```
sudo systemctl start mailproxy
```
Check that it actually started with:
```
sudo systemctl status mailproxy
```
Stop it with:
```
sudo systemctl stop mailproxy
```
Set it to autostart with
```
sudo systemctl enable mailproxy
```
