# ecs87's Simple DirecTV Remote Control App

## Usage

### PhoneGap CLI

    $ phonegap create my-app --template blank

### Desktop/Mobile instructions

In your browser (or phone), open the file:

    /www/index.html

If you are on a iOS device or in Internet Explorer you won't be able to use the auto-scanning feature for picking up your DirecTV receiver. You will need to enter in your DirecTV IP manually (if the section I commented out on line 41 is uncommented for those of you using iOS devices or IE, the process will hang indefinitely if you try to autoscan.)

If you are on an Android device or are using a browser other than IE, feel free to remove the forced "display:none;" at line 41 to use the auto scanning option.

If you want your vol up, vol down, and mute buttons to work, please refer to my <a href="https://github.com/ecs87/Java-Infrared-REST-API-Server-for-Android">Android IR (infared) REST API server</a> for devices with IR blasters. You will need to enter your endpoint API information into the "Advanced IR Endpoint Options" of the settings for this to work through the remote.

You can also piggyback both the DirecTV power off API and your IR Rest API together to shut off two devices at once (IE: shutting off your DirecTV receiver and TV at the same time).

Here's an example of an Advanced IR Endpoint (I have a REST API IR server running on my S5 at 192.168.1.33:8080. To power on my LG TV I send: http://192.168.1.33:8080/powerOn to send an IR signal to turn it on):

IP address: 192.168.1.33

Port: 8080

ON endpoint: /powerOn

OFF endpoint: /powerOff

Vol+ endpoint: /volUp

Vol- endpoint: /volDown

Mute endpoint: /muteVol
