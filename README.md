# loc - Location bookmarking script

```
Author: Amit Singh (xk0der) 
amit@xkoder.com
Licensed under MIT License
```

## LICENSE

Copyright (c) 2009, Amit Singh (xk0der)

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the "Software"), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.


## About the Script

The Location Bookmarking Script (LOC) makes it easy 
to bookmark folders and to move across bookmarked folders.


## Installing 

To install, run the following command from inside the folder
where the scripts loc, lcr and lcg are present.

```bash
$ sh install
```

This script will copy the files loc, lcr and lcg
to `/usr/local/bin`


## Using the Script

Here is how you'll typically use the loc script: 
(For detailed command explanation see section labeled 'syntax')

NOTE: Precede all location commands with a DOT (.)


### Bookmarking a location 

Suppose you are inside the following folder

```
/home/xk0der/SourceCode/loc
```

To bookmark this location, give the following command

```bash
$ . lcr loc
```

This will remember (bookmark) the location "/home/xk0der/SourceCode/loc"
by the name "loc". You can use any descriptive name you want.

If you do not specify the bookmark name "loc", the folder will be save
as the default bookmark.

```bash
$ . lcr
```

`lcr` is short for : location-remember


### Moving to a bookmarked location

Issue the following command to move to the bookmark named "loc"

```bash
$ . lcg loc
```

`lcg` stands for: location-go

`. lcg` supports auto-completion of stored bookmarks. Type `. lcg` and press `[TAB]` to view list of stored bookmarks.

Issuing the above command will take you to 
the bookmarked location by the name `"loc"`, in our case to `"/home/xk0der/SourceCode/loc"`

If we do not specify any bookmark name, you will be moved to the default bookmark which 
was saved using `$ . lcg` command.

```bash
$ . lcg
```

`. lcg` now supports auto-completion of bookmarks.

### Viewing all bookmarked locations

To view all your bookmarked locations issue the following command:

```bash
$ . lcs
```

`lcs` stands for: location-show

## Syntax

```bash
$ . loc rem [Location_NickName]
$ . loc go [Location_NickName]
$ . loc show
$ . loc clear [all|number]
```

Notice the DOT (`.`) before every command.
Technically it is only required with the "go" command,
But if you use it with all the "loc" it just makes it that bit
easier for your brain!! :)


## Shortcuts - lcs, lcr and lcg

`lcs`, `lcr` and `lcg` are shortcuts for `"loc show"`, `"loc rem"` and `"loc go"` commands respectively.


### Commands

#### `rem` - Remember the current working directory.

Optionally you may specify a short nick name

_Example:_
```bash
(/etc/mail)$ . loc rem mail
(/home/xk0der)$ . loc rem
```

The first command will save `/etc/mail` as mail
Second will store `/home/xk0der` as default location

#### `go`  - Go will move you to the locations you saved using 'rem'
 
_Example:_
```bash
$ . loc go mail
$ . loc go
```
    
Taking previous examples into consideration the first
will take you to `/etc/mail`, the second will take you to `/home/xk0der`

#### `show`  - This will list down a numbered list of remembered (saved) locations
 
_Example:_ 
```bash
$ . loc show
```
    
Output format is
```
    indexNumber [nickName]: storedLocation
```    
    
_Example output:_
```
    1 [default]: /usr/src" 
    2 [mail]: /etc/mail
    3 [share]: /usr/local/share
```    

#### `clear` - Clears saved locations
    
You need to either specify 'all' after this command to clear
all saved locations OR a number as shown by 'show' command 
to delete that location.

_Example:_ 
```bash
$ . loc clear all
$ . loc clear 3
```

The first command will clear all saved bookmarks.
The second one will delete the bookmark named "share" as 
per our example in the show command.
