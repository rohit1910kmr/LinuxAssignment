# Linux-Assignment-4

**Q1. Create a directory named "MyFiles" in your home directory. Navigate into this directory and list its contents.**


```
mkdir Myfilies
```

```
ls  Myfilies/
```




**Q2 Copy a file named "document.txt" from your home directory to the "MyFiles" directory. Move the file to a subdirectory named "Documents" within "MyFiles."**

```
touch document.txt
```

```
cp document.txt Myfilies/
```

```
ls Myfilies/
```

```
cd Myfilies/
```

```
mkdir Documents
```

```
mv document.txt Documents/
```

```
ls Documents/
```



**Q3. Create an empty file named "notes.txt" in the "MyFiles" directory. Afterward, delete the file.**
```
cd Myfilies/
```
```
touch notes.txt
```
```
rm notes.txt
```


**Q4. Create a hard link named "hardlink.txt" for the file "document.txt" within the "Documents" subdirectory. Also, create a symbolic link named "symlink.txt" in the same location.**
```
ln document.txt Myfilies/Documents/hardlink.txt
```
```
ln -s document.txt Myfilies/Documents/symlink.txt
```


**Q5. In the "MyFiles" directory, use a single command to list all files that start with the letter "a" and have a ".txt" extension.**
```
cd Myfilies/
```
```
touch aman.txt abcdef.txt auto autom.txt
```
```
ls a*.txt
```


**Q6. Rename all files in the "Documents" subdirectory of "MyFiles" with a ".bak" extension. Ensure the original file names are preserved.**


```
ls
```
```
vim a.sh
```
```
cat a.sh
```
```
bash a.sh
```




**Q7. Use a wildcard character to copy all files from the "Documents" subdirectory of "MyFiles" to another directory named "Backup."**
```
cd Myfilies/
```
```
mkdir Backup
```
```
cd Documents/
```
```
cp * ../Backup/
```
```
ls ../Backup/
```



**Q8. Execute the ls command to list files in the current directory. Save the output to a file named "file\_list.txt." Then, use a pipe to filter the output through grep to display only files with a ".txt" extension.**
```
ls > file_list.txt
```
```
cat file_list.txt
```
```
cat file_list.txt | grep .txt
```


****

**Q9. Create a new text file named "my\_notes.txt" using the touch command. Open the file in the Vim editor, add some text, and save the changes.**
```
touch my_notes.txt
```
```
vim my_notes.txt
```
```
cat my_notes.txt
```



**Q10. Run the date command and store the output in a variable named "current\_date." Display the value of the variable and append it to the "my\_notes.txt" file.**

```
current_date=$(date)
```
```
echo $current_date
```
```
cat my_notes.txt
```
```
echo $current_date >> my_notes.txt
```
```
cat my_notes.txt
```



**Q11. Edit the Bash startup script (e.g., .bashrc) to set an environment variable named "CUSTOM\_PATH" to a specific directory path. Ensure the variable is available in new shell sessions.**

```
vim .bashrc
```
```
source ~/.bashrc
```
```
echo $CUSTOM_PATH
```


