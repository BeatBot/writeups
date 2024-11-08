### Challenge description

Someone sent this to me...
such enigma, such mystery:

```
rkenr wozec gtrfl obbur bfgma fkgyq ctkvq zeucz hlvwx yyzat zbvns kgyyd sthmi vsifc ovexl zzdqv slyir nwqoj igxuu kdqgr fdbbd njppc mujyy wwcoy
```

Settings as below:

- 3 Rotor Model
- Rotor 1: `VI`, Initial: `A`, Ring `A`
- Rotor 2: `I`, Initial: `Q`, Ring `A`
- Rotor 3: `III`, Initial `L`, Ring `A`
- Reflector: `UKW B`
- Plugboard: `BQ CR DI EJ KW MT OS PX UZ GH`


### Solution

From the chals description we get a hint, its using Enigma encryption. 

We use `Enigma` and `To lower case` on CyberChef, input the encrypted text and we get this string:

```
messa gewra ppedi nligh thidd endee perou tofsi ghtlo cking itmor etigh tanyw ayyou rflag isher eflag fdfea bcacb ebfba daefb eccaa dddba fezzz
```
Formatting it gives us:
```
message wrapped in light hidden deeper out of sight locking it more tight any way your flag is here flag fdfea bcacb ebfba daefb eccaa dddba fezzz
```
We remove the `zzz` at the and and the spaces and add braces, thats the flag.

flag{fdfeabcacbebfbadaefbeccaadddbafe}