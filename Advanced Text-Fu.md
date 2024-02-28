* regex (Regular Expressions):
	* Test String: 
	  *"sally sells seashells* 
	  *by the seashore"*
	 * **Beginning of a line with ^**
		 * ^by : would match the line *by the seashore*
	 * **End of a line with $**
		 * seashore$ : would match the line *by the seashore*
	 * **Matching any single character with .**
		 * b. : would match *by*
	 * **Bracket notation with []**
		 * **d**[iou]g : would match: dig, dog, dug
		 * d [ ^i ]g : would match: dog and dug but not dig
		 * d[a-c]g : will match patterns like dag, dbg, and dcg
		 * d[A-C]g : will match dAg, dBg and dCg but not dag, dbg and dcg
 * vim search patterns:
	 * Example: A file contains the following text: "My pretty file is very pretty."
	 * "/" search pattern:
		 * While you are in a vim session, To search for an expression just type the / key and then your search result 
	 * "?" search pattern:
		 * The ? search command will search the text file backwards, so in the above example, the last pretty would come up first.
	 *  Once you hit enter, you can press "n" to go forward or "N" to go backward in your search results.
 * vim appending texts:
	 * To insert something in the file, we need to move from command mode to insert mode.
	 *  i - insert text before the cursor
	 * a - append text after the cursor
	 * O - insert text on the previous line
	 -  o - insert text on the next line
	 -  A - append text at the end of the line
 - vim editing:
	* x - used to cut the selected text also used for deleting characters
	- dd - used to delete the current line
	- y - yank or copy whatever is selected
	- yy - yank or copy the current line
	- p - paste the copied text before the cursor
- vim Saving and Exiting:
	- - :w - writes or saves the file
	- :q - quit out of vim
	- :wq - write and then quit
	- :q! - quit out of vim without saving the file
	- ZZ - equivalent of :wq, but one character faster
	- u - undo your last action
	- Ctrl-r - redo your last action
	
	  