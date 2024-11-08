### Challenge description

This is a dumb challenge. I'm sorry. 

### Solution

We unzip the downloaded file and see base64 encoded. But how many time? 32?

We wrote a little python script and got the flag

```python
import base64

with open('base64by32', 'r') as file:
    data = file.read()

for i in range(32):
    data = base64.b64decode(data)

print(data)
```
Bonus, one liner:
```bash
state=$(<base64by32);for i in {1..32}; do state=$(<<<"$state" base64 -d) done; echo "$state"
```

flag{8b3980f3d33f2ad2f531f5365d0e3970}