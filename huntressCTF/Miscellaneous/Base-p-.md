### Challenge description

That looks like a weird encoding, I wonder what it's based on.

### Solution

It's some kind of base encoding.. `-p-` could be refering to prime number.. There is `Base65536`, we can decode it on this website [Base65536 Decode Online Tool](https://www.better-converter.com/Encoders-Decoders/Base65536-Decode).

That worked, we get a `Base64` string. We put that in CyberChef and click the magic wand and we get an image.

Nothing but colored squares... after messing around a bit, we use color picker and get the hex values of the squares in order and what do you know, it's the flag.
```
#666c61#677b35#383663#663863#383439#633937#333065#613762#323131#326666#663339#666636#617d20
```
flag{586cf8c849c9730ea7b2112fff39ff6a}