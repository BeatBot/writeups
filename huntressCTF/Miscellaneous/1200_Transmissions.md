### Challenge description

Wait, there aren't actually 1200 transmissions in this file, are there?

WARNING: The audio in this file is very loud and obnoxious. Please turn your volume way down before playing. 

### Solution

Alright, it sounds like an old modem. Googling a bit we stumble upon a tool called `minimodem`. (1200 from the hint.)
```
minimodem -r -f transmissions.wav 1200
```
we get
```
### CARRIER 1200 @ 1200.0 Hz ###
Greetings, Professor Falken. 

Would you like to play a game? 

flag{f28d133e7174c412c1e39b4a84158fa3}

Thanks for playing the Huntress CTF!

        @
       @@
       @@@@
  @@@@  @@@@@@  @@ @@@@@@@@
   @@@@@@ @@@@@@@   @  @  @@@@
     @@@@@@@@@@@@@@ @@@ @@   @@@
 @@@@@@# @@@@@@@@@@@ @@@@@@@@  @@@
  @@@@@@@@@@@@@@@@@@@@@@@@@@@@@ @@@
  @@         @@@@@@@@@@@@@@@     @@
  @@@@@@@@@@@@/@@@@@@@@@     @(~ @@
  @@    @@@@@@@@@@@ @@@@ @@@@  @@@
  @@@ @@@@.@@@@@@@@ @@@@@ @@@@  @@
   @@@  @@@*%@@@@ @@@ @@@@ @@@@@
     @@@    @   @@@@@@@@@ @@@@@
       @@@@.     @@@@@@@@ @@@@
           @@@@@@@@@ @@@@@ @@
                        @@
                         @ -dk

### NOCARRIER ndata=663 confidence=4.773 ampl=1.001 bps=1200.00 (rate perfect) ###
```

flag{f28d133e7174c412c1e39b4a84158fa3}