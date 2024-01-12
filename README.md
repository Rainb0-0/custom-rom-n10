## **Installing custom ROMs on Oneplus nord N10 5g**

Overview:

1.  Unlock bootloader
2.  Flash recovery
3.  Flash ROM

## **Enable USB debugging**

Open settings on your phone. Scroll down to About phone and tap on it.

Find the build number and tap on it 7 times. (If you have a password/pattern it asks you to enter it).

Go back to the settings list. Scroll down to system and tap on it. Open the developers option and enable USB debugging(If you can't find it you can search for it).

## **Downloading adb and fastboot**

**Windows:**  
Download platform tools from [HERE](https://dl.google.com/android/repository/platform-tools-latest-windows.zip) and extract it somewhere you remember and note the location you extracted it.

**Linux:**

1.  **Arch:** `sudo pacman -S android-tools`
2.  **Debian:** `sudo apt install android-sdk-platform-tools-common`

## **Unlocking the bootloader**

**MAKE SURE TO BACKUP YOUR DATA. UNLOCKING THE BOOTLOADER RESETS YOUR PHONE.**

Connect your phone to you PC(preferably USB 2.0). do `adb devices`in the terminal/cmd(On windows: open cmd and navigate to the location you extracted platform tools using the `cd` command. Then use `.\adb.exe devices`). A popup will appear on your phone. Tick the checkbox and press Allow.

Type `adb reboot bootloader` in the terminal/cmd. Your phone should restart to the bootloader. Then execute `fastboot oem unlock`. A dialog should appear on your phone. Using the volume down key navigate to the lower button(Unlock the bootloader) and press the power button. It should start to reset the phone and boot to the stock OS. Setup the OS normally and enable USB debugging again.

**For windows users:** if the fastboot commands doesn't work, Download [this driver](https://t.me/FuckNvidia/25) and install it(extract the zip somewhere you remember. open device manager, right click on the unknown device and choose update driver, then click on manual. and choose the path where you extracted the zip.

## **Flashing the recovery**

Download the desired recovery/rom recovery. execute `adb reboot bootloader`. Do `fastboot flash recovery [/path/to/recovery].img`. and then `fastboot reboot-recovery`. It should open up the newly installed recovery. If the touch works use it and if not navigate around with volume/power buttons.

## **Flashing the ROM**

In the recovery navigate to apply update and choose sideloading. Then on you PC do `adb sideload [/path/to/rom/file]`. And wait for it to finish. If it gets stuck on 46% don't worry it's ok. press reboot on your phone and Boom! enjoy the new ROM.
