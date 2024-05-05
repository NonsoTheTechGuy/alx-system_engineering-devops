# About Bash Project: 0x05. Processes and Signals

## Resources
---
### Read or watch:

- __[Linux PID](https://www.linfo.org/pid.html)__
- __[Linux process](https://www.thegeekstuff.com/2012/03/linux-processes-environment/)__
- __[Linux signal](https://www.educative.io/answers/what-are-linux-signals)__
- __[Process management in linux](https://www.digitalocean.com/community/tutorials/process-management-in-linux)__
---
## man or help:
- ps
- pgrep
- pkill
- kill
- exit
- trap
## Learning Objectives
- At the end of this project, you are expected to be able to __[explain to anyone](https://intranet.alxswe.com/rltoken/_zeQBWHdlNNOM-5IqFDhSQ)__, without the help of Google:
---

## General

- What is a PID
- What is a process
- How to find a process’ PID
- How to kill a process
- What is a signal
- What are the 2 signals that cannot be ignored

# Requirements

## General
- Allowed editors: vi, vim, emacs
- All your files will be interpreted on Ubuntu 20.04 LTS
- All your files should end with a new line
- A README.md file, at the root of the folder of the project, is mandatory
- All your Bash script files must be executable
- Your Bash script must pass Shellcheck (version 0.7.0 via apt-get) without any error
- The first line of all your Bash scripts should be exactly #!/usr/bin/env bash
- The second line of all your Bash scripts should be a comment explaining what is the script doing


# More Info
- For those who want to know more and learn about all signals, check out this [article](https://intranet.alxswe.com/rltoken/BOU-KVNMqfKEIBo_VOI26A).
---
# Tasks
0. What is my PID
Write a Bash script that displays its own PID.

chinonso@ubuntu$ ./0-what-is-my-pid
4120
chinonso@ubuntu$

## Repo:
---
- GitHub repository: alx-system_engineering-devops
- Directory: 0x05-processes_and_signals
- File: 0-what-is-my-pid
---
## 1. List your processes

## Write a Bash script that displays a list of currently running processes.
Requirements:
- Must show all processes, for all users, including those which might not have a TTY
- Display in a user-oriented format
- Show process hierarchy
- 
`chinonso@ubuntu$ ./1-list_your_processes | head -50
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         2  0.0  0.0      0     0 ?        S    Feb13   0:00 [kthreadd]
root         3  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [ksoftirqd/0]
root         4  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [kworker/0:0]
root         5  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [kworker/0:0H]
root         7  0.0  0.0      0     0 ?        S    Feb13   0:02  \_ [rcu_sched]
root         8  0.0  0.0      0     0 ?        S    Feb13   0:03  \_ [rcuos/0]
root         9  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [rcu_bh]
root        10  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [rcuob/0]
root        11  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [migration/0]
root        12  0.0  0.0      0     0 ?        S    Feb13   0:02  \_ [watchdog/0]
root        13  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [khelper]
root        14  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [kdevtmpfs]
root        15  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [netns]
root        16  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [writeback]
root        17  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [kintegrityd]
root        18  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [bioset]
root        19  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [kworker/u3:0]
root        20  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [kblockd]
root        21  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [ata_sff]
root        22  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [khubd]
root        23  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [md]
root        24  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [devfreq_wq]
root        25  0.0  0.0      0     0 ?        S    Feb13   0:41  \_ [kworker/0:1]
root        27  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [khungtaskd]
root        28  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [kswapd0]
root        29  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [vmstat]
root        30  0.0  0.0      0     0 ?        SN   Feb13   0:00  \_ [ksmd]
root        31  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [fsnotify_mark]
root        32  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [ecryptfs-kthrea]
root        33  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [crypto]
root        45  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [kthrotld]
root        46  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [kworker/u2:1]
root        65  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [deferwq]
root        66  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [charger_manager]
root       108  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [kpsmoused]
root       125  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [scsi_eh_0]
root       126  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [kworker/u2:2]
root       172  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [jbd2/sda1-8]
root       173  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [ext4-rsv-conver]
root       409  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [iprt]
root       549  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [kworker/u3:1]
root       808  0.0  0.0      0     0 ?        S    Feb13   0:00  \_ [kauditd]
root       834  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [rpciod]
root       846  0.0  0.0      0     0 ?        S<   Feb13   0:00  \_ [nfsiod]
root         1  0.0  0.4  33608  2168 ?        Ss   Feb13   0:00 /sbin/init
root       373  0.0  0.0  19472   408 ?        S    Feb13   0:00 upstart-udev-bridge --daemon
root       378  0.0  0.2  49904  1088 ?        Ss   Feb13   0:00 /lib/systemd/systemd-udevd --daemon
root       518  0.0  0.1  23416   644 ?        Ss   Feb13   0:00 rpcbind
statd      547  0.0  0.1  21536   852 ?        Ss   Feb13   0:00 rpc.statd -L`

chinonso@ubuntu$

Repo:

- GitHub repository: alx-system_engineering-devops
- Directory: 0x05-processes_and_signals
- File: 1-list_your_processes

## 2. Show your Bash PID
Using your previous exercise command, write a Bash script that displays lines containing the bash word, thus allowing you to easily get the PID of your Bash process.
Requirements:
- You cannot use pgrep
- The third line of your script must be # shellcheck disable=SC2009 (for more info about ignoring shellcheck error [here](https://intranet.alxswe.com/rltoken/vErRT8QGU2bwJ6FLvPLzxw)

chinonso@ubuntu$ chinonso@ubuntu$ ./2-show_your_bash_pid
chinonso   4404  0.0  0.7  21432  4000 pts/0    Ss   03:32   0:00          \_ -bash
chinonso   4477  0.0  0.2  11120  1352 pts/0    S+   03:40   0:00              \_ bash ./2-show_your_bash_PID
chinonso   4479  0.0  0.1  10460   912 pts/0    S+   03:40   0:00                  \_ grep bash
chinonso@ubuntu$ 
---
Here we can see that my Bash PID is 4404.

Repo:

- GitHub repository: alx-system_engineering-devops
- Directory: 0x05-processes_and_signals
- File: 2-show_your_bash_pid

## 3. Show your Bash PID made easy
Write a Bash script that displays the PID, along with the process name, of processes whose name contain the word bash.
Requirements:
- You cannot use ps

chinonso@ubuntu$ ./3-show_your_bash_pid_made_easy
4404 bash
4555 bash
chinonoso@ubuntu$ ./3-show_your_bash_pid_made_easy
4404 bash
4557 bash
chinonso@ubuntu$

Here we can see that:
- For the first iteration: bash PID is 4404 and that the 3-show_your_bash_pid_made_easy script PID is 4555
- For the second iteration: bash PID is 4404 and that the 3-show_your_bash_pid_made_easy script PID is 4557
Repo:
- GitHub repository: alx-system_engineering-devops
- Directory: 0x05-processes_and_signals
- File: 3-show_your_bash_pid_made_easy

## 4. To infinity and beyond
Write a Bash script that displays To infinity and beyond indefinitely.
Requirements:
- In between each iteration of the loop, add a sleep 2
chinonso@ubuntu$ ./4-to_infinity_and_beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
^C
chinonso@ubuntu$ 
Note that I ctrl+c (killed) the Bash script in the example.
Repo:
- GitHub repository: alx-system_engineering-devops
- Directory: 0x05-processes_and_signals
- File: 4-to_infinity_and_beyond

## 5. Don't stop me now!
We stopped our `4-to_infinity_and_beyond` process using `ctrl+c` in the previous task, there is actually another way to do this.
Write a Bash script that stops `4-to_infinity_and_beyond` process.

Requirements:
- You must use `kill`
Terminal #0
sylvain@ubuntu$ ./4-to_infinity_and_beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
Terminated
sylvain@ubuntu$ 
Terminal #1

sylvain@ubuntu$ ./5-dont_stop_me_now 
sylvain@ubuntu$ 

I opened 2 terminals in this example, started by running my `4-to_infinity_and_beyond` Bash script in terminal #0 and then moved on terminal #1 to run `5-dont_stop_me_now`. We can then see in terminal #0 that my process has been terminated.

Repo:
- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x05-processes_and_signals`
- File: `5-dont_stop_me_now`

## 6. Stop me if you can
Write a Bash script that stops `4-to_infinity_and_beyond` process.

Requirements:

You cannot use `kill` or `killall`
Terminal #0
sylvain@ubuntu$ ./4-to_infinity_and_beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
Terminated
sylvain@ubuntu$ 
Terminal #1

sylvain@ubuntu$ ./6-stop_me_if_you_can
sylvain@ubuntu$
I opened 2 terminals in this example, started by running my `4-to_infinity_and_beyond` Bash script in terminal #0 and then moved on terminal #1 to run `6-stop_me_if_you_can`. We can then see in terminal #0 that my process has been terminated.

Repo:
- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x05-processes_and_signals`
- File: `6-stop_me_if_you_can`

## 7. Highlander
Write a Bash script that displays:
- `To infinity and beyond` indefinitely
- With a `sleep 2` in between each iteration
- `I am invincible!!!` when receiving a `SIGTERM` signal
Make a copy of your `6-stop_me_if_you_can` script, name it `67-stop_me_if_you_can`, that kills the `7-highlander` process instead of the `4-to_infinity_and_beyond` one.

Terminal #0
sylvain@ubuntu$ ./7-highlander
To infinity and beyond
To infinity and beyond
I am invincible!!!
To infinity and beyond
I am invincible!!!
To infinity and beyond
To infinity and beyond
To infinity and beyond
I am invincible!!!
To infinity and beyond
^C
sylvain@ubuntu$ 
Terminal #1

sylvain@ubuntu$ ./67-stop_me_if_you_can 
sylvain@ubuntu$ ./67-stop_me_if_you_can
sylvain@ubuntu$ ./67-stop_me_if_you_can
sylvain@ubuntu$ 
I started `7-highlander` in Terminal #0 and then run `67-stop_me_if_you_can` in terminal #1, for every iteration we can see `I am invincible!!!` appearing in terminal #0.

Repo:
- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x05-processes_and_signals`
- File: `7-highlander`

## 8. Beheaded process
Write a Bash script that kills the process `7-highlander`.

Terminal #0

sylvain@ubuntu$ ./7-highlander 
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
Killed
sylvain@ubuntu$ 
Terminal #1

sylvain@ubuntu$ ./8-beheaded_process
sylvain@ubuntu$ 
I started `7-highlander` in Terminal #0 and then run `8-beheaded_process` in terminal #1 and we can see that the `7-highlander` has been killed.

Repo:
- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x05-processes_and_signals`
- File: `8-beheaded_process`

## 9. Process and PID file
Write a Bash script that:
- Creates the file `/var/run/myscript.pid` containing its PID
- Displays `To infinity and beyond` indefinitely
- Displays `I hate the kill command` when receiving a SIGTERM signal
- Displays `Y U no love me?!` when receiving a SIGINT signal
- Deletes the file `/var/run/myscript.pid` and terminates itself when receiving a SIGQUIT or SIGTERM signal

![image](https://github.com/NonsoTheTechGuy/alx-system_engineering-devops/assets/92136146/442a2652-f9d9-4627-b16c-53fbf308275d)

sylvain@ubuntu$ sudo ./100-process_and_pid_file
To infinity and beyond
To infinity and beyond
^CY U no love me?!
Executing the `100-process_and_pid_file` script and killing it with `ctrl+c`.

Terminal #0

sylvain@ubuntu$ sudo ./100-process_and_pid_file
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
To infinity and beyond
I hate the kill command
sylvain@ubuntu$ 
Terminal #1

sylvain@ubuntu$ sudo pkill -f 100-process_and_pid_file
sylvain@ubuntu$ 
Starting `100-process_and_pid_file` in the terminal #0 and then killing it in the terminal #1.

Repo:
- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x05-processes_and_signals`
- File: `100-process_and_pid_file`


## 10. Manage my process

![image](https://github.com/NonsoTheTechGuy/alx-system_engineering-devops/assets/92136146/dea07246-7d5a-4edf-bcd5-4e0a041cd86f)

Read:
- __[&](https://intranet.alxswe.com/rltoken/R4YSgPT1k0PhWCrB0TYzoQ)__
- __[init.d](https://intranet.alxswe.com/rltoken/sVqN4oNYYO6ojS4ctT02Jw)__
- __[Daemon](https://intranet.alxswe.com/rltoken/kCoQ5aYO3towdDQFVPcfNg)__
- __[Positional parameters](https://intranet.alxswe.com/rltoken/TJ2rxUwRsnM1mJQHSCnOQA)__

man: `sudo`

Programs that are detached from the terminal and running in the background are called daemons or processes, need to be managed. The general minimum set of instructions is: `start`, `restart` and `stop`. The most popular way of doing so on Unix system is to use the init scripts.

Write a `manage_my_process` Bash script that:
- Indefinitely writes I am alive! to the file /tmp/my_process
- In between every I am alive! message, the program should pause for 2 seconds

Write Bash (init) script `101-manage_my_process` that manages `manage_my_process`. (both files need to be pushed to git)

Requirements:
- When passing the argument `start`:
  - Starts `manage_my_process`
  - Creates a file containing its PID in `/var/run/my_process.pid`
  - Displays `manage_my_process` started
When passing the argument `stop`:
  - Stops `manage_my_process`
  - Deletes the file `/var/run/my_process.pid`
  - Displays `manage_my_process` stopped
When passing the argument `restart`
  - Stops `manage_my_process`
  - Deletes the file `/var/run/my_process.pid`
  - Starts `manage_my_process`
  - Creates a file containing its PID in `/var/run/my_process.pid`
  - Displays `manage_my_process restarted`
- Displays `Usage: manage_my_process {start|stop|restart}` if any other argument or no argument is passed
- 
Note that this init script is far from being perfect (but good enough for the sake of manipulating process and PID file), for example we do not handle the case where we check if a process is already running when doing `./101-manage_my_process start`, in our case it will simply create a new process instead of saying that it is already started.

sylvain@ubuntu$ sudo ./101-manage_my_process
Usage: manage_my_process {start|stop|restart}
sylvain@ubuntu$ sudo ./101-manage_my_process start
manage_my_process started
sylvain@ubuntu$ tail -f -n0 /tmp/my_process 
I am alive!
I am alive!
I am alive!
I am alive!
^C
sylvain@ubuntu$ sudo ./101-manage_my_process stop
manage_my_process stopped
sylvain@ubuntu$ cat /var/run/my_process.pid 
cat: /var/run/my_process.pid: No such file or directory
sylvain@ubuntu$ tail -f -n0 /tmp/my_process 
^C
sylvain@ubuntu$ sudo ./101-manage_my_process start
manage_my_process started
sylvain@ubuntu$ cat /var/run/my_process.pid 
11864
sylvain@ubuntu$ sudo ./101-manage_my_process restart
manage_my_process restarted
sylvain@ubuntu$ cat /var/run/my_process.pid 
11918
sylvain@ubuntu$ tail -f -n0 /tmp/my_process 
I am alive!
I am alive!
I am alive!
^C
sylvain@ubuntu$ 
Repo:
- GitHub repository: `alx-system_engineering-devops`
- Directory: `0x05-processes_and_signals`
- File: `101-manage_my_process, manage_my_process`







## Emphasis

**This is bold text**

__This is bold text__

*This is italic text*

_This is italic text_

~~Strikethrough~~


## Blockquotes


> Blockquotes can also be nested...
>> ...by using additional greater-than signs right next to each other...
> > > ...or with spaces between arrows.


## Lists

Unordered

+ Create a list by starting a line with `+`, `-`, or `*`
+ Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    * Ac tristique libero volutpat at
    + Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
+ Very easy!

Ordered

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa


1. You can use sequential numbers...
1. ...or keep all the numbers as `1.`

Start numbering with offset:

57. foo
1. bar


## Code

Inline `code`

Indented code

    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code


Block code "fences"

```
Sample text here...
```

Syntax highlighting

``` js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```

## Tables

| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |

Right aligned columns

| Option | Description |
| ------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |


## Links

[link text](http://dev.nodeca.com)

[link with title](http://nodeca.github.io/pica/demo/ "title text!")

Autoconverted link https://github.com/nodeca/pica (enable linkify to see)


## Images

![Minion](https://octodex.github.com/images/minion.png)
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

Like links, Images also have a footnote style syntax

![Alt text][id]

With a reference later in the document defining the URL location:

[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"


## Plugins

The killer feature of `markdown-it` is very effective support of
[syntax plugins](https://www.npmjs.org/browse/keyword/markdown-it-plugin).


### [Emojies](https://github.com/markdown-it/markdown-it-emoji)

> Classic markup: :wink: :cry: :laughing: :yum:
>
> Shortcuts (emoticons): :-) :-( 8-) ;)

see [how to change output](https://github.com/markdown-it/markdown-it-emoji#change-output) with twemoji.


### [Subscript](https://github.com/markdown-it/markdown-it-sub) / [Superscript](https://github.com/markdown-it/markdown-it-sup)

- 19^th^
- H~2~O


### [\<ins>](https://github.com/markdown-it/markdown-it-ins)

++Inserted text++


### [\<mark>](https://github.com/markdown-it/markdown-it-mark)

==Marked text==


### [Footnotes](https://github.com/markdown-it/markdown-it-footnote)

Footnote 1 link[^first].

Footnote 2 link[^second].

Inline footnote^[Text of inline footnote] definition.

Duplicated footnote reference[^second].

[^first]: Footnote **can have markup**

    and multiple paragraphs.

[^second]: Footnote text.


### [Definition lists](https://github.com/markdown-it/markdown-it-deflist)

Term 1

:   Definition 1
with lazy continuation.

Term 2 with *inline markup*

:   Definition 2

        { some code, part of Definition 2 }

    Third paragraph of definition 2.

_Compact style:_

Term 1
  ~ Definition 1

Term 2
  ~ Definition 2a
  ~ Definition 2b


### [Abbreviations](https://github.com/markdown-it/markdown-it-abbr)

This is HTML abbreviation example.

It converts "HTML", but keep intact partial entries like "xxxHTMLyyy" and so on.

*[HTML]: Hyper Text Markup Language

### [Custom containers](https://github.com/markdown-it/markdown-it-container)

::: warning
*here be dragons*
:::
