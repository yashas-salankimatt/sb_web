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

![http-server-launch-image](images/http-server-launch.png "Output of http-server command")

## ROSbridge suite

Install ROSbridge suite with:
`sudo apt install -y ros-noetic-rosbridge-suite`

Then,
`cd /to/sb_web/`

Open rb_server.launch.

Change the address to the IP address that is shown by http-server.
Also change the certfile and keyfile paths to be the absolute path location to the certfile and keyfile on your installation of Ubuntu.

![launchfile-args-to-change](images/launchfile-args-to-change.png "Change the address, certfile, and keyfile args")

And run
`roslauch rb_server.launch`

![rosbridge-launch](images/rosbridge-launch.png "Output of launching the rosbridge")

## Opening the web app

Find the IP address of the device that is hosting the http-server and the rosbridge server. The IP address should appear at the output when each of the servers were started.

Once that IP address has been found, on the device that will be serving as the head (phone on the Survivor Buddy or your own phone or computer when testing), open up the IP address and port of the rosbridge server. If my IP were 10.229.48.167 and the port were 9093 for the rosbridge server, I would navigate to `https://10.229.48.167:9093`.

Once there, you should see a warning that says that it is not secure- click on advanced or more information and continue to the site.

![chrome-warning](images/warning.jpg "Chrome warning")

You should then see a blue screen that looks like the following.

![autobahn-screen](images/autobahn.jpg "Success after going through chrome warning")

Then navigate back to the IP address and port of the http-server and the sb_head html. Again, if my IP address were 10.229.48.167, I would navigate to `https://10.229.48.167:8080/sb_head.html`.

![successful-load](images/webpage-success.jpg "Successful webpage load")

Then click connect to ROSbridge server, making sure the IP address and port in the fields are the correct address and port for the rosbridge server. Once connected, click on the record button to start transmitting the camera and audio data wirelessly to the instance of ROS running on your computer.

![rosbridge-success](images/rosbridge-client-connected.png "Successfully connected to rosbridge server")
