# Hidden in plain CTF write up

This repository is a tutroial for solving the Hidden in plain CTF in CyberTalents website, you can access the problem through this [Link](https://cybertalents.com/challenges/network/arp-storm)

## Discovering abnormalities

From the first look at the file table in Wireshark we cannot find anything abnormal about the file, but what caught my interest was the long length of the data and after investigating each reply and request we can find out that the data of the packet is changing by wide range from a packet to another so from that we can start our path for finding the hidden flag

[![ARP STORM 1](https://github.com/zeyadsalah22/ARP-Storm-CTF/blob/main/images/Picture1.png)

## Catching up the packets data

Now we want to collect the packets data from each request and reply in the file and save it in a text file for investigation, we can do that using tshark in the command prompt to collect the packets data we can run the command found in the figure below then copy and paste the result in a text file.

[![ARP STORM 2](https://github.com/zeyadsalah22/ARP-Storm-CTF/blob/main/images/Picture2.png)


## Decoding Data

From the output we can see that the data is encoded in some way, after using online coding analyzer we can find that the data is encoded using yEnc, so now we need to use a python code to decode that text file but installing yEnc library cannot work for python3 so we can use another way by implementing the decoding function by ourselves and decode the text file as shown in the figure below.

[![ARP STORM 3](https://github.com/zeyadsalah22/ARP-Storm-CTF/blob/main/images/Picture3.png)


## Investigating the output

The output of the code seems strange and cannot get any outcome from it but after scrolling over the output, we can see that there are some text parts present in the strange output as shown in the figure.

[![ARP STORM 4](https://github.com/zeyadsalah22/ARP-Storm-CTF/blob/main/images/Picture4.png)


Then the output of that code will be our encoded flag which is: ZmxhZ3tnckB0dWl0MHVzXzBwY09kZV8xc19BbHdAeXNfQTZ1U2VkX3QwX3AwMXMwbn0

 ## Another Decoding

After getting the part we are interested in from the output we can see that it is decoded in base64 so now we need to decode it again but this time using base64 library.

[![ARP STORM 5](https://github.com/zeyadsalah22/ARP-Storm-CTF/blob/main/images/Picture5.png)

 ## Catching the flag

After doing that we can take from the output is that our flag is as the following :
b’flag{md5sum(\’flag\’)}’
md5sum shows us that the flag is hashed by MD5 hash, so we need to get its actual value by running the following code.

[![ARP STORM 5](https://github.com/zeyadsalah22/ARP-Storm-CTF/blob/main/images/Picture5.png)

 ## Submitting Flag

Now we have got the flag which will be flag{327a6c4304ad5938eaf0efb6cc3e53dc}

[![ARP STORM 5](https://github.com/zeyadsalah22/ARP-Storm-CTF/blob/main/images/Picture5.png)

