#FakeMii

A simple proxy tamper designed by Lectem for 3DS/N3DS, with small adjustments to use with the Nintendo Switch.
 
This proxy will fake the Nintendo connection test so that you can pass the test on a network without internet access, any other page will send a 404 error. 
It is useful if you want to use LAN services (such as FTP) without having/providing internet access.


##HOWTO


###Run FakeMii
1. Install [Node.js](http://nodejs.org/)
2. Run `FakeMii.js` or execute run.bat
3. The server should now be running

###Set up the Nintendo Switch
1. Get your computer's local IP address.
  1. On Windows : Open a cmd.exe and type `ipconfig`
  2. On linux : `ip addr show`
2. Configure your Switch's proxy settings.
  1. Go to your Switch's internet settings (Internet Settings->Selection connection->Change Settings)
  2. Set Proxy Settings to On
  3. Set Server as the IP address of your computer
  4. Set Port to 3000
3. Save your settings and connect to the network, you should now pass the test!


###Running a WLAN on windows (can be used even while connected to another AP via WIFI)
1. Configure your hosted network if never done before
  1. Open a cmd.exe as administrator (You need administrator privileges for netsh)
  2. Use `netsh wlan set hostednetwork mode=allow ssid=MYWLANNAME key=MYWLANPASSWORD keyUsage=persistent`
2. Start the hosted network with `netsh wlan start hostednetwork`
3. Stop the hosted network with `netsh wlan stop hostednetwork`

###Hosting a WLAN on linux
This is usually done with `hostapd`.
An overview of the tool can be found [here](https://wiki.archlinux.org/index.php/Software_access_point)

Thanks to cell9 of #3dsdev for providing his own server script
