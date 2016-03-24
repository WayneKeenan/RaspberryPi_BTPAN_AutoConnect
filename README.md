## A script and cron job to auto connect to a Bluetooth Network.


After cloning this repostiory copy the 2 scripts `bt-pan` and `check-and-connect-bt-pan.sh` to `~pi/bin`  (create the folder if necessary)


## 

run `hcitool scan`:

```
hcitool scan
Scanning ...
	F4:5C:89:8B:10:E8	Wayne’s MacBook Pro
```

Edit `check-and-connect-bt-pan.sh` replacing the MAC address foud from `hcitool scan` with your one.


```
BT_MAC_ADDR=F4:5C:89:8B:10:E8

```



```
crontab -e
```

Add this line:

```
* * * * * /home/pi/bin/check-and-connect-bt-pan.sh
```
