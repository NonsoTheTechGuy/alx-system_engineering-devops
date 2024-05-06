# About Bash Project: 0x04. Loops, conditions and parsing

## Resources
---
### Read or watch:
- __[Loops sample](https://intranet.alxswe.com/rltoken/wT98UJfv_E2tk4yP9PcLLw)__
- __[Variable assignment and arithmetic](https://intranet.alxswe.com/rltoken/olvOKX699pq50rkHRE5cSA)__
- __[Comparison operators](https://intranet.alxswe.com/rltoken/HxohzllkOWh0t4dy_HptIQ)__
- __[File test operators](https://intranet.alxswe.com/rltoken/g8of2ABPEJfCNtPrDQaqVw)__
- __[Make your scripts portable](https://intranet.alxswe.com/rltoken/O0Ay21p7tDhfLMsYbtAKug)__
---
## man or help:
- env
- cut
- for
- while
- until
- if
## Learning Objectives
- At the end of this project, you are expected to be able to __[explain to anyone](https://intranet.alxswe.com/rltoken/UnkzDNdH09TFJ0-Y56azyg)__, without the help of Google:
---

## General

- How to create SSH keys.
- What is the advantage of using `#!/usr/bin/env bash` over `#!/bin/bash`.
- How to use `while`, `until` and `for` loops.
- How to use `if`, `else`, `elif` and `case` condition statements.
- How to use the `cut` command.
- What are files and other comparison operators, and how to use them.
- 
# Requirements

## General
- Allowed editors: `vi, vim, emacs`.
- All your files will be interpreted on Ubuntu 20.04 LTS.
- All your files should end with a new line.
- A `README.md` file, at the root of the folder of the project, is mandatory.
- All your Bash script files must be executable.
- Your Bash script must pass `Shellcheck` (version `0.7.0` via `apt-get`) without any error.
- The first line of all your Bash scripts should be exactly `#!/usr/bin/env bash`.
- The second line of all your Bash scripts should be a comment explaining what is the script doing


# More Info

## Shellcheck
[Shellcheck](https://intranet.alxswe.com/rltoken/joK6l_yEZ9N7T0GQ1RDjLA) is a tool that will help you write proper Bash scripts. It will make recommendations on your syntax and semantics and provide advice on edge cases that you might not have thought about. `Shellcheck` is your friend! All your Bash scripts must pass `Shellcheck` without any error or you will not get any points on the task.

`Shellcheck` is available on the school’s computers. If you want to use it on your own computer, here is how to [install](https://intranet.alxswe.com/rltoken/jbz0_-i3TV3WpKgxhyrtpA) it.

Examples:

Not passing `Shellcheck`:

https://s3.amazonaws.com/intranet-projects-files/holbertonschool-sysadmin_devops/251/Vxotqyj.png

Passing `Shellcheck`:

https://s3.amazonaws.com/intranet-projects-files/holbertonschool-sysadmin_devops/251/ubHWxDU.png

For every feedback, Shellcheck will provide a code that you can use to get more information about the issue, for example for code `SC2034`, you can browse https://intranet.alxswe.com/rltoken/dxp49_rfO4_9Yjtcg59exg.

---
# Tasks
## 0. Create a SSH RSA key pair
Read for this task:
- [Linux and Mac OS users](https://intranet.alxswe.com/rltoken/Cy1plV2eR3VphjPqliXB8A)
- [Windows users](https://intranet.alxswe.com/rltoken/074M_gTsD34x3Q6MX55PDw)

man: `ssh-keygen`

You will soon have to manage your own `servers` concept page hosted on remote [data centers](https://intranet.alxswe.com/rltoken/nDPzEm5SYxcdGxP_OpVYXQ). We need to set them up with your RSA public key so that you can access them via SSH.

Create a RSA key pair.

Requirements:

- Share your `public key` in your answer file `0-RSA_public_key.pub`
- Fill the `SSH public key` field of your [intranet profile](https://intranet.alxswe.com/rltoken/qsaEQ3ZWrgs-zoueDpXpPA) with the public key you just generated
- `Keep the private key to yourself in a secure location`, you will use it later to connect to your servers using SSH. Some storing ideas are Dropbox, Google Drive, password manager, USB key. Failing to do so will prevent you to access your servers, which will prevent you from doing your projects
- If you decide to add a passphrase to your key, make sure to save this passphrase in a secure location, you will not be able to use your keys without the passphrase.

SSH and RSA keys will be covered in depth in a later project.

Repo:

- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x04-loops_conditions_and_parsing`
- File: `0-RSA_public_key.pub`

## 1. For Best School loop

Write a Bash script that displays `Best School` 10 times.

Requirement:

- You must use the `for` loop (`while` and `until` are forbidden)

```
sylvain@ubuntu$ head -n 2 1-for_best_school 
#!/usr/bin/env bash
# This script is displaying "Best School" 10 times
sylvain@ubuntu$ ./1-for_best_school 
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Best School
sylvain@ubuntu$
```
Note that:

- The first line of my Bash script starts with `#!/usr/bin/env bash`
- The second line of my Bash scripts is a comment explaining what it is doing
- 
Repo:

- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x04-loops_conditions_and_parsing`
- File: `1-for_best_school`

## 2. While Best School loop

Write a Bash script that displays `Best School` 10 times.

Requirements:

- You must use the `while` loop (`for` and `until` are forbidden)
- 
```
sylvain@ubuntu$ ./2-while_best_school
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Best School
sylvain@ubuntu$
```

Repo:

- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x04-loops_conditions_and_parsing`
- File: `2-while_best_school`

---
## 3. Until Best School loop

Write a Bash script that displays `Best School` 10 times.

Requirements:

- You must use the `until` loop (`for` and `while` are forbidden)
```
sylvain@ubuntu$ ./3-until_best_school
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Best School
sylvain@ubuntu$
``` 
Repo:

- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x04-loops_conditions_and_parsing`
- File: `3-until_best_school`


## 4. If 9, say Hi!

Write a Bash script that displays `Best School` 10 times, but for the 9th iteration, displays `Best School` and then `Hi` on a new line.

Requirements:

- You must use the `while` loop (`for` and `until` are forbidden)
- You must use the `if` statement
```
sylvain@ubuntu$ ./4-if_9_say_hi
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Best School
Hi
Best School
sylvain@ubuntu$ 
```
Repo:

- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x04-loops_conditions_and_parsing`
- File: `4-if_9_say_hi`




## Author

KALU JONAH CHINONSO