****![](https://lh7-us.googleusercontent.com/JHLDvRHmQ6Q3tRxClitpLlw42j-ruM6kkemgGT7WwLxzEpBL2A_fTsDp8LzBkUqymsGLNQvtaTy7cDm0Ir6Mf9-cQ4cKm_eu456Q_v_pY3Lp_ZFQZk_C91CLWkzjag0jqvZxbSsOoGWHtH5JwnZx430)****

****![](https://lh7-us.googleusercontent.com/EvRsNKcEg_bPIg_27WhCTNYXHrGIJ4remP_wwTBCED-RfIJuO6zg0ADKolh4JTpjJ0SyTOVjo1T4j1qpfVZ7JDycFRQIkk-tc9IFZSWVG4LRCBArasuvdAcyviiTaEyT5DiqWyeR9F0jpk7xquo5EOs)****

**Q12. Use the echo command to add a new line of text to the "my\_notes.txt" file without overwriting existing content. Verify that the new text is appended.**
```
cat my_notes.txt
```
```
echo "I am writing text in new line" >> my_notes.txt
```
```
cat my_notes.txt
```**

**Q13. List all files in the "/etc" directory, filter the output to include only those containing the word "conf," and save the result to a file named "conf\_files.txt."**

```
ls /etc | grep 'conf' > conf_files.txt
```

```
cat conf_files.txt 
```
*

**Q14. Open the "my\_notes.txt" file in Vim. Use Vim's search and replace functionality to replace all occurrences of the word "important" with "critical." Save the changes.**
```
vim my_notes.txt
```
**Note:-** 
**After opening file write below command after press shift + colon**







*


**Q15. Create a new user account named "john\_doe." Set the user's home directory to "/home/john\_doe" and assign the user to the "users" group.**

```
grep '^users:' /etc/group
```
```
sudo adduser --home /home/john_doe john_doe
```
```
sudo usermod -aG users john_doe
```

```
id john_doe
```
****![](https://lh7-us.googleusercontent.com/7AunDC2SZpDQhgpQ6cjHEK3nw0FKJPYa1quVznUXBC3mfAdCu9Hmu0yfTvmQyOjVKNNGvQPI7R-AAZ09b3ulvvcmQ-OErzBRngKUSzg9im1o5TbbSi-qxkPItKN4Tof1UjmNodTCrh5ABG42arXZL1M)****

**Q16. Add the user "john\_doe" to the sudoers file, allowing them superuser privileges. Confirm that "john\_doe" can execute commands with sudo.**

```
sudo usermod -aG users john_doe
```

```
id john_doe
```
```
su - john_doe
```
```
sudo apt update
```
```
exit
```
```
sudo usermod -aG sudo john_doe
```

```
id john_doe
```
```
su - john_doe
```

```
sudo su
```

****![](https://lh7-us.googleusercontent.com/-YRZXZVpojUFAvaTHdQvVbbfe1nzTk5JtJgSRTR4EvH_PyVXrGrv3oHqlDWcVkTQTI8KFEdZU__mEHiyCpVo6p5oEAptkFTe_fJVJCpTdunVT6Z1_AulEUhv8bjA2hUMxqNJCM_ErYnAdsEdNILcXD0)****

**Q17. Modify the user account "john\_doe" to change the default shell to "/bin/bash" and set the account's expiration date to one month from today.**
```
sudo chsh -s /bin/bash john_doe
```
```
sudo chage -E $(date -d "+1 month" +"%Y-%m-%d") john_doe
```
```
sudo chage -l john_doe
```
```
grep john_doe /etc/passwd
```

****![](https://lh7-us.googleusercontent.com/hOY_oeXSR8hxEI2q-E0gNfJE9utdjG1LWmNO6K6SQ8DmVpO_s5imeFE534A9HojwK893GnsjsIxHVrgScqufmRJA64wUzh7Gn_y-jxWJzczVf1f3heRP8g3lOIMrzsPgYilBvAVIY1UgZwRcdEgLj9M)****


**Q18. Create a new group named "development\_team." Add "john\_doe" to this group and verify the group's existence.**

```
grep development_team /etc/group
```
```
sudo addgroup development_team
```
```
grep development_team /etc/group
```
```
sudo adduser john_doe development_team
```
```
id john_doe
```

**

**Q19. Remove "john\_doe" from the "users" group and add them to the "development\_team" group. Confirm the changes.**

```
id john_doe
```

```
sudo deluser john_doe users
```
```
sudo adduser john_doe development_team
```
```
id john_doe
```
***

 

**Q20. Delete the user account "john\_doe" and ensure that their home directory is also removed.**
```
sudo deluser --remove-home john_doe
```
```
id john_doe
```

```
ls /home/john_doe
```
**

**Q21. Delete the group "development\_team" and ensure that all users previously belonging to the group are appropriately handled.**

```
sudo deluser john_doe development_team
```
```
sudo delgroup development_team
```
```
grep development_team /etc/group
```


**Q22. Implement a password policy that requires users to change their passwords every 90 days. Apply this policy to all existing and new user accounts.**

```
sudo chage -M 90 -m 0 -W 7 -I 30 -E -1 $(cut -d: -f1 /etc/passwd)
```
```
sudo sed -i '/^PASS_MAX_DAYS/c\PASS_MAX_DAYS   90' /etc/login.defs
```
```
sudo chage -l john_doe
```
```
grep PASS_MAX_DAYS /etc/login.defs
```




**Q23. Manually lock the user account "john\_doe." Attempt to log in as "john\_doe" to confirm that the account is locked. Then, unlock the account.**

```
sudo passwd -l john_doe
```
```
su - john_doe
```
```
sudo su - john_doe
```
```
sudo passwd -u john_doe
```
```
exit
```

```
sudo passwd -u john_doe
```
```
su - john_doe
```


**Q24. Use the id command to display detailed information about the "john\_doe" user, including user ID, group ID, and supplementary groups.**
```
id john_doe
```



**Q25. Configure the password aging for the user "john\_doe" to enforce a maximum password age of 60 days. Confirm that the changes take effect.**

```
sudo adduser john_doe
```

```
sudo grep 'john_doe' /etc/passwd
```

```
sudo chage -M 60 john_doe
```
```
sudo chage -l john_doe
```
