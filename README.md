Aligner-service
===============

## Text/Audio Alignment Server - Node.js REST Wrapper for a Python HTK wrapper

I found this great library for doing Forced Alignment. But it's wrapping the HTK library with command line Python. Still too messy and hard to integrate into our process. I want someone to write a simple Node/Express REST wrapper so that we can expose the functionality in a loosely coupled manner across the network or internet.

"Forced audio alignment" is the process of taking a block of text and an audio reading of the same text and then figuring out where the two line up. Fortunately, the hard part is already taken care up by some excellent libraries such as HTK. 

And this Python tool provides a command line wrapper simplifying HTK:

https://github.com/kylebgorman/Prosodylab-Aligner

https://www.dropbox.com/sh/sj3c3eqq6b4odza/nT1nfT6tx0

But all that command line Python stuff is still too local and messy. I want it wrapped with a nice clean REST API -- so that we can pass in and receive back JSON objects over the network. We'll probably be running it on a Mac desktop somewhere. We think it will be easiest to just use Node/Express to wrap the Python wrapper. But you take a look and decide if it would be easier to just wrap HTK directly.

### Note: 

* Audio alignment can take some processing time so we need some kind of promises-compatible alignment call with progress status in the API. Perhaps some queueing of some sort to allow for batch or multiple asynchronous calls.

* If the alignment fails because of missing vocabulary, this should be saved and reported back. The API should support adding the missing vocabulary and training files, as the Python API does.

So, take a look at the Github project and let me know how you would implement this.

## Skills required: 

Express JS, Javascript, node.js, Python
