Automated Backup Using Batch Script and Task Scheduler
This guide explains how to automate folder backups on Windows using a batch file and Task Scheduler.

Steps to Set Up the Automated Backup
1. Create the Batch File
Open a text editor (e.g., Notepad).

Add the following code to your batch file (backup.bat):

bat
Copy code
@echo off
xcopy "C:\Path\To\SourceFolder" "D:\Path\To\DestinationFolder" /E /H /C /I
echo Backup completed on %date% at %time% >> "D:\Path\To\DestinationFolder\backup_log.txt"
pause
Explanation:

C:\Path\To\SourceFolder: Replace this with the folder you want to back up.
D:\Path\To\DestinationFolder: Replace this with the folder where the backup will be stored.
/E /H /C /I: Options to include subfolders, hidden files, and overwrite without prompts.
A log entry will be saved in the destination folder.
Save the file with a .bat extension (e.g., backup.bat).

2. Set Up Task Scheduler
Open Task Scheduler (search for it in the Start menu).
Click Create Basic Task on the right-hand menu.
Enter a Name (e.g., "Daily Backup") and a Description (optional), then click Next.
Choose the Trigger (e.g., "Daily") and set the desired time for the backup to run. Click Next.
Select the Action as "Start a Program" and click Next.
Browse and select your backup.bat file.
Click Finish to save the task.
3. Verify the Task
After an hour or at the scheduled time, the batch script will execute, copying the source folder to the destination folder and logging the operation.
