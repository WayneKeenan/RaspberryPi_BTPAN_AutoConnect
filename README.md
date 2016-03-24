## A script and cron job to auto connect to a Bluetooth Network.

See this [video](https://www.youtube.com/watch?v=4Ac0wc-f9HI) by Andrew Mulholland on how to setup a connection manaully first.



After cloning this repostiory copy the 2 scripts `bt-pan` and `check-and-connect-bt-pan.sh` to `~pi/bin`  
(create the folder if necessary)


## Find you Mac/PC 

First we need to determine the Bluetooth MAC address of your MAc/PC that is providing the network link.

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


## Automatically reconnect

In order for the Pi to automatically reconnt we are using a `cron` job to run a test and connect script every minute.

Type:
```
crontab -e
```

Add this line:

```
* * * * * /home/pi/bin/check-and-connect-bt-pan.sh
```

Then save the file.
