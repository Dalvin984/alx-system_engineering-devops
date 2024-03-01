_0x07. Networking basics #0
==========================

-   By Sylvain Kalache
-   Weight: 1


Resources
---------

**Read or watch**:

-   [OSI model](https://alx-intranet.hbtn.io/rltoken/k2uCsynicuNbu1cAQhXqVQ "OSI model")
-   [Different types of network](https://alx-intranet.hbtn.io/rltoken/XW3ZGm5Ya_a8XVDXcAKT_A "Different types of network")
-   [LAN network](https://alx-intranet.hbtn.io/rltoken/en370-Hrwgi_GUvFcg3bKg "LAN network")
-   [WAN network](https://alx-intranet.hbtn.io/rltoken/Ah1EKqnINR85lM4P2WnLSw "WAN network")
-   [Internet](https://alx-intranet.hbtn.io/rltoken/Lwh9xQxFD4dWh5sIApXI1g "Internet")
-   [MAC address](https://alx-intranet.hbtn.io/rltoken/j-Wp-YRvFTVP04SpIeRzHQ "MAC address")
-   [What is an IP address](https://alx-intranet.hbtn.io/rltoken/HaZZvrmGaQ3U7ZLDYgZb6w "What is an IP address")
-   [Private and public address](https://alx-intranet.hbtn.io/rltoken/OPJCZYuWSEXLIZOqU9Uc0A "Private and public address")
-   [IPv4 and IPv6](https://alx-intranet.hbtn.io/rltoken/M8g-egWLlldTl6Y0QECdwA "IPv4 and IPv6")
-   [Localhost](https://alx-intranet.hbtn.io/rltoken/7lj-zoZQ7xFTkj4MTyos_g "Localhost")
-   [TCP and UDP](https://alx-intranet.hbtn.io/rltoken/uJbs8E9-FyATfsELpmtTIg "TCP and UDP")
-   [TCP/UDP ports List](https://alx-intranet.hbtn.io/rltoken/4PYkqDfOvIZZb9aUPGOOzQ "TCP/UDP ports List")
-   [What is ping /ICMP](https://alx-intranet.hbtn.io/rltoken/3zBgO6r2M1Q8lUVt9g8aJw "What is ping /ICMP")
-   [Positional parameters](https://alx-intranet.hbtn.io/rltoken/ZbMHH3jmxFhcrbigVy15iw "Positional parameters")

**man or help**:

-   `netstat`
-   `ping`

Learning Objectives
-------------------

At the end of this project, you are expected to be able to [explain to anyone](https://alx-intranet.hbtn.io/rltoken/RowLuXQWMOPFHaboo_3odA "explain to anyone"), **without the help of Google**:

### OSI Model

-   What it is
-   How many layers it has
-   How it is organized

### What is a LAN

-   Typical usage
-   Typical geographical size

### What is a WAN

-   Typical usage
-   Typical geographical size

### What is the Internet

-   What is an IP address
-   What are the 2 types of IP address
-   What is `localhost`
-   What is a subnet
-   Why IPv6 was created

### TCP/UDP

-   What are the 2 mainly used data transfer protocols for IP (transfer level on the OSI schema)
-   What is the main difference between TCP and UDP
-   What is a port
-   Memorize SSH, HTTP and HTTPS port numbers
-   What tool/protocol is often used to check if a device is connected to a network

Requirements
------------

### General

-   Allowed editors: `vi`, `vim`, `emacs`
-   All your Bash script files will be interpreted on Ubuntu 20.04 LTS
-   All your files should end with a new line
-   A `README.md` file, at the root of the folder of the project, is mandatory
-   All your Bash script files must be executable
-   Your Bash script must pass `shellcheck` without any error
-   The first line of all your Bash scripts should be exactly `#!/usr/bin/env bash`
-   The second line of all your Bash scripts should be a comment explaining what is the script doing

More Info
---------

The second line of all your Bash scripts should be a comment explaining what is the script doing

For multiple choice question type tasks, just type the number of the correct answer in your answer file, add a new line for every new answer, example:

What is the most important position in a software company?

1.  Project manager
2.  Backend developer
3.  System administrator

```
sylvain@ubuntu$ cat foo_answer_file
3
sylvain@ubuntu$

```

Source for question 1 [here](https://alx-intranet.hbtn.io/rltoken/iEZZ6SemL1HJHjaJOjlPYQ "here")

Tasks
-----

### 0\. OSI model

mandatory

Score: 0.00% (Checks completed: 0.00%)

OSI (Open Systems Interconnection) is an abstract model to describe layered communication and computer network design. The idea is to segregate the different parts of what make communication possible.

It is organized from the lowest level to the highest level:

-   The lowest level: layer 1 which is for transmission on physical layers with electrical impulse, light or radio signal
-   The highest level: layer 7 which is for application specific communication like SNMP for emails, HTTP for your web browser, etc

Keep in mind that the OSI model is a concept, it's not even tangible. The OSI model doesn't perform any functions in the networking process. It is a conceptual framework so we can better understand complex interactions that are happening. Most of the functionality in the OSI model exists in all communications systems.

![](https://s3.amazonaws.com/alx-intranet.hbtn.io/uploads/medias/2018/6/4e6a0ad87a65d7054248.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARDDGGGOUSBVO6H7D%2F20220121%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20220121T124113Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=10fe93ff962631db911454dccd5d0553cfc34439ee9edd8c4db198d75356e66c)

In this project we will mainly focus on:

-   The Transport layer and especially TCP/UDP
-   On the Network layer with IP and ICMP

The image bellow describes more concretely how you can relate to every level.

![](https://s3.amazonaws.com/alx-intranet.hbtn.io/uploads/medias/2020/9/0fc96bd99faa7941b18bcae4c5f90c6acd11791d.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARDDGGGOUSBVO6H7D%2F20220121%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20220121T124113Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=1d4075da205528e0d4858d4a2666a8bafa32bc83b954e85401315e13903e2ed1)

Questions:

What is the OSI model?

1.  Set of specifications that network hardware manufacturers must respect
2.  The OSI model is a conceptual model that characterizes the communication functions of a telecommunication system without regard to their underlying internal structure and technology
3.  The OSI model is a model that characterizes the communication functions of a telecommunication system with a strong regard for their underlying internal structure and technology

How is the OSI model organized?

1.  Alphabetically
2.  From the lowest to the highest level
3.  Randomly

**Repo:**

-   GitHub repository: `alx-system_engineering-devops`
-   Directory: `0x07-networking_basics`
-   File: `0-OSI_model`

 Done? Help Check your code Get a sandbox QA Review

