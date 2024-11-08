### Challenge description

You've reached the Obfuscation Station!
Can you decode this PowerShell to find the flag? 

### Solution

We got a file, we open it and its obfuscation... We remove the last part (`| & ( $eNV:cOmSPEc[4,15,25]-JOin'')`) and paste it in `powershell` and run it:
```powershell
(nEW-objECt  SYstem.iO.COMPreSsIon.deFlaTEStREAm( [IO.mEmORYstreAM][coNVERt]::FROMBAse64sTRING( 'UzF19/UJV7BVUErLSUyvNk5NMTM3TU0zMDYxNjSxNDcyNjexTDY2SUu0NDRITDWpVQIA') ,[io.COmPREssioN.coMpreSSioNmODE]::DeCoMpReSS)| %{ nEW-objECt  sYStEm.Io.StREAMrEADeR($_,[TeXT.encodiNG]::AsCii)} |%{ $_.READTOENd()})
```
and we get the flag.

flag{3ed675ef0343149723749c34fa910ae4}