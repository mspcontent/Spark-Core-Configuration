<a name="Title" />
# Spark Core Configuration #

<a name="overview" />
## Overview ##

This walk through helps you configure your Spark Core on a Windows Machine.  If you would prefer to configure your spark core using your iOS or Android device, you can follow the instructions on the Spark.IO website: http://docs.spark.io/start/ and http://docs.spark.io/connect/ 

The steps here are also described in various locations in the Spark documentation.  You should always refer to the Spark documentation for the latest instructions. You can find them at http://docs.spark.io 

<a name="inventory" />
## Inventory ##

To follow the steps in this walk through, you'll need: 

![00010-Inventory](images/00010-inventory.png?raw=true "Inventory")

1. Spark Core (Breadboard optional)
2. USB Cable (One is included with your Spark Core Dev Kit)
3. Windows Computer that has access to the Internet

<a name="steps" />
## Steps ##

To successfully configure, claim, and deploy code to your Spark Core, there are a few steps you'll need to take:

1. [Install the Spark Core USB Driver for Windows](#install-the-spark-core-usb-driver-for-windows)
1. [Install Node.js](#install-nodejs)
1. [Install the Spark-CLI](#install-the-spark-cli)
1. [Create a Spark Build account](#create-a-spark-build-account)
1. [Claim your Spark Core](#claim-your-spark-core)
1. [Configure the Spark Core's WiFi ](#configure-the-spark-cores-wifi)
1. [Identify your Spark Core](#identify-your-spark-core)
1. [Deploy code to your Spark Core ](#identify-your-spark-core)
1. [Remove Your Spark Core from Your Account](#remove-your-spark-core-from-your-account)

---

<a name="install-the-spark-core-usb-driver-for-windows" />
## Install the Spark Core USB Driver for Windows ##

The first time you connect a Spark Core to your Windows Computer, you need to install the USB Driver for the Spark Core.  You only need to do this once.  Once the driver has been installed successfully you can connect any number of Spark Cores any number of times to your computer in the future. 

1. Go to the "[Connecting Your Core](http://docs.spark.io/connect/)" page and click on the **"[Windows driver for Spark Core](https://s3.amazonaws.com/spark-website/Spark.zip)"** link (or just use this link: https://s3.amazonaws.com/spark-website/Spark.zip) 

	![01010-DownloadLink](images/01010-downloadlink.png?raw=true "Download Link")

1. When prompted, save the .zip file to your downloads folder:

	![01020-SaveFile](images/01020-savefile.png?raw=true "Save File")

1. Right-click on the downloaded .zip file, and select **"Properties"** from the pop-up menu:

	![01030-Properties](images/01030-properties.png?raw=true "Properties")

1. In the **"Sparik.zip Properties"** window, click the **"Unblock"** button, then click **"OK"**:

	![01040-Unblock](images/01040-unblock.png?raw=true "Unblock")

1. Next, extract the .zip file to a folder off the root of your C: Drive:

	![01050-ExtractAll](images/01050-extractall.png?raw=true "Extract All")

	![01060-ExtractToCDrive](images/01060-extracttocdrive.png?raw=true "Extract to C Drive")

1. Confirm the contents of the extracted folder:

	![01070-SparkFolder](images/01070-sparkfolder.png?raw=true "Spark Folder")

	![01080-SparkDriver](images/01080-sparkdriver.png?raw=true "Spark Driver")

1. Connect the Spark Core to your computer using the USB cable

	![01090-ConnectSparkViaUSB](images/01090-connectsparkviausb.png?raw=true "Connect Spark Core via USB")

1. Ensure the that Spark Core is in **[Listening Mode](http://docs.spark.io/connect/#connecting-your-core-listening-mode)**. You can tell if your Spark Core is in **"Listening Mode"** if the large LED on it is flashing blue, on and off (not fading in and out) ([video](https://vine.co/v/hFHPMue5lgd)). If your Spark Core isn't in Listening Mode you can press and hold the **"Mode"** button until the LED starts flashing blue ([video](https://vine.co/v/hFHlpBDELeU)).  

	![05010-ListeningMode](images/05010-listeningmode.png?raw=true "Listening Mode")



1. Open **"Device Manager"** on your computer (right-click on the Start menu button, and select **"Device Manager"** from the pop-up menu):

	![01100-OpenDeviceManager](images/01100-opendevicemanager.png?raw=true "Open Device Manager")

1. Under **"Other Devices"** you should see a **"Spark Core with WiFi"** entry:

	> **Note**: You may not see the exact name **"Spark Core with WiFi"**, or it may appear under **"Ports (COM & LPT)"** (this seems to happen in Windows 10 Technical Preview).  If you don't see the Spark core with the missing driver as shown below, look for a different name, or under the **"Ports (COM & LPT)"** header for it instead.

	![01110-SparkCoreMissingDriver](images/01110-sparkcoremissingdriver.png?raw=true "Spark Core Missing Driver")

1. Right click on the **"Spark Core with Wifi" device, and select **"Update Driver Software..."** from the pop-up menu:

	![01120-UpdateDriver](images/01120-updatedriver.png?raw=true "Update Driver")
	
1. In the **"Update Driver Software - Spark Core with WiFi"** window, click the **"Browse my computer for driver software"** option

	![01130-Browse](images/01130-browse.png?raw=true "Browse")

1. Browse the to the folder where you extracted the Spark USB driver previously, then click **"Next"**:

	![01140-BrowseToSparkFolder](images/01140-browsetosparkfolder.png?raw=true "Browse To Spark Folder")

1. In the **"Windows Security"** dialog, click **"Install"** to confirm the installation:

	![01150-Install](images/01150-instal.png?raw=true "Install")

1. Confirm the driver was installed correctly, and click **"Close"**

	![01160-Close](images/01160-close.png?raw=true "Close")

1. Back in the **"Device Manager"** window, under **"Ports (COM & LPT)"** you should now see the **"Spark Core with Wifi and Arduino Compatability (COM3)"** listed, although your COM port number may vary.  Note the COM port that your core is connected to in case you need to connect to it in the future.  

	![01170-SparkCOMPort](images/01170-sparkcomport.png?raw=true "Spark Core COM Port")

---

<a name="install-nodejs" />
## Install Node.js ##

You can configure your Spark Core using a Node.js module that is provided by Spark.  However, this means that you first must install Node.js on your computer.  This is really easy, quick, and free. 

1. Open [nodejs.org](http://nodejs.org) in your browser, click the big **"Install"** link, and when prompted, run the downloaded installer:

	![02010-RunNodeInstaller](images/02010-runnodeinstaller.png?raw=true "Run Node.js Installer")

1. Follow the prompts of the installer, accepting all the defaults.

	![02020-NodeJs01](images/02020-nodejs01.png?raw=true "Node.js Installation 01")

	![02030-NodeJS02](images/02030-nodejs02.png?raw=true "Node.js Installation 02")

	![02040-NodeJS03](images/02040-nodejs03.png?raw=true "Node.js Installation 03")

	> **Note:** Make sure to leave the **"Add to PATH"** option enabled.  This will let you run Node from any command prompt.  

	![02050-NodeJS04](images/02050-nodejs04.png?raw=true "Node.js Installation 04")

	![02060-NodeJS05](images/02060-nodejs05.png?raw=true "Node.js Installation 05")

	> **Note:** If you are prompted to confirm the installation, do so. 

	![02070-NodeJS07](images/02070-nodejs07.png?raw=true "Node.js Installation 07")

---

<a name="install-the-spark-cli" />
## Install the Spark-CLI ##

Now that we have Node.js installed, we can install the Spark-cli.  

1. Open up a Windows Command Prompt as Administrator by right-clicking on your Start Menu, and selecting **"Command Prompt (Admin)"** from the pop-up menu:

	![03010-OpenCommandPrompt](images/03010-opencommandprompt.png?raw=true "Open Command Prompt as Admin")

1. At the command prompt, type:

	`npm install -g spark-cli` and press `ENTER`

	![03020-SparkCLIInstall](images/03020-sparkcliinstall.png?raw=true "Spark-CLI Installation")

1. Once you have installed the spark-cli, you can verify its version using:

	`npm list -g spark-cli`

	![03030-ListSparkCLI](images/03030-listsparkcli.png?raw=true "List Spark-CLI")

1. And finally, if you need to update to the latest version you can run:

	`npm update -g spark-cli`

	> **Note:** In the screen shot below, no update was needed so you see no output from the command.

	![03040-UpdateSparkCLI](images/03040-updatesparkcli.png?raw=true "Update Spark-CLI")

---

<a name="create-a-spark-build-account" />
## Create a Spark Build account ##

Before you can "claim" your Spark Core, you need an account with Spark.  

1. Open your [Spark Build](http://spark.io/build) (http://spark.io/build) in your browser.  Enter your **email address**, and the **password** you want to use, then click the **"SIGN UP"** button:

	![04010-Register](images/04010-register.png?raw=true "Register for Spark Build")

1. You will then be signed into **"Spark Build"**, Spark's web based development environment.  Initially, it asks you to name your first app.  We'll return to do this later. For now you can just leave the browser:

	![04020-FirstApp](images/04020-firstapp.png?raw=true "First App")

---

<a name="claim-your-spark-core" />
## Claim your Spark Core ##

Now that you have a Spark account, you can "claim" your Spark Core.  Claiming a Spark Core ensures that only you can deploy code to that Spark Core and that you have a way to securely access your Spark Core over the internet. 

1. Ensure the that Spark Core is connected to your computer via the USB cable and is in **[Listening Mode](http://docs.spark.io/connect/#connecting-your-core-listening-mode)**. You can tell if your Spark Core is in **"Listening Mode"** if the large LED on it is flashing blue, on and off (not fading in and out) ([video](https://vine.co/v/hFHPMue5lgd)). If your Spark Core isn't in Listening Mode you can press and hold the **"Mode"** button until the LED starts flashing blue ([video](https://vine.co/v/hFHlpBDELeU)).  

	![05010-ListeningMode](images/05010-listeningmode.png?raw=true "Listening Mode")

1. It's also important to ensure that your Spark Core hasn't already been claimed.  If you have claimed it previously you will need to first remove the core from your account before you can claim it again.  If somebody else has already claimed the core, you will need to work with that person to remove the core from their account before you can claim it.  If you need to, you can refer to the **"[Remove Your Spark Core from Your Account](#remove-your-spark-core-from-your-account)"** topic for help.

1. Open an administrative command prompt as described before (right-click on the Start Menu and select **"Command Prompt (Admin)"** from the pop-up menu). In the command prompt window, enter:

	`spark setup`

1. Then enter with the email address and password you used when creating your Spark account previously:

	> **Note:** Once you are logged in your Spark Core's **"Core ID"** will be displayed.  The **"Core ID"** is unique to each Spark Core and identifies each spark core individually.  

	![05020-SparkSetup](images/05020-sparksetup.png?raw=true "Spark Setup")

1. Next, follow the prompts to enter your WiFi networks SSID, Security Mode, and Password:

	> **Note:** You need to know your WiFi information.  You can't claim your Core without first connecting it to the Internet via WiFi.  You also need a WiFi network with known SSID, Security Mode and Password.  WiFi networks that require corporate credentials, or a secondary web based login won't work with the Spark Core.  If your current WiFi doesn't work consider using your phone as a hot spot if you can. 

	![05030-SetupWifi](images/05030-setupwifi.png?raw=true "Setup Wifi")

1. If your Spark Core has successfully connected to the WiFi network, it should begin **"[breathing cyan](https://vine.co/v/OmOAlMg17Y9)"**.  That means it should have a light blue (cyan color) that fades in and out (not flashing, fading).  When that happens press `ENTER`

1. Next, wait for your Spark Core to be **"[Shouting Rainbows](https://vine.co/v/hFdPKul226i)"**. when that happens, press `ENTER`

1. Then, when prompted, enter a name for your Spark Core (no spaces) and press `ENTER`.

1. Finally, once your core has been named, you will be asked if you want to log out or not (your choice), and your Spark Core's name and ID will be displayed:

	![05040-NameCore](images/05040-namecore.png?raw=true "Name Core")

---

<a name="configure-the-spark-cores-wifi" />
## Configure the Spark Core's WiFi ##

If you have a Spark Core that you have already claimed, but you need to change the WiFi network settings, it's super easy to do.  These steps assume that you have already installed the Windows USB Driver, Node.js and the Spark-cli as documented above.  

1. Ensure the that Spark Core is connected to your computer via the USB cable and is in **[Listening Mode](http://docs.spark.io/connect/#connecting-your-core-listening-mode)**. You can tell if your Spark Core is in **"Listening Mode"** if the large LED on it is flashing blue, on and off (not fading in and out) ([video](https://vine.co/v/hFHPMue5lgd)). If your Spark Core isn't in Listening Mode you can press and hold the **"Mode"** button until the LED starts flashing blue ([video](https://vine.co/v/hFHlpBDELeU)).  

	![05010-ListeningMode](images/05010-listeningmode.png?raw=true "Listening Mode")

1. Open up a Windows Command Prompt as Administrator by right-clicking on your Start Menu, and selecting **"Command Prompt (Admin)"** from the pop-up menu:

	![03010-OpenCommandPrompt](images/03010-opencommandprompt.png?raw=true "Open Command Prompt as Admin")

1. At the command prompt, enter `spark setup wifi` and follow the prompts to enter your new WiFi network configuration.  When all is done, ensure that your Spark Core is **"[breathing cyan](https://vine.co/v/OmOAlMg17Y9)"**.  

	![06010-SparkSetupWifi](images/06010-sparksetupwifi.png?raw=true "Spark Setup Wifi")

---

<a name="identify-your-spark-core" />
## Identify your Spark Core ##

You need to know your Spark Core's Core ID, or possibly Name to interact with it.  There are a number of ways that you can do this:

- Use Spark Build to show you your Cores and their ID's, and your account's Access Token
- Use the spark-cli's `spark list` command
- Use the spark-cli's `spark identify` command
- Or connect to the Spark Core over USB/Serial using a terminal program like PuTTY, and using the `i` command.

We'll show you each of those methods below:

1. The easiest way to identify your Spark Core is to login to [Spark Build](http://spark.io/build) with the account that claimed the Spark Core you wish to identify.  Then along the left hand side, click the Core's button and finally click the arrow next to your Spark Core's name to reveal it's Core ID:

	![06010-IdentifySparkCore](images/06010-identifysparkcore.png?raw=true "Identify Spark Core")

1. You often also need to know the Access Token for your Spark Account.  The Access Toekn is needed if you will be accessing the Spark Core via REST calls.  To get your Access Token, login to [Spark Build](http://spark.io/build), then click the **"Settings"** icon in the lower left corner.  From there you can view and copy your Access Token:

	![06020-AccessToken](images/06020-accesstoken.png?raw=true "Access Token")

1. Another handy method is to use the Spark-cli `spark list` ([docs](http://docs.spark.io/cli/#running-from-source-advanced-spark-list)) command to list all the Spark Cores claimed by your account, whether or not they are online, and to get each Spark Core's name and Core ID:

	![06030-SparkList](images/06030-sparklist.png?raw=true "Spark List")

1. You can also use the Spark-cli `spark identify` ([docs](http://docs.spark.io/cli/#running-from-source-advanced-spark-identify)) command to identify a spark that is connected to the computer and that is in **"[Listening Mode](http://docs.spark.io/connect/#connecting-your-core-listening-mode)"**

	![06034-SparkIdentify](images/06034-sparkidentify.png?raw=true "Spark Identify")

1. Lastly, you can connect a terminal program (like [PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty/)) to your Spark Core that is **[Listening Mode](http://docs.spark.io/connect/#connecting-your-core-listening-mode)**, and using the **"i"** command to identify the Spark Core.  Use the COM Port that your Spark Core is listening on (you can find that in the Windows **"Device Manager"**, under **"Ports (COM & LPT)"**.  

	![01170-SparkCOMPort](images/01170-sparkcomport.png?raw=true "Spark Core COM Port")

	![06040-PuttyConnection](images/06040-puttyconnection.png?raw=true "PuTTY Connection")

	
	![06050-PuTTYCoreID](images/06050-puttycoreid.png?raw=true "PuTTY Core ID")

---

<a name="deploy-code-to-your-spark-core" />
## Deploy code to your Spark Core ##

Typically, you will use the **[Spark Build](http://spark.io/build)** web based code editor to write and deploy code to your Spark Core.  However, there are other options including using the Spark-CLI's `spark compile` ([link](http://docs.spark.io/cli/#running-from-source-advanced-spark-compile)) and `spark flash` ([link](http://docs.spark.io/cli/#running-from-source-advanced-spark-flash)) commands, or the new [Spark Dev](https://www.spark.io/dev) development environment.  For this walkthrough though we'll focus on the web based **[Spark Build](http://spark.io/build)** environment.

1. Open **[Spark Build](http://spark.io/build)** in your web browser, and log in with the Spark account your created previously.  If this is the first time you have written an app for your spark core, you will be presented with a blank app, and prompted to enter a name for the new app:

	![07010-NewApp](images/07010-newapp.png?raw=true "New App ")

1. You can see the default app's `setup()` and `loop()` methods in the code window.  You can learn all about writing apps for the Spark Core by reading the [documentation](http://docs.spark.io/).  For this walkthrough though, we'll use the sample **"BINK AN LED"** app that is provided in the editor.  Click the **"BLINK AN LED"** example app to open it:

	![07020-BlinkAppLink](images/07020-blinkapplink.png?raw=true "Blink App Link")

1. Then click the **"FORK THIS EXAMPLE"** button to create your own copy of the Blink App:

	![07030-ForkBlink](images/07030-forkblink.png?raw=true "Fork the Blink Example")

1. You can modify the code in the code window if needed (although for this example, don't make any changes).  When you are ready to deploy your code to your Spark Core, you first need to Save your code:

	![07040-SaveApp](images/07040-saveap.png?raw=true "Save App")

1. Then you can verify your code to ensure that it compiles

	![07050-VerifyApp](images/07050-verifyap.png?raw=true "Verify App")

1. If the app compiles successfully, you should see a status message along the bottom like this:

	![07060-SuccessStatus](images/07060-successstatus.png?raw=true "Success Status")

1. If instead, you have any errors, read the errors, fix them, and try verifying again.  For example, in the following screenshot, the error states that at line 11, character 1, it found a '}' rather than a ';'.  That means I forgot to put a semi-colon at the end of my statement on line 10.  I can fix that and verify again:

	![07070-CompileError](images/07070-compileerror.png?raw=true "Compile Error")

1. Next, if you have multiple cores claimed by your account you need to ensure that you will be deploying code to the right core.  Click the Core's link along the left, then click on the **"Star"** icon next to the core that you want to flash to select it as the one to flash.  If you can't select your core for flashing ensure that is is powered on and **"[breathing cyan](https://vine.co/v/OmOAlMg17Y9)"**:

	![07080-SelectCore](images/07080-selectcore.png?raw=true "Select Core to Flash")

1. Finally, you can deploy, or "Flash" your code to the core.  Click the **"Flash"** button along the left.  Watch the Spark Core's RGB LED and you should see it begin flashing purple rapidly.  Once the update is done, it will flash gree for a bit, then reconnect to the WiFi network and end with **"[breathing cyan](https://vine.co/v/OmOAlMg17Y9)"**. You can watch the status along the bottom of the window for info. 

	![07090-FlashApp](images/07090-flashap.png?raw=true "Flash App")

1. Your sketch should now be running.  In the case of the blink app, that means that the small blue led on the Spark Core should be blinking on or off every second:

	![07100-BlinkingLed](images/07100-blinkingled.png?raw=true "Blinking LED")

---

<a name="remove-your-spark-core-from-your-account" />
## Remove Your Spark Core from Your Account ##

If you have claimed a spark core in an account and wish to use it in another account, or to pass along to another developer, you first need to **"Remove"** the spark core from your account. 

There are a couple of ways to do this:

1. You can use the Spark-cli `spark core remove` command ([link](http://docs.spark.io/cli/#running-from-source-advanced-spark-core-remove))

1. Or you can use the **"Spark Build"** web ide.  Simply login to [Spark Build](http://spark.io/build).  Click the **"Cores"** link along the left, and expand the arrow next to the name of the core you want to remove.  Finally, click the **"Remove"** button:

	![08010-RemoveCore](images/08010-removecore.png?raw=true "Remove Core")


1. After removing the core from your account, it is helpful to do a factory reset on it before you pass it along to the next developer, or re-use it with another account.  This makes sure the Spark Core is fresh and ready to re-configure.  You can follow the docs to [Factory Reset your Spark Core](http://docs.spark.io/connect/#appendix-factory-reset)









