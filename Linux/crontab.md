# crontab

* Crontab is a time-based scheduling utility in Unix-based operating systems.
* It is used to automate repetitive tasks by scheduling commands or scripts to run at specific intervals, such as every `minute`, `hour`, `day`, `week`, or `month`.
* The crontab command allows users to create, edit, and manage their own cron jobs, which are stored in a file known as a `crontab` file.
* Each line in the crontab file represents a single cron job, and includes a set of time and date fields, as well as the command or script to be executed.

**The syntax of a crontab**
```
* * * * * Command
```
* The five asterisks (*) represent the time and date fields for `minutes`, `hours`, `day of the month`, `month`, and `day of the week`, respectively. A value of `*` in a field means "any value".
* The `command` is the command or script to be executed, along with any necessary arguments or options.
```
minute hour day week month [command]
```
* Crontab provides a flexible and powerful way to automate tasks in Ubuntu and other Unix-based systems, and can be useful for a wide range of purposes, such as `backups`, `data processing`, and `system maintenance`.

# Crontab Fields and Allowed Ranges
`
Field    Description    Allowed Value
MIN      Minute field    0 to 59
HOUR     Hour field      0 to 23
DOM      Day of Month    1-31
MON      Month field     1-12
DOW      Day Of Week     0-6
CMD      Command         Any command to be executed.
`
<br></br>

# To schedule a cron job in Ubuntu, you can follow these steps:

1. Open the crontab file in your preferred text editor. You can do this by typing the following command in your terminal:
```
crontab -e
```
If this is the first time you're opening the crontab file, you may be prompted to choose a default text editor like `nano` or `vim`.

2. Once the crontab file is open, you can add a new job by adding a new line to the end of a file. 

Each line represents a separate job, and has the following format:
```
* * * * * /path/to/command arg1 arg2
```
The five asterisks represent the scheduling information, and the rest of the line specifies the command to be executed. 

* For example, the following line would run the command `/usr/bin/mycommand` every day at 5:30am:
```
30 5 * * * /usr/bin/mycommand
```
3. Save the crontab file and exit the editor. Your changes will take effect immediately.

4. To view the list of existing cron jobs, you can type the following command in your terminal:
```
crontab -l
```
This will display the current crontab file in your terminal.

* `Note` that when specifying paths to commands in your crontab file, it's important to use absolute paths (e.g., /usr/bin/mycommand), since cron jobs run in a different environment than your user's shell.














