man: ps, pgrep, pkill, kill, exit

help: trap

For those who want to know more and learn about all signals, check out this article.

At the end of this project you are expected to be able to explain, without the help of Google:

What is a PID
What is a process
How to find a process PID
How to kill a process
What is a signal
What are the 2 signals that cannot be ignored
Allowed editors: vi, vim, emacs
All your files will be interpreted on Ubuntu 14.04 LTS
All your files should end with a new line
A README.md file, at the root of the folder of the project, is mandatory
All your Bash script files must be executable
Your Bash script must pass Shellcheck (version 0.3.3-1~ubuntu14.04.1 via apt-get) without any error
The first line of all your Bash scripts should be exactly #!/usr/bin/env bash
The second line of all your Bash scripts should be a comment explaining what is the script doing
Write a Bash script that displays its PID.

GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 0-what-is-my-pid
Write a Bash script that displays a list of currently running processes.

Requirements:

Must show all processes, for all users, including those which might not have a TTY
Display a user-oriented format
Show process hierarchy
GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 1-list_your_processes
Using your previous exercise command, write a Bash script that displays line containing the bash word, this allowing you to easily get the PID of your Bash process

Requirements:

You cannot use pgrep
The third line of your script must be # shellcheck disable=SC2009 (for more info about ignoring shellcheck error here)
Here we can see that my Bash PID is 4404.

GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 2-show_your_bash_pid
Write a Bash script that displays the PID, along with the process name, of processes which name contains the word bash.

Requirements:

You cannot use ps
Here we can see that:

For the first iteration: bash PID is 4404 and that the 3-show_your_bash_pid_made_easy script PID is 4555
For the second iteration: bash PID is 4404 and that the 3-show_your_bash_pid_made_easy script PID is 4557
GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 3-show_your_bash_pid_made_easy
Write a Bash script that displays To infinity and beyond indefinitely.

Requirements:

In between each iteration of the loop, add a sleep 2
Note that I ctrl+c (killed) the Bash script in the example.

GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 4-to_infinity_and_beyond
We killed our 4-to_infinity_and_beyond process using ctrl+c in the previous task, there is actually another way to do this.

Write a Bash script that kills 4-to_infinity_and_beyond process.

Requirements:

You must use kill
Terminal #0

Terminal #1

I opened 2 terminals in this example, started by running my 4-to_infinity_and_beyond Bash script in terminal #0 and then moved on terminal #1 to run 5-kill_me_now. We can then see in terminal #0 that my process has been terminated.

GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 5-kill_me_now
Write a Bash script that kills 4-to_infinity_and_beyond process.

Requirements:

You cannot use kill or killall
Terminal #0

Terminal #1

I opened 2 terminals in this example, started by running my 4-to_infinity_and_beyond Bash script in terminal #0 and then moved on terminal #1 to run 6-kill_me_now_made_easy. We can then see in terminal #0 that my process has been terminated.

GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 6-kill_me_now_made_easy
Write a Bash script that displays:

To infinity and beyond indefinitely
With a sleep 2 in between each iteration
I am invincible!!! when receiving a SIGTERM signal
Make a copy of your 6-kill_me_now_made_easy script, name it 67-kill_me_now_made_easy, that kills the 7-highlander process instead of the 4-to_infinity_and_beyond one.

Terminal #0

Terminal #1

I started 7-highlander in Terminal #0 and then run 67-kill_me_now_made_easy in terminal #1, for every iteration we can see I am invincible!!! appearing in terminal #0.

GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 7-highlander
Write a Bash script that kills the process 7-highlander.

Terminal #0

Terminal #1

I started 7-highlander in Terminal #0 and then run 8-beheaded_process in terminal #1 and we can see that the 7-highlander has been killed.

GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 8-beheaded_process
Write a Bash script that:

Creates the file /var/run/holbertonscript.pid containing its PID
Displays To infinity and beyond indefinitely
Displays I hate the kill command when receiving a SIGTERM signal
Displays Y U no love me?! when receiving a SIGINT signal
Deletes the file /var/run/holbertonscript.pid and terminate itself when receiving a SIGQUIT or SIGTERM signal
"Y U no love me?!" picture

Executing the 9-process_and_pid_file script and killing it with ctrl+c.

Terminal #0

Terminal #1

Starting 9-process_and_pid_file in the terminal #0 and then killing it in the terminal #1.

GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 9-process_and_pid_file
Priest stopping data center with /etc/init.d/DEAMON STOP

Read:

&
init.d
Daemon
Positional parameters
man: sudo

Programs that are detached from the terminal and running in the background are called daemons or processes, need to be managed. The general minimum set of instructions is: start, restart and stop. The most popular way of doing so on Unix system is to use the init scripts.

Write a manage_my_process Bash script that:

Indefinitely writes I am alive! to the file /tmp/my_process
In between every I am alive! message, the program should pause for 2 seconds
Write Bash (init) script 10-manage_my_process that manages manage_my_process

Requirements:

When passing the argument start:
Starts manage_my_process
Creates a file containing its PID in /var/run/my_process.pid
Displays manage_my_process started
When passing the argument stop:
Stops manage_my_process
Deletes the file /var/run/my_process.pid
Displays manage_my_process stopped
When passing the argument restart
Stops manage_my_process
Deletes the file /var/run/my_process.pid
Starts manage_my_process
Creates a file containing its PID in /var/run/my_process.pid
Displays manage_my_process restarted
Displays Usage: manage_my_process {start|stop|restart} if any other argument or no argument is passed
Note that this init script is far from being perfect (but good enough for the sake of manipulating process and PID file), for example we do not handle the case where we check if a process is already running when doing ./10-manage_my_process start, in our case it will simply create a new process instead of saying that it is already started.

GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 10-manage_my_process
Zombie searhose

Read what a zombie process is.

Write a C program that creates 5 zombie processes.

Requirements:

For every zombie process created, it displays Zombie process created, PID: ZOMBIE_PID
Your code should use the Betty style. It will be checked using betty-style.pl and betty-doc.pl
When you code is done creating the parent process and the zombies, use the function bellow
Example:

Terminal #0

Terminal #1

In Terminal #0, I start by compiling 11-zombie.c and executing zombie which creates 5 zombie processes.

GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 11-zombie.c
Now that you master signals, what about sharing your knowledge?

Create a screencast where you live-code a task of your choice from this project or even a mix of them.

Requirements:

Step by step video
Two minutes of above
Done in English
Published to Youtube
While you are free to choose the recording system to record the screencast, I highly recommend screencast-o-matic.

Once you are done, please share the Youtube URL in your answer file and below.

We'll be watching you!

eating popcorn and being impressed

GitHub repository: holberton-system_engineering-devops
Directory: 0x05-processes_and_signals
File: 12-screencast_unix_signal
Unless stated, all your projects will be auto-corrected with Ubuntu 14.04 LTS.
