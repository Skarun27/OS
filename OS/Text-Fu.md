
* stdout (Standard Out) :
	* echo Hello World > peanuts.txt :
		* *If peanuts file already exists it will empty the file content and write Hello World to it; else creates a new file named peanuts and write*
	* echo Hello World >> peanuts.txt : 
		* *Instead of removing file content, it appends to the existing content*

* stdin (Standard In) :
	* Just like we had **>** for stdout redirection, we can use **<** for stdin redirection.
	* Example : $ cat **<** peanuts.txt **>** banana.txt:
		* *we redirected peanuts.txt to be our stdin for cat command*
		* *Then the output of cat peanuts.txt which would be Hello World gets redirected to another file called banana.txt.*
* stderr (Standard Error) :
	* We will have to use file descriptors.
	* File Descriptors:
		* A file descriptor is a non-negative number that is used to access a file or stream.
		* file descriptor for stdin, stdout and stderr is 0, 1, and 2 respectively.
	* ls /fake/directory 2> peanuts.txt :
		* *should see just the stderr messages in peanuts.txt.*
	* ls /fake/directory > peanuts.txt 2>&1 :
		*  To see both stderr and stdout in the peanuts.txt file
	* ls /fake/directory &> peanuts.txt
		* Shorter way to redirect both stdout and stderr to a file
	* ls /fake/directory 2> /dev/null
		* Redirecting output to a special file /dev/null and it will discard any input.
* pipe
	* The pipe operator |, represented by a vertical bar, allows us to get the stdout of a command and make that the stdin to another process
	* ls -la /etc | less 
* tee
	* writes the output of my command to two different streams
	* ls | tee peanuts.txt
* env (Environment)
	* This outputs a whole lot of information about the environment variables you currently have set. These variables contain useful information that the shell and other processes can use.
	* $ echo $PATH : /usr/local/sbin:/usr/local/bin:/usr/sbin:/bin
		* This returns a list of paths separated by a colon that your system searches when it runs a command. Let's say you manually download and install a package from the internet and put it in to a non standard directory and want to run that command, you type $ coolcommand and the prompt says command not found. Well that's silly you are looking at the binary in a folder and know it exists. What is happening is that $PATH variable doesn't check that directory for this binary so it's throwing an error.
		* Let's say you had tons of binaries you wanted to run out of that directory, you can just modify the PATH variable to include that directory in your PATH environment variable.
* Text Processing commands
	* echo 'The quick brown; fox jumps over the lazy  dog' > sample.txt
	* **cut**:
		* cut -c 5 sample.txt
			* This outputs the 5th character in each line of the file. In this case it is "q", note that the space also counts as a character.
		* $ cut -f 2 sample.txt
			* The -f or field flag cuts text based off of fields, by default it uses TABs as delimiters, so everything separated by a TAB is considered a field. You should see "dog" as your output.
		* $ cut -f 1 -d ";" sample.txt
			* This will change the TAB delimiter to a ";" delimiter and since we are cutting the first field, the result should be "The quick brown".
	* **paste**:
		* paste -s sample.txt (-s for serialize)
			* The default delimiter for paste is TAB, so now there is one line with TABs separating each word.
		* paste -d ' ' -s sample2.txt
			* Since delimiter (-d) is changed to space, there is one line with single space separating each word.
	* **head**:
		* By default the head command will show you the first 10 lines in a file.
		* $ head /var/log/syslog
		* $ head -n 15 /var/log/syslog
			* We can modify number of lines visible by using -n (number of lines) flag
	* **tail**:
		* Similar to head command, the tail command lets you see the last 10 lines of a file.
		* tail /var/log/syslog
		* tail -n 10 /var/log/syslog
			* Along with head you can change the number of lines you want to see.
		* tail -f /var/log/syslog
			* Your syslog file will be continually changing while you interact with your system and using tail -f you can see everything that is getting added to that file.
		* tail -f -n 20 /var/log/syslog
			* Using `-f` and `-n` together combines the benefits of both options, providing both a snapshot of recent activity and a live feed of new events or log entries.
	* **expand:** 
		* expand sample.txt
			* The command above will print output with each TAB converted into a group of spaces.
		* expand sample.txt > result.txt
			* To save this output in a file, use output redirection like below.
	* **unexpand:**
		* unexpand -a result.txt
			* Opposite to expand, we can convert back each group of spaces to a TAB with the unexpand command.
	* **join:**
		* Multiple files can be joined together by the first field by default and the fields have to be identical
		* join file1.txt file2.txt
		* see https://linuxjourney.com/lesson/join-split-command for more info
	* **split:**
		*  split somefile
			* This will split the file into different files, by default it will split them once they reach a 1000 line limit. The files are named x** by default.
	* **sort:**
		* The sort command is useful for sorting lines.
		* sort file1.txt
		* sort -r file1.txt
			* This does a reverse sort.
		* sort -n file1.txt
			* This sorts via numerical value.
		* see https://linuxjourney.com/lesson/sort-command for more info
	* **tr (Translate):**
		* The tr (translate) command allows you to translate a set of characters into another set of characters in the input provided (file or key input)
		* tr a-z A-Z < sample.txt > result.txt
			* converts all lowercase letters in sample.txt to uppercase letters in result.txt
	* **uniq (Unique):**
		* uniq sample.txt
			* Let's say we had a file with lots of duplicates lines, uniq command helps us remove the duplicate.
		* uniq -c sample.txt
			* Helps us get the count of occurrences of each line
		* uniq -u sample.txt
			* Helps us get only unique values
		* uniq -d reading.txt
			* Helps us get duplicate values
		* sort sample.txt | uniq
		* **Note:** uniq does not detect duplicate lines unless they are adjacent, to overcome this limitation we can use sort in combination with uniq.
	* **wc (Word count):**
		* wc /etc/password
			* wc displays the number of lines, number of words and number of bytes, respectively.
			* 96     265    5925 /etc/passwd
			* To just see just the count of a certain field, use the -l, -w, or -c respectively.
		* wc -l /etc/passwd
			* This outputs count only for number of lines (96)
	* **nl (Number line):**
		* nl file1.txt
			* Adds incrementing number before each of the line in the file, we can use this method to know the total number of lines in a file. 
	* **grep:**
		* $ grep fox sample.txt
			* Helps us know if a file existed in a certain directory or if a string was found in a file
		* $ grep -i somepattern somefile
			* also grep patterns that are case insensitive with the -i flag
		* $ env | grep -i User
			* To get even more flexible with grep you can combine it with other commands with |.
		* $ ls /somedir | grep '.txt$'
			* Should return all files ending with .txt in somedir.
			* The `$` ensures that `.txt` appears at the very end of the line, matching file names like `document.txt` but not `document.txt.backup`.
