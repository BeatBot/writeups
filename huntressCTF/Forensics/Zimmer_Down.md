### Challenge description

A user interacted with a suspicious file on one of our hosts.
The only thing we managed to grab was the user's registry hive.
Are they hiding any secrets?

### Solution

We get the file and check it with the `file` command. It says its a windows registry file. I looked up a registry viewer and downloaded `Registry Explorer` from [ericzimmerman.github.io](https://ericzimmerman.github.io/
) (or you can use regripper).

When we look in `C:\Users\Anon\Downloads\NTUSER.DAT: Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs` we see a file name with `b62` extension. This could be a hint to `base62` and it is!.
```
VJGSuERgCoVhl6mJg1x87faFOPIqacI3Eby4oP5MyBYKQy5paDF.b62.lnk
```
flag{4b676ccc1070be66b1a15dB601c8d500}