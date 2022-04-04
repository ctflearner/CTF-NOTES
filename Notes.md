# Web-Category

## Method-1
```bash
1. If you want to send a particular http request we can do with "curl command"
Command: curl -X FLAG <url> -i 
Where: 
-X: Specify http request method
-i: include protocol response headers in the output
```

# Forensic-Category

## Method-1
```bash
If there is pcap file first check that the "Protocol hierarchy"---> "Statistics---> protocol hierarchy"
```
## Method-2
```bash
If to Recover password from a pcap file first set the filter to "http" and see the "value"---> it will be given in "base64" so 
decode it.
```
## Method-3
```text
When we get  a "pdf" file in a CTF
1. We can use "pdftotext" command
Description: It basically converts the pdf to plain text
Command: pdftotext <pdf file> <output.txt>
To grep the flag: cat <output.txt> | grep <name of the flag>
```
