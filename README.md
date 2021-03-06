#iD-socket
## Simple Socket manager for supporting realtime communication in iD editor.

https://github.com/f3rnando/riD/tree/realtime-changes

### Demo
http://id-editor.fernando.com.ar

## Installation
iD-socket can be installed in a server separated from the iD editor itself or not, as socket.io supports CORS by default. Be sure you first have riD (iD fork) cloned and running by doing:

	$ git clone https://github.com/f3rnando/riD.git
	$ cd riD/
	$ python -m SimpleHTTPServer

(At this point, the cloned iD fork, has the demo iD-socket server url, so it will work stand alone)

Once you install iD-socket somewhere:

	$ git clone https://github.com/f3rnando/iD-socket.git
	$ cd iD-socket
	$ npm install

## Start

	$ DEBUG="*" node app.js

Or you can also override the default 80 port with env var called PORT:

	$ DEBUG="*" PORT="3000" node app.js

## Usage
Once you know the host of your iD-socket, you can change it in the riD index.html file, at the bottom script tag:


		var socket_connect = function (room) {
				return io('http://url-to-id-socket:80', {
					query: 'r_var='+room
				});
			}
