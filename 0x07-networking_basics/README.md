[](https://github.com/markdown-it/markdown-it-emoji)


# About Bash Project: 0x07. Networking basics #0 :wink:
## DevOps Network

# Resources
## Read or watch:
- [OSI model](https://intranet.alxswe.com/rltoken/k2uCsynicuNbu1cAQhXqVQ)
- [Different types of network](https://intranet.alxswe.com/rltoken/XW3ZGm5Ya_a8XVDXcAKT_A)
- [LAN network](https://intranet.alxswe.com/rltoken/en370-Hrwgi_GUvFcg3bKg)
- [WAN network](https://intranet.alxswe.com/rltoken/Ah1EKqnINR85lM4P2WnLSw)
- [Internet](https://intranet.alxswe.com/rltoken/Lwh9xQxFD4dWh5sIApXI1g)
- [MAC address](https://intranet.alxswe.com/rltoken/j-Wp-YRvFTVP04SpIeRzHQ)
- [What is an IP address](https://intranet.alxswe.com/rltoken/HaZZvrmGaQ3U7ZLDYgZb6w)
- [Private and public address](https://intranet.alxswe.com/rltoken/OPJCZYuWSEXLIZOqU9Uc0A)
- [IPv4 and IPv6](https://intranet.alxswe.com/rltoken/M8g-egWLlldTl6Y0QECdwA)
- [Localhost](https://intranet.alxswe.com/rltoken/7lj-zoZQ7xFTkj4MTyos_g)
- [TCP and UDP](https://intranet.alxswe.com/rltoken/uJbs8E9-FyATfsELpmtTIg)
- [TCP/UDP ports List](https://intranet.alxswe.com/rltoken/4PYkqDfOvIZZb9aUPGOOzQ)
- [What is ping /ICMP](https://intranet.alxswe.com/rltoken/3zBgO6r2M1Q8lUVt9g8aJw)
- [Positional parameters](https://intranet.alxswe.com/rltoken/U5CMxsErz85edWap3fNEoQ)

## man or help:
- `netstat`
- `ping`


## Learning Objectives

- At the end of this project, you are expected to be able to [explain to anyone](https://intranet.alxswe.com/rltoken/RowLuXQWMOPFHaboo_3odA), without the help of Google:

## OSI Model
- What it is
- How many layers it has
- How it is organized
## What is a LAN
- Typical usage
- Typical geographical size
## What is a WAN
- Typical usage
- Typical geographical size
## What is the Internet
- What is an IP address
- What are the 2 types of IP address
- What is `localhost`
- What is a subnet
- Why IPv6 was created
## TCP/UDP
- What are the 2 mainly used data transfer protocols for IP (transfer level on the OSI schema)
- What is the main difference between TCP and UDP
- What is a port
- Memorize SSH, HTTP and HTTPS port numbers
- What tool/protocol is often used to check if a device is connected to a network


# Requirements
## General
- Allowed editors: `vi, vim, emacs`
- All your Bash script files will be interpreted on Ubuntu 20.04 LTS
- All your files should end with a new line
- A README.md file, at the root of the folder of the project, is mandatory
- All your Bash script files must be executable
- Your Bash script must pass `shellcheck` without any error
- The first line of all your files should be exactly `#!/usr/bin/env bash`
- The second line of all your Bash scripts should be a comment explaining what is the script doing.


## More Info
The second line of all your Bash scripts should be a comment explaining what is the script doing

For multiple choice question type tasks, just type the number of the correct answer in your answer file, add a new line for every new answer, example:

What is the most important position in a software company?

- Project manager
- Backend developer
- System administrator

```
sylvain@ubuntu$ cat foo_answer_file
3
sylvain@ubuntu$
```
Source for question 1 [here](https://intranet.alxswe.com/rltoken/iEZZ6SemL1HJHjaJOjlPYQ)


# Tasks
## 0. OSI model

OSI (Open Systems Interconnection) is an abstract model to describe layered communication and computer network design. The idea is to segregate the different parts of what make communication possible.

It is organized from the lowest level to the highest level:

- The lowest level: layer 1 which is for transmission on physical layers with electrical impulse, light or radio signal
- The highest level: layer 7 which is for application specific communication like SNMP for emails, HTTP for your web browser, etc

Keep in mind that the OSI model is a concept, it’s not even tangible. The OSI model doesn’t perform any functions in the networking process. It is a conceptual framework so we can better understand complex interactions that are happening. Most of the functionality in the OSI model exists in all communications systems.

![image](https://github.com/NonsoTheTechGuy/alx-system_engineering-devops/assets/92136146/376bb2bd-1189-40b1-9050-cd02d111ac64)

In this project we will mainly focus on:

- The Transport layer and especially TCP/UDP
- On the Network layer with IP and ICMP

The image bellow describes more concretely how you can relate to every level.

![image](https://github.com/NonsoTheTechGuy/alx-system_engineering-devops/assets/92136146/d3bb88f7-b304-4f17-9af4-b0c4d18f30aa)

Questions:

What is the OSI model?

- Set of specifications that network hardware manufacturers must respect
- The OSI model is a conceptual model that characterizes the communication functions of a telecommunication system without regard to their underlying internal structure and technology
- The OSI model is a model that characterizes the communication functions of a telecommunication system with a strong regard for their underlying internal structure and technology

How is the OSI model organized?
- Alphabetically
- From the lowest to the highest level
- Randomly

---
Repo:

- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x07-networking_basics`
- File: `0-OSI_model`

## 1. Types of network

![image](https://github.com/NonsoTheTechGuy/alx-system_engineering-devops/assets/92136146/32a22935-a1ca-4796-b51f-299eda4b9bc2)


LAN connect local devices together, WAN connects LANs together, and WANs are operating over the Internet.

Questions:

What type of network a computer in local is connected to?

- Internet
- WAN
- LAN

What type of network could connect an office in one building to another office in a building a few streets away?

Internet
- WAN
- LAN
What network do you use when you browse www.google.com from your smartphone (not connected to the Wifi)?

Internet
- WAN
- LAN
- ---
Repo:

- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x07-networking_basics`
- File: 1-types_of_network`


## 2. MAC and IP address

![image](https://github.com/NonsoTheTechGuy/alx-system_engineering-devops/assets/92136146/8e7fd983-f7f3-42a7-932c-de455603aa8f)

Questions:

What is a MAC address?

- The name of a network interface
- The unique identifier of a network interface
- A network interface

What is an IP address?

- Is to devices connected to a network what postal address is to houses
- The unique identifier of a network interface
- Is a number that network devices use to connect to networks
---
Repo:

- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x07-networking_basics`
- File: `2-MAC_and_IP_address`


## 3. UDP and TCP

![image](https://github.com/NonsoTheTechGuy/alx-system_engineering-devops/assets/92136146/b8986a0e-8fd9-4550-8631-6dab53fce6cf)

Let’s fill the empty parts in the drawing above.

Questions:

- Which statement is correct for the TCP box:
  - `It is a protocol that is transferring data in a slow way but surely`
  - `It is a protocol that is transferring data in a fast way and might loss data along in the process`
- Which statement is correct for the UDP box:
  - `It is a protocol that is transferring data in a slow way but surely`
  - `It is a protocol that is transferring data in a fast way and might loss data along in the process`
- Which statement is correct for the TCP worker:
  - `Have you received boxes x, y, z?`
  - `May I increase the rate at which I am sending you boxes?`
---
Repo:

- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x07-networking_basics`
- File: `3-UDP_and_TCP`




# Author

## KALU JONAH CHINONSO 😃
