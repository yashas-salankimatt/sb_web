# Survivor Buddy Head Web Application Setup

## Web Server

Make sure you have npm installed.

Install http-server with the following command
`npm install -g http-server`

Then,
`cd /to/sb_web/`

And run
`http-server -S -C cert.pem -o --key key.pem`

## ROSbridge suite

Install ROSbridge suite with:
`sudo apt install -y ros-noetic-rosbridge-suite`

Then.
`cd /to/sb_web/`

And run

```
roslauch rb_server.launch
```
