# Survivor Buddy Head Web Application Setup

## Web Server

Make sure you have npm and node installed.
Useful link here: https://medium.com/@iam_vinojan/how-to-install-node-js-and-npm-using-node-version-manager-nvm-143165b16ce1

Install http-server with the following command
`npm install -g http-server`

Then,
`cd /to/sb_web/`

And run
`http-server -S -C cert.pem -o --key key.pem`

Insert picture of http-server

## ROSbridge suite

Install ROSbridge suite with:
`sudo apt install -y ros-noetic-rosbridge-suite`

Then.
`cd /to/sb_web/`

Open rb_server.launch.

Change the address to the IP address that is shown by http-server.
Also change the certfile and keyfile paths to be the absolute path location to the certfile and keyfile on your installation of Ubuntu.

Insert picture of lines to change

And run
`roslauch rb_server.launch`

Insert output of rosbridge server

## Opening the web app

Find the IP address of the device that is hosting the http-server and the rosbridge server. The IP address should appear at the output when each of the servers were started.

INSERT PICTURE HERE

Once that IP address has been found, on the device that will be serving as the head (phone on the Survivor Buddy or your own phone or computer when testing), open up the IP address and port of the rosbridge server. If my IP were 10.211.55.4 and the port were 9093 for the rosbridge server, I would navigate to `https://10.211.55.4:9093`.

Once there, you should see a warning that says that it is not secure- click on advanced or more information and continue to the site.

INSERT PICTURE OF WARNING HERE

You should then see a blue screen that looks like the following.

INSERT PICTURE OF AUTOBAHN

Then navigate back to the IP address and port of the http-server and the sb_head html. Again, if my IP address were 10.211.55.4, I would navigate to `https://10.211.55.4:8080/sb_head.html`.

Then click connect to ROSbridge server, making sure the IP address and port in the fields are the correct address and port for the rosbridge server. Once connected, click on the record button to start transmitting the camera and audio data wirelessly to the instance of ROS running on your computer.
