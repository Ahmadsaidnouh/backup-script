# Backup Script

## Made by:

- Ahmad Said Nouh
  - ID: 7086

## Contents:

- [Backup Script](#backup-script)
  - [Made by:](#made-by)
  - [Contents:](#contents)
  - [User Manual](#user-manual)
    - [Starting the program](#starting-the-program)
    - [Enter inputs](#enter-inputs)
    - [How to enter directory names](#how-to-enter-directory-names)
  - [Input Validations](#input-validation)

## User Manual

### Starting the program

First run ___sudo apt install make___ command if ___make___ command is not installed on your machine. Then, open the directory named ___main___ in a terminal. Then just run ___make___ command. That's it...  

### Enter inputs

Once you run ___make___ command, the program will ask you to enter the four inputs as shown in the image below. 
![inputs](imgs/input.png)
- First input ___dir___ : it is the directory to be backed up, must be existing directory.
- Second input ___backupdir___ : it is the backup destination directory. You have two options here, you either specify its name or just leave this option empty and the program will automatically backup to a default directory ___~/backups___.Therefore, there are 6 cases:
  - cases1: default directory ___~/backups___ and it's not exiting ==============> will create it then proceed backing up directly. 
  - cases2: default directory ___~/backups___ and it's exiting but empty ========> will proceed backing up directly. 					
  - cases3: default directory ___~/backups___ and it's exiting but not empty ====> will firstly ask the user if he want to delete all existing files in __~/backups__. If user said yes, the program will delete all existing files then proceed backing up directly. If user said no, the program will terminate execution without any deletion. 
  - cases4: user specified directory and it's not existing ======================> will create it then proceed backing up directly. 	
  - cases5: user specified directory and it's existing but empty ================> will proceed backing up directly. 						
  - cases6: user specified directory and it's existing but not empty ============> will display error message and then terminate execution without any deletion. 
- Third input ___interval-sec___ : it is how many seconds the program should wait before checking for a new backup.
- Fourth input ___max-backups___ : it is the maximum number of backups to be stored in the ___backupdir___. If maximum backups is reached and a new backup needs to be added, the program will delete the oldest backup and then add the new one.

  

### How to enter directory names
All directories that will be dealed with must be below your home directory. Therefore, any directory name you will enter to the program must be relative to the (\~/). The tilde (\~) is a Linux "shortcut" to denote a user's home directory. Thus tilde slash (\~/) is the beginning of a path to a file or directory below the your home directory. For example, if you have a directory named ___abc___ below your home directory then its path is ___~/abc___. So if you want to back it up then just enter to the program ___abc___ , not ___~/abc___. Also, if you have a directory named ___xyz___ below that ___abc___ directory then its path is ___~/abc/xyz___. So, if you want to back it up then just enter to the program ___abc/xyz___ , not ___~/abc/xyz___. 

##Input Validations

