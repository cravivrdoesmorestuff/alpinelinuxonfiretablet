# alpinelinuxonfiretablet
This is a guide to install alpine linux (postmarketos) on the Fire Tablet 5th Generation with the codename ford, (maybe trying it on austin if i find a tablet) this is a continuation of https://wiki.postmarketos.org/wiki/Amazon_Fire_7_2015_(amazon-ford)

before starting you need to be on a linux based system like debian or fedora
WSL, WSL2 is untested

#ford
First, you need to unlock your bootloader using this guide: https://xdaforums.com/t/unlock-root-twrp-unbrick-downgrade-fire-7-ford-and-austin.3899860/

After doing that, install python and pip and pmbootstrap with the command below

git clone --depth=1 https://gitlab.postmarketos.org/postmarketOS/pmbootstrap.git
mkdir -p ~/.local/bin
ln -s "$PWD/pmbootstrap/pmbootstrap.py" ~/.local/bin/pmbootstrap

MAKE SURE YOU ARE ON PMBOOTSTRAP 3.9.0 OR NEWER
do pmbootstrap --version to verify this or ./pmbootstrap -v

now, go into the terminal 

select device as amazon-ford
vendor as amazon
and codename ford

preferably choose a non-gui interface select console or buffyboard

now! you should create the "rom" that you would install using pmbootstrap install --android-recovery-zip
could take 15-45 minutes

When thats done you can you flash the zip, plug in the tablet and enter TWRP by holding the power button and the left volume button
Click Advanced and click ADB Sideload
go back into the terminal and paste pmbootstrap flasher --method=adb sideload

Now Restart your device and it should be running alpine linux! (this could take some reboots because of the amonet exploit)

if you get into a bootloop wait 20-1h and find an error message like (roofs not found or root parition not found, i got this problem)

download the android-recovery.zip file in the github and try flashing with that - if you get a different error message send it as a bug
ill make a fix for it!






# I AM NOT RESPONSIBLE FOR BRICKED DEVICES AND BLA BLA BLA THIS GUIDE IS NOT COMPELETLY VERIFYED TO WORK
please report bug fixes here
# made by JustCravi on YT
