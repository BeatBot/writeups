### Challenge description

A simple message for you to decipher:

`squiqhyiiycfbudeduutvehrhkjki`

Submit the original plaintext hashed with MD5, wrapped between the usual flag format: `flag{}`

### Solution

We put it in CyberChef and use `ROT13` with amount `10` and get the deciphered text. Next, we use `md5` to get the hash and but it in `flag{}`.

flag{c945bb2173e7da5a292527bbbc825d3f}