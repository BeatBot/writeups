### Challenge description

When you gaze long into the void, the void gazes also into you... 

### Solution

We connect using `nc` but there is nothing.. void. We redirect the output to a file so we can analyze more.

```bash
nc nc challenge.ctf.games 30124 > flag.txt
```
Opening the file reveals a lot of `[30;40m` which are [Ansi escape codes](https://en.wikipedia.org/wiki/ANSI_escape_code). We seatch for `f` and find the beginning flag. We copy the portion wich contains the flag, find&replace to clean it up and ... got it!

flag{b1370ac4fadd8c0237f8771d7d77286a}