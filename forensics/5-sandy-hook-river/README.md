### Challenge description

Here is the challenge description:

![description](./images/1.png) 

And we were given the message.rar file.


### Solution
When i read the description of the challenge carefully i extracted some words from it which were bold written in the paragraphs.

![chall-description](./images/3.png) 

which turned out to be a : **WhisperbreathsighopaquestuttersstonesLoch NessChupacabraesteemed**

Now moving forward, 

When i opened the rar file manually, it just contained the message.txt:

![message-txt](./images/2.PNG) 

When extracting the rar file i faced this issue although the message.txt file was extracted:

![message-txt2](./images/4.png) 

The message.txt file does not contain any useful information:
![message-txt3](./images/5.PNG) 

i used the command **dir** to lists the contents of a directory, showing files and folders along with some basic details like file size, date modified, etc., then i used the **dir /r** command to lists the contents of a directory, and it also includes additional information specifically for Alternate Data Streams (ADS) on files, which is a feature of the NTFS file system. ADS allows files to contain hidden metadata or other "streams" of data that are not typically visible. When we use **dir /r**, we see these hidden streams if they exist.

![dir-r](./images/6.png) 

Now i used the command 
**certutil -decode message.txt:message.rar hidden.rar**
to extract and decode an Alternate Data Stream (ADS) named message.rar that is hidden within the file message.txt. By decoding it into hidden.rar, We can create an accessible, separate file (hidden.rar) from the hidden ADS data. 

![command](./images/7.png) 

Here we got the hidden.rar file:

![zip-file](./images/8.PNG) 

but it is password protected .

![zip-file2](./images/9.PNG) 

Now entering the string which we extracted from the bold words of the challenge description 
i.e :**WhisperbreathsighopaquestuttersstonesLoch NessChupacabraesteemed**

here we got the final flag:
![final-flag](./images/10.PNG) 
