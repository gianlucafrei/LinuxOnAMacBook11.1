# LinuxOnAMacBook11.1
Some tips on how to configurate linux on a macbook version 11.1

Recently I installed Kubuntu on my MacBook Retina. After some struggle with the drivers, I finally got a smooth running system. I tried a lot of different stuff from different sources, this repo should help you if you want to install Kubuntu on your MacBook. If you want to install a different distro or have a different MacBook version, some of the steps here will still work.

# Basic Configuration

Download the latest release of Kubunut and install it from a USB-Stick. I don't cover that here since there are plenty of tutorials out there.

Check your product version
You can check the version of your MacBook by using the command:

## Wifi

The WiFI does not work out of the box. To fix this I connected my machine to the internet via an ethernet cable.

```
> sudo apt-get install bcmwl-kernel-source

```

## Display Scaling


Go to Systems Settings > Displays > Scale Display. I took a scaling factor of 1.2.

Also, check out the font DPI. Go to Systems Settings > Fonts and choose Force Fonts DPI. Try out what fits you best. I selected 139.


## Touchpad

To configure touch gestures take a look at the following repo.
[https://github.com/iberianpig/fusuma](https://github.com/iberianpig/fusuma)

## Printer

I had a lot of issues with my brother network printer.  Try to install CUPS:

```
# Install cups
sudo apt install cups

# Add network printer
lpadmin -p <name> -E -v ipp://<PrinterIP>/ipp/print -m everywhere
```

# Webcam

TODO

# Additional Stuff

## Power consumption

Optimize the power consumption with powertop and tlp.


```
sudo apt-get install powertop
sudo apt-get install tlp tlp-rdw
sudo tlp start

# Check out the following configuration file
sudo vi /etc/default/tlp

sudo powertop --calibrate
sudo powertop --auto-tune
```

## Antivirus

I recommend installing an anti-virus solution. On my machine I installed ClamAV.

```
# Installation
sudo apt install clamav


# Make a scan
clamscan
```



