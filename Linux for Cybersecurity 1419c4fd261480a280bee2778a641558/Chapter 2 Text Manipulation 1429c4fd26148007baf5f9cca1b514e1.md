# Chapter 2 Text Manipulation

`head “file”` - If you just want to view the beginning of a file, you can use the head command. By default, this command displays the first 10 lines of a file. 

`head -n 5 “file” -` specific number of lines

`tail “file”` -  . By default, it shows the last 10 lines of a file or input passed to it. You can modify the number of lines displayed using various options.

tail `-n 5 “file” -` specific number of lines

`nl “file”` - displays lines but it numbers them too

`sed s/mysql/MySQL/g /etc/snort/snort.conf > snort2.conf` - You should see that the grep command found two occurrences of mysql. Let’s say you want sed to replace every occurrence of mysql with MySQL and then save the new file to snort2.conf. You could do this by entering the command shown in

`more /etc/snort/snort.conf` - **Scroll Through File**: Use spacebar to move to the next page, or enter to move line by line

`less /etc/snort/snort.conf` - use `/` to search specific word