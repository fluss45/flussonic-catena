#flussonic offline - catena 

#cracked
#flussonic
#lifetime
Crack Flussonic lifetime and unlimited servers works

l4|8Ku8ypPgOUySHysCdkFHW0|r6BzpmVPpjgKpn9IunpFp6lLbCZOp3

l4|aO4RO2ZdLEzHAdH46n6iD0|r6BzpmVPpjgKpn9IunpFp6lLbCZOp3

#Skype - kaul.thetv
Flussonic streaming software with Iptv camera
Catena is a platform (web control panel, IPTV middleware) that enables you to manage live streams, VOD assets, customers and resellers via a unified web interface. Catena is not a video streamer but it uses one or more Flussonic Media Servers as streamers.

Note. Flussonic Catena was intended to replace the Flussonic's IPTV plugin and add more functionality.

With Flussonic Catena you can:

#flussonic
#camera
#offline
#dvr
#watcher
#unlimited servers

Manage thousands of stream sources
Manage subscribers
Manage TV packages
Provide a web UI for playing TV content
Provide m3u playlists to your subscribers
Protect streams from restreaming
Manage a group of Flussonic streamers by using a unique Pipelines solution
Load balance streams among a group of servers
Load balance clients among Edge servers
The huge benefit Catena offers is that you can keep all streams' and users' data in a centralized database and don't have to worry about backing up each streamer. Also, with the Catena's single unified web interface you can conveniently manage your entire service.

Installing Flussonic Catena
Catena requires PostgreSQL 10+ and Ubuntu 18.04 and running on http/80 and https/443 ports. PostgreSQL is installed automatically with Catena.

Note: Make sure that you are not running any web or streaming services on the server where you want to install Catena.

To install Flussonic Catena and PostgreSQL on Ubuntu 18.04, run this command in the Linux console (command line):



Administrator's login and password will be generated during the installation process:

*******************************************



Login: admin@example.com
Password: XH2jx5xx



*******************************************

Catena password

Now open http://1.1.1.1/admin and log in with the generated credentials.

Note: Replace 1.1.1.1 with real IP address of your server.

After logging in you'll see the admin UI:

Catena first login

Learn more about system requirements, updating Catena, and resetting the password

Configuring Flussonic Catena
Flussonic Catena works with one or more Flussonic Media Servers as streamers. All connected streamers use Catena as the authorization backend and main source of truth concerning the configuration.

This is why it is important to serve Catena on an Internet server (VPS or dedicated server) with a static IP address and a real domain name. So the first configuration step is setting the external address of Flussonic Catena.

To change the Catena's external URL:

Go the Config tab of the admin UI and edit the URL.

It can be just the IP address of the server where you install Catena, in http://123.123.123.123, but we strongly recommend using domain names like in http://mycatena.example.com.

Catena set hostname

If you have specified a valid fully qualified domain name, the message about the hostname will not appear, and your streams will be protected via the Catena database.

Now you can add servers, streams, pipelines, subscribers, and packages to Catena.

Let's Encrypt and Catena
The Let's Encrypt service automatically provides certificates for setting up HTTPS in automatic mode. Catena has built-in support for Let's Encrypt — no need to install extra packages and manually configure your web server.

To get a Let's Encrypt certificate:
Go the Config tab and click the Issue LetsEncrypt certificate button:

Catena config tab

If the certificate was obtained successfully, you will see a message about it:

Catena successful lets encrypt

To apply the changes, restart Catena via the command line:

service catena restart

After Catena has restarted, go to the Config tab in the web UI and change the protocol from http to https.

Importing the configuration from XC
We would be glad to help you import your sources and customers from any other IPTV panel or IPTV middleware. At the moment, we offer the HTTP API and XC Migration tool (MySQL database client). Learn more in Migrating data into Catena

For support purposes, we have a utility that mends the Catena database. If some error occured during import and the database was corrupted, you can reinitialize your Flussonic Catena instance by using the following commands:
Code:
/opt/catena/bin/setup reset
/opt/catena/bin/setup init
After running /opt/catena/bin/setup init you'll see a new password for the admin UI.

Customer Portal and M3U playlists
Your subscribers can log in to Customer Portal, where they can get M3U playlists, payment information, and play available TV channels in the browser.

The Customer Portal link is http://catena-ip/. Please don't confuse it with the admin UI link: http://catena-ip/admin.

Catena customer portal

Catena web player
Customers can manually reset playback tokens by clicking Reset token. This button can be useful if someone steals your link.
