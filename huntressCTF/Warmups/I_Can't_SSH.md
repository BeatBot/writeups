### Challenge description

I've got this private key... but why can't I SSH?

### Solution

Trying to ssh using the key with `-i` and after changing the file permission with `chmod` gives us an error:
```
Load key "id_rsa": error in libcrypto
```
This is a weird one but ssh key needs to have a new line at the end of it. We can add it with echo:
```
echo "" >> id_rsa
```
We try again and ... we are in. Cat the `flag.txt` and that is it.

flag{ee1f28722ec1ce1542aa1b486dbb1361}