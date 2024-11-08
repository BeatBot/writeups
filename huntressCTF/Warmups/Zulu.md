### Challenge description

Did you know that zulu is part of the phonetic alphabet? 

### Solution

Running `file` on the downloaded file gives us `zulu: compress'd data 16 bits`. I rename the file with the `.gz` suffix and extract with: 
```
gzip -d zulu.gz
```
Read the file with `cat` and there is the flag.

flag{74235a9216ee609538022e6689b4de5c}