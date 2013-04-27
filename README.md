Jason's Asset Manager (JAM)
-------------------------------------------------------------------------------
Provides a simple shell utility for combining and minifing web assets.

# Usage

## As an Archive  

1. Click the big ol' **Downloads** button next to the project description.
1. Extract the archive to `~/jam` or where ever it is you keep these sorts of 
things.

## As a git project

1. `cd ~` or where ever it is you keep these sorts of things.
1. `$ git clone git://github.com/jasonsnider/jam.git`

Make the build file executable 

    chmod +x build
    
Then run the demo cofiguration to ge ta feel for how it works. Assuming the jam
directory is loacted at ~/jam. Simply call the build script and supply the name
of a configuration file.

    cd ~/jam
    ./build demo
    
Look in the compiled directory you will see 4 files; 2 .js and 2 .css. 1 file 
of each type is minified and 1 file of each type is just a merge of all the 
specified files. The file names consist of the configuration name, a timestamp
a string denoting minification and the file extension.
    
To create your own configuration, just add a file of the desired name to the 
config directory. This file must contain 2 settings; COMPILETO and FILES. 
Additionally the config file may simply call an external file. I like this
option because it the config file to be maintained as a part of the project
that is using it.

COMPILETO is the path upon which you would like jam to write the combined and 
minified files FILES is an array of the paths you would like to combine and 
minify. The paths may be either relative or absolute. 

### Sample configuration

~/jam/config/demo

	#!/bin/bash
    COMPILETO="compiled"
	FILES="
		demo/source/css/a.css 
		demo/source/css/b.css
		demo/source/css/c.css
		demo/source/js/1.js
		demo/source/js/2.js
		demo/source/js/3.js
	"

## Credits

* [Jason Snider](https://github.com/jasonsnider) - Core Development
* [Lyubomir Dimov](https://github.com/ldimov) - Core Development

## License

Licensed under [The MIT License](http://www.opensource.org/licenses/mit-license.php)

## Copyright

Copyright 2013, [Jason D Snider](https://jasonsnider.com)