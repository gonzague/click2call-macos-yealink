# click2call-macos-yealink
A simple Mac OS Automator script to place a phone call using a VOIP Yealink Phone. The notifications are in French but there isnt much to translate. How does it work? Plain simple: Yealink phones can be instructed to perform certain actions by calling their webserver and specifying parameters. You can place a call, end a call etc.. Here we are just placing a call.

Please not : this is very BASIC and I'm not a developer so there is much to improve. You're welcome to do so.

How to get it working and what do you need?

- Mac OS (a recent version I assume)
- a SIP Phone from Yealink such as the T46G (this is what I used)
- administrative access to the Yealink phone (login/password)

First of, you might wanna check the settings of your Yealink phone. Find its IP adress and browse it in your prefered browser. 

Go to Features and then Remote Control. For example the URL to this page could be https://192.168.X.X/servlet?m=mod_data&p=features-remotecontrl&q=load

On this page, check that Action URI Server IP is either set to your computer's IP or what ever you wanna use to send the commands from your script. This section of the phone settings is what allows it to be remotely "controlled".

Then download and open with a right clic (beware : do not select the option to install it yet ) - choosing "Open with => Automator" - the Automator script. You *have* to edit it.. to specify the IP of your phone and its password. The part you have to change is :
curl -k -O https://admin:pass@192.168.9.24/servlet?key=number=$numero
 .. where you'll change the "pass" part and the IP to the one of your phone.

 Once done you can save your changes. You should now be able to right click a phone number in your Mac and then in the Services menu, find your "quick action" to place the call to this number. 