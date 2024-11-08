### Challenge description

Don't believe everything you see on the Internet!

Anyway, have you heard this intro soundtrack from Half-Life 3? 

### Solution

Download the file and check if it really is an mp3 file.

```
file Half-Life_3_OST.mp3
```
it says its a PNG file
```
Half-Life_3_OST.mp3: PNG image data, 800 x 200, 8-bit/color RGB, non-interlaced
```
Rename the file with the proper png exension and the open it.

```
mv Half-Life_3_OST.mp3 Half-Life_3_OST.png
```

flag{a85466991f0a8dc3d9837a5c32fa0c91}