debugchannel-javascript-client
=======================

javascript client for DebugChannel.

## Install via Bower ##

javascript-client is available through bower with the command
```
bower install debugchannel-javascript-client
```

## Install via Github ##

javascript-client is hosted on GitHub and can be used just like any other local library.

Download the repository by checking out the code:

````
git clone git@github.com:debugchannel/debugchannel-javascript-client.git
````
or by downloading a zip:

```
wget https://github.com/debugchannel/debugchannel-javascript-client/archive/0.1.2.zip
```

This will create a directory called `debugchannel-javascript-client`. You only need to include 1 file - located at `debugchannel-javascript-client/DebugChannel.js` - and you are done.

For example:
```
...
<script src="path/to/debugchannel-javascript-client/DebugChannel.js"></script>
...
```

How to use javascript-client
============================

Including the DebugChannel.js script adds the constructor DebugChannel to the global namespace.
An instance of DebugChannel has 2 methods:
- .explore() displays a pretty representation of object graphs
- .clear() removes all messages from channel

## Initialisation ##

```
var d = new DebugChannel("192.168.2.158", "greeting");
```
Creates a new client `d` pointing at the DebugChannel server found at `192.168.2.158` and displays messages on the channel `greeting`. To view your messages just point a browser at `http://192.166.2.158/greeting`.
The explore method can be used on any value:
```
d.explore("Hello World"); // 1
d.explore(23); // 2
d.explore({name: "John", age: 32)); // 3
d.explore([1,"hello", {name: "John", age: 32}]); // 4
```

## ->clear() ##
```
$d->clear()
````
Clears any messages currently being displayed on your channel. Great for 'resetting' a channel at the beginning of a new debugging flow.

