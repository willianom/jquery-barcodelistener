
# Introduction #

This guide will help you to seup and use correctly the BarcodeListener plugin for jQuery.

# Setup the scanner #
It is important to setup correctly your barcode scanner.
First of all you have to add some header characters to the output, before the code. Most of scanners should do it. For example the header characters of my scanner are:
```
§~
```
these are not common characters. I did that because the BarcodeListener plugin listen every input but catch only the one that start whith these characters; so do not use letters or number that are really common when you write something.

The last point is to set the scanner to hit the ENTER button after the code to let the plugin read the code and lauch the user's function.

# Setup the plugin #

## Download ##
First of all download the [last version of jQuery](http://code.google.com/p/jqueryjs/downloads/list) and the [last version of BarcodeListener](http://code.google.com/p/jquery-barcodelistener/downloads/list).

**Interesting links for this section:**
  * [last version of jQuery](http://code.google.com/p/jqueryjs/downloads/list)
  * [last version of BarcodeListener](http://code.google.com/p/jquery-barcodelistener/downloads/list)


## Include ##
Now you have to include the scripts in your HTML document. The code is:
```
<script type="text/javascript" src="[URL to jQuery code]"></script>
<script type="text/javascript" src="[URL to BarcodeListener code]"></script>
```


## Find your way ##
There are two ways to setup the plugin:
  * [using the wizard](http://www.gregoriopellegrino.com/jquery-barcodelistener/) (for beginners);
  * [setting the plugin your own](#Setting_the_plugin_your_own.md) (for experts).

### Setting the plugin your own ###
To call the plugin use this code:
```
<script type="text/javascript">
	$(document).BarcodeListener(characters, function(code) {
	    // YOUR FUNCTION HERE
            // for example:
            alert(code);
	});
    });
</script>
```
The option _characters_ is an array made of arrays. The right way to set up it is:
```
<script type="text/javascript">
char0 = new Array("§", "32");
char1 = new Array("˜", "732");
characters = new Array(char0, char1);
</script>
```
For every character you have to make an array with two elements:
  * the first is the character;
  * the second id the eventcode (the e.which code ouputed by the function [keypress()](http://docs.jquery.com/Events/keypress#fn)).

You can add a lot of header characters: there's no limit!


# Test #
That's all! Your code should be like this:
```
<script type="text/javascript" src="_javascript/jquery-1.3.2.js"></script>
<script type="text/javascript" src="_javascript/jquery.barcodelistener.js"></script>
<script type="text/javascript">
    $(document).ready(function() {
	char0 = new Array("§", "32");
	char1 = new Array("˜", "732");
	characters = new Array(char0, char1);
	$(document).BarcodeListener(characters, function(code) {
	    // YOUR FUNCTION HERE
            // for example:
            alert(code);
	});
    });
</script>
```
Try and use it!

# Contacts #
For any problem send a message to the [Discussion group](http://groups.google.com/group/jquery-barcodelistener), I will reply as quick as possible!