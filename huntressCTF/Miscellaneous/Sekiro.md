### Challenge description

お前はもう死んでいる 

### Solution

Welp, the name is a hint. It's souls like game and the instance we connect to seems like we are fighting a boss and we need to react to the moves that they make.

We made a script to help us with this:

```python
import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect(("challenge.ctf.games", 32586))

text = s.recv(2200)
print(text.decode("utf-8"))

text = s.recv(201)
print(text.decode("utf-8"))

while True:
	text = s.recv(1024)
	text = text.decode("utf-8")
	
	if len(text) > 20 and len(text) < 60 :
		print(repr(text))
		text = text[6:].strip().split('\n')[0].split(' ')[2]
		print(text)
		
		if text == 'strike':
			s.send(b'block\n')
			print('I block')
			continue
		if text == 'advance':
			s.send(b'retreat\n')
			print('I retreat')
			continue
		if text == 'retreat':
			s.send(b'strike')
			print('I strike')
			continue
		if text == 'block':
			s.send(b'advance')
			print('I advance')
			continue
	else:
		print(text)
```

After running it for a few seconds we get the flag.

flag{a1ae4e5604576818132ce3bfebe95de5}