## A script and cron job to auto connect to a Bluetooth Network.

See this [video](https://www.youtube.com/watch?v=4Ac0wc-f9HI) by Andrew Mulholland on how to setup a connection on a Pi3 manually first.

The bt-pan script comes from [here](https://github.com/mk-fg/fgtk.git).


After cloning this repository copy the 2 scripts `bt-pan` and `check-and-connect-bt-pan.sh` into `~pi/bin`  
(create the folder if necessary)


## Find your Mac/PC MAC Address

We need the Bluetooth MAC address of your Mac/PC that is providing the Bluetooth network.

On the Pi run `hcitool scan`:

```
hcitool scan
Scanning ...
	F4:5C:89:8B:10:E8	Wayne’s MacBook Pro
```

Edit `check-and-connect-bt-pan.sh` and replace the exisitng MAC address assigned to `BT_MAC_ADDR` with the one found by `hcitool scan` for your computer.

```
BT_MAC_ADDR=<Your MAC address>
```


## CRON job

In order for the Pi to automatically (re)connect create a `cron` job to run a script every minute.

Type:
```
crontab -e
```

Add this line:

```
* * * * * /home/pi/bin/check-and-connect-bt-pan.sh
```

Then save the file.

