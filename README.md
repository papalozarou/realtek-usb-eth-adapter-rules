# Realtek rules for RTL8159, RTL8157 and RTL8156/RTL8156B(G) chipsets

Clone of Realtek rules to enable Raspberry Pi 5 to work with the following network adapters:

* RTL8159: 10G Gigabit Ethernet > USB 3.2 Gen2
* RTL8157: 5G Gigabit Ethernet > USB 3.2 Gen2
* RTL8156/RTL8156B(G): 2.5G Gigabit Ethernet > USB 3.0

Taken from [Realtek's site](https://www.realtek.com/Download/List?cate_id=585) and [a thread on the Raspberry Pi forums](https://forums.raspberrypi.com/viewtopic.php?t=362358&cmdf=ugreen+2.5gb+usb+with+raspberry+pi+5).

## Installation

Copy the file to the Pi then copy the file to the correct location:

```
sudo cp 50-usb-realtek-net.rules /etc/udev/rules.d/
```

Reboot the Pi:

```
sudo reboot now
```

Verify the adapter is working:

```
sudo ethtool eth1
```

The output should be something like:

```
Settings for eth1:
        Supported ports: [ TP    MII ]
        Supported link modes:   10baseT/Half 10baseT/Full
                                100baseT/Half 100baseT/Full
                                1000baseT/Half 1000baseT/Full
                                2500baseT/Full
…
```

Tested successfully on a Raspberry Pi 5 with a [UGreen 2.5Gb USB3.2 Gen 1 adapter](https://www.amazon.co.uk/gp/product/B0CWV2Q6HJ?smid=AXZ3JQ1GVFPIF&psc=1).