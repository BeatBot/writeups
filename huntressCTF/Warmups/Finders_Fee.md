### Challenge description

You gotta make sure the people who find stuff for you are rewarded well!

Escalate your privileges and uncover the flag.txt in the finder user's home directory.

### Solution

We run `find` with the `exec` flag to read the contents of flag.txt in finders home dir.
```
find /home/finder/flag.txt -exec cat {} \;
```
flag{63a10f0440218364424b20f9ddf6ad39}
