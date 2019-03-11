# lobash
A function library for bash scripts.
This project contains bash- and other scripts we use in our daily work.

## Usage

You have to add the following line into your script right after the shebang (`#!/bin/bash`).
This will download the latest version of the script and pipe it into your bash.

```bash
#!/bin/bash
source <(curl -s "https://lobash.lan.frux.io?ref=master")
_init

# or use
_initAndPrompt
# to get an additional line like:
#2019-02-12T08:22:53 zebra@legolas(13.124.21.23) from 192.168.0.12
# or use
_initAndPrompt "scriptname.sh"
# and you may omit the next line (_echo_h) because it's taken care of for you

# You may use the bashlib functions from here on
_echo_h "This is a test and should be formatted correctly"
```

If you'd like a specific version of this script, then you'd have to play around with tags or branches or even get the call to curl the raw format of a file in a specific version (commit). I have not tried it yet, but it should be doable.

### Multiple Includes

Those don't matter at all. Other than download-time it doesn't affect the bash if you import a file more than once. The 'older' versions just get 'overwritten'.

This may be a performance problem when operating from outside, but with a download-time of 1ms internal, this is not a real problem.
