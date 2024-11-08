### Challenge description

My friend wouldn't shut up about his new keyboard, so...

### Solution

So running `file` on the downloaded file says its a pcap file and the chal mentiones keyboard, could be USB keystrokes.

I found a [python script](https://github.com/RajChowdhury240/usb-keystrokes-ctf-tool/blob/master/UsbKeyboardDataHacker.py) for extracting the key strokes and tried it and it worked!

```
python3 UsbKeyboardDataHacker.py keyboard_junkie
[-] Unknow Key : 01
[-] Unknow Key : 01
[+] Found : so<SPACE>the<SPACE>answer<SPACE>is<SPACE>flag{f7733e0093b7d281dd0a30fcf34a9634}<SPACE>hahahah<SPACE>lol<RET>
```

flag{f7733e0093b7d281dd0a30fcf34a9634}