<sup>looking for
<a href="https://github.com/sentriz/cliphist-sh">cliphist-sh</a>?</sup>

### cliphist

*clipboard history “manager” for wayland*

- write clipboard changes to a history file
- recall history with dmenu (for example)
- both text and images are supported
- clipboard is preserved byte-for-byte
  - leading / trailing whitespace / no whitespace or newlines are
    preserved
  - won’t break fancy editor selections like vim wordwise, linewise,
    block mode
- no concept of a picker, only pipes

requires: [go](https://golang.org/),
[wl-clipboard](https://github.com/bugaevc/wl-clipboard), xdg-utils

### install

`$ go install go.senan.xyz/cliphist`

### usage

###### listen for clipboard changes

`$ wl-paste --watch cliphist store`  
this will listen for changes on your primary keyboard and write it to
the history.  
call it once per session - for example in your sway config

###### select old item

`$ cliphist list | dmenu | cliphist decode | wl-copy`  
bind it to something nice on your keyboard
