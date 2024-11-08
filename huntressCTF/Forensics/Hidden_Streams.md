### Challenge description

Beneath the surface, secrets glide,
A gentle flow where whispers hide.
Unseen currents, silent dreams,
Carrying tales in hidden streams.

Can you find the secrets in these Sysmon logs? 

### Solution

Downloading the file we see the `.evtx` extension. I used `dump_evtx` so i can search it easily. Looking for `powershell.exe` we come across a base64 string, we decode it and get the flag:
```
Record 756
<?xml version="1.0" encoding="utf-8"?>
<Event xmlns="http://schemas.microsoft.com/win/2004/08/events/event">
  <System>
    <Provider Name="Microsoft-Windows-Sysmon" Guid="5770385F-C22A-43E0-BF4C-06F5698FFBD9">
    </Provider>
    <EventID>15</EventID>
    <Version>2</Version>
    <Level>4</Level>
    <Task>15</Task>
    <Opcode>0</Opcode>
    <Keywords>0x8000000000000000</Keywords>
    <TimeCreated SystemTime="2024-08-28T00:19:14.033585Z">
    </TimeCreated>
    <EventRecordID>15107</EventRecordID>
    <Correlation>
    </Correlation>
    <Execution ProcessID="6968" ThreadID="6552">
    </Execution>
    <Channel>Microsoft-Windows-Sysmon/Operational</Channel>
    <Computer>WIN-UL3TI0T0LM6.test.local</Computer>
    <Security UserID="S-1-5-18">
    </Security>
  </System>
  <EventData>
    <Data Name="RuleName">-</Data>
    <Data Name="UtcTime">2024-08-28 00:19:11.899</Data>
    <Data Name="ProcessGuid">B56AE52F-6533-66CE-BE00-000000000900</Data>
    <Data Name="ProcessId">2460</Data>
    <Data Name="Image">C:\Windows\system32\WindowsPowerShell\v1.0\PowerShell.exe</Data>
    <Data Name="TargetFilename">C:\Temp:$5GMLW</Data>
    <Data Name="CreationUtcTime">2024-08-28 00:00:22.726</Data>
    <Data Name="Hash">SHA1=B1C3068058ADDF418D3E1418CD28414325B7A757,MD5=E754797031C6B367D0B6209092F34B3B,SHA256=F414CBA3A5D8C6EF18B1BE31F09C848447DDB37A5712E36EB7825E4E1EFAE868,IMPHASH=00000000000000000000000000000000</Data>
    <Data Name="Contents">ZmxhZ3tiZmVmYjg5MTE4MzAzMmY0NGZhOTNkMGM3YmQ0MGRhOX0=  </Data>
    <Data Name="User">WIN-UL3TI0T0LM6\Administrator</Data>
  </EventData>
</Event>
```

flag{bfefb891183032f44fa93d0c7bd40da9}