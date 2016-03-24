

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
