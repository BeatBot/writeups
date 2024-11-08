### Challenge description

Hmmm, have you seen some of the strange DNS records for the ctf.games domain? One of them sure is [od](https://en.wikipedia.org/wiki/Od_(Unix))d... 

### Solution

Check the DNS TXT records of the domain:

```bash
dig ctf.games txt
```
We see an array of numbers, lets extract them.
```bash
dig ctf.games txt | grep -e "^ctf.games." | cut -d '"' -f2
```
We get:
```
146 154 141 147 173 061 064 145 060 067 062 146 067 060 065 144 064 065 070 070 062 064 060 061 144 061 064 061 143 065 066 062 146 144 143 060 142 175
```
copy them over into cyberchef and use `From Octal`. We know this becouse the challenge hinted at it with the link to the wikipedia page of the command `od` wich dumps in `octal`.

flag{14e072f705d45882401d141c562fdc0b}