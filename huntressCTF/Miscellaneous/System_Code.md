### Challenge description

Follow the white rabbit.

NOTE: Bruteforce is permitted for this challenge instance if you feel it is necessary.

### Solution

Wow. This chal.. lost a lot on it.

Anyway, inspecting the config we find something interesting 
```javascript
backupGlyphsTwr: ["a", "b", "c", "d", "e", "f"],
```
`Twr` is reference to white rabbit and since we have an input box on the screen and it allows brute-force, we write a script to try every combo with these letters.

```python
import requests
from itertools import permutations 

perm = permutations(["a", "b", "c", "d", "e", "f"])

for i in perm:
	ans = ''.join(i)
	r = requests.get('http://challenge.ctf.games:32563/enter='+ans)
	if r.text == "Incorrect. You will receive the flag with the correct input.":
		continue
	else:
		print(r.text)
		print(ans)
		exit(0)
```
flag{dc9edf4624504202eec5d3fab10bbccd}