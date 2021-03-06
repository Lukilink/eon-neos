Downgrade from 0.6 to 0.5 
======

This is the operating system for your [EON Dashcam Development Kit](https://shop.comma.ai/products/eon-dashcam-devkit).

It's open source, you can find the repo needed to build NEOS [here](https://github.com/commaai/eon-neos-builder)


------

Requirements: unzip, simg2img, fastboot

Clone this repo. Hold power and volume to enter fastboot mode on your EON. Then run:

You can use homebrew to install: 

1. Install homebrew

```
ruby -e “$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
2. Install adb (fastboot)

```
brew cask install android-platform-tools
```

3. Install simg2img
```
brew install simg2img
```

``` 
git checkout 45ce1790dd5f4ef8ef5987fa198a904b69b9ce53
```

Hold power and volume to enter fastboot mode on your EON or Android device. 

Connect it via USB to your MAC.

Navigate to the direction, wehre your files are and run:

```
./download.py 
./flash.sh
```

After a while your eon will reboot and ask you: "Enter the URL of the NEOS program to install"

Type in:

```
https://openpilot.comma.ai
```

It will download and install official comma 06. 

After rebooting a purple screen will appear: 

![enter image description here](https://cdn.discordapp.com/attachments/555026950067060736/597766347031838723/image0.jpg)


Do not klick anything. 

From here you need to install 05.11 original comma:

ssh in and [guide for ssh](https://medium.com/@jfrux/comma-eon-getting-connected-with-ssh-3ed6136e4a75): 

```
cd /data; cp -rf ./openpilot ./openpilot.bak; rm -rf ./openpilot; git clone https://github.com/arne182/openpilot.git openpilot; cd openpilot; git checkout 0511-final
```

Restart your eon and it will boot on 05.11 branch. 

From here you can install every awesome fork with great mapd support for example ;) - Like arnes realse 2 :

[Arne's fork](https://github.com/arne182/openpilot/tree/release2)



<b>NOTE: This will wipe your EON</b>



Restoring on Linux
------
Submit a PR with instructions.

Restoring on Windows
------
Submit a PR with instructions.
