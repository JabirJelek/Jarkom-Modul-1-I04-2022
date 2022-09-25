# Jarkom-Modul-1-I04-2022

**Module 1 Practicum Report**

Group Members:

+ Farzana Afifah Razak - 5025201130
+ Muhammad Azka Aysar Santoso - 5025201150
+ Raihan Farid - 5025201141


## Important Links

+ [Questions](https://docs.google.com/document/d/1e5fXdleV59vFthVeK0O5WfmuOYV6xi6WkpHsZEiBofE/edit?usp=sharing)
+ [Resources](https://docs.google.com/document/d/1WcElh3NxoqVzibwBwo-fZ0l6eK3pEtx7gW60r2KSZMM/edit)

## Table of Contents

- [Jarkom-Modul-1-I01-2022](#jarkom-modul-1-i01-2022)
  - [Important Links](#important-links)
  - [Table of Contents](#table-of-contents)
  - [Answers](#answers)
    - [Question 1](#question-1)
    - [Question 2](#question-2)
    - [Question 3](#question-3)
    - [Question 4](#question-4)
    - [Question 5](#question-5)
    - [Question 6](#question-6)
    - [Question 7](#question-7)
    - [Question 8](#question-8)
    - [Question 9](#question-9)
    - [Question 10](#question-10)
  - [Revisions](#revisions)


## Answers

### Question 1

> Mention the web server used on "monta.if.its.ac.id"!

With the help of wireshark filter _tcp.host_, we can see which server are using the tcp protocol to request a GET method to retreive and request data from a specified resource in a server. From our experiment we can see that the web server used by monta.if.its.ac.id was `nginx/1.10.3` shown by the picture below <br>
![Result](Contents/no1.png)

### Question 2

> Ishaq was confused looking for TA topics for this semester, then he came to the monta website and found the topic details on the website “monta.if.its.ac.id”, what TA title did Ishaq open?

By using Ishaq's ip address of `103.94.189.5`, we can filter his network traffic by searching a tcp protocol that is using a GET request which contains topik in the request.

![Result](Contents/no2_1.png)

Therefore, we can conclude that this is the topic that Ishaq open. Using our own browser to send a GET request to the server with the same value as Ishaq's, we can see the topic that Ishaq's looking for which is Evaluasi untuk kerja User Space Filesystem (FUSE).<br>
![Result](Contents/no2_2.png)

### Question 3

> Filter so that wireshark only shows packets going to port 80!

filtering packets that only going to port 80 can be easily done by applying command `tcp.dstport == 80` . <br>
![Result](Contents/no3.png)

### Question 4

> Filter so that wireshark only picks up packets coming from port 21!

in order to get information about packets that only coming from port 21 in our network traffic we can do that by applying filter by using command `tcp.srcport == 21` <br>
![Result](Contents/no4.png)

### Question 5

> Filter so that wireshark only picks up packets coming from port 443!

We can filter our network traffic coming only from port 443 by using the command `tcp.srcport == 443`.<br>
![Result](Contents/no5.png)

### Question 6

> Filter so that wireshark only shows packets going to lipi.go.id !

To see packets only going to a specific domain, we used `http.host == lipi.go.id`.<br>
![Result](Contents/no6.png)

### Question 7

> Filter so that wireshark only picks up packets coming from your ip!

if we were using an Windows OS, we could open the Command Prompt and use the `ipconfig` to find out our current IP address (IPv4), after that we could just use `ip.src`:

![Result](Contents/no7.png)

### Question 8

> Browse the flow of packets in the given .pcap file, look for useful information in the form of a conversation between two students regarding cheating in practicum activities. The conversation is reported to use a network protocol with a high level of reliability in its data exchange so you need to apply a filter with that protocol.

first, we input this code  into the filter:  
`(tcp.flags.syn == 1 && tcp.flags.ack == 0) || (tcp.flags.syn == 1 && tcp.flags.ack == 1)`

then search for the network that shown [SYN,ACK] in the network, and click follow network, then we can get the result :

![Result](Contents/no8.png)

### Question 9

> There are reports of file exchanges made by the two students in the conversations obtained, look for the file in question! To facilitate reporting to superiors, name the file found in the format **[group_name].des3** and save the output file with the name **“flag.txt”.**

After we input this code previously : `(tcp.flags.syn == 1 && tcp.flags.ack == 0) || (tcp.flags.syn == 1 && tcp.flags.ack == 1)`

then, we search in the network that has the info of COMPLETE_DATA[31], then follow that network

after that, change  the code into raw, and download that data using the format **[group_name].des3**

in which it would display:

![Result](Contents/no9.png)


### Question 10

> Find the secret password (flag) of the above-mentioned underground organization!

After previously at number 8, stated that the password of the encrypted file is **'Ada, klo nggak salah passwordnya itu pake nama karakter anime yang kembar lima itu lho, jangan lupa pake huruf kecil semua'**, after that, we try to use each name of the each character of that anime, and we found the password was **nakano**, we use ubuntu to decrypt the file, and the result was :

![Result](Contents/no10.png)



