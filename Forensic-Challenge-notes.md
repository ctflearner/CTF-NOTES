# Forensic-challenge
------------------------
Method-1
--------------
``IF there ia pcap file always check for ``
```
tcp.stream eq <Number>
```
``Check for unusal ports``
``To save the packet inforamation``
```
1. Select a tcp packet-->follow tcp stream -->save as raw
```

Method-2
-------------------
``If there is  a midi file``
```
Tool: Audacity[https://www.audacityteam.org/]
```

Method-3
-------------
``IF the backup of our data was somehow corrupted and we want to recover the file from that ``
```
SOLLUTION
------------
Command used: foremost -i <name of the backup-file> -o <NAme-of-the-file-you-want-to-save>
```

Tools-information
-------------------
```
foremost: It is avery useful open source forensic utility which is able to recover deleted files using the technique called data carving
-i: It means the input as in this case external memory/file
-o : It is the output folder, where to save the recovered files.

```
``Note: After recovering the file if it is in zip foramt then we can check with zip command``
```
Command used: zip -FF <name of thefile>.zip --out <fixed.zip>
```
```Article for explanation```: ![https://www.computerhope.com/unix/zip.htm]

