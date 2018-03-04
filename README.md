# transpose
Copy of https://sourceforge.net/projects/transpose/
This is just a mirror / unmaintained fork of the original project by Alex Sheppard (and/or batchainpuller ?).

## Original README:
### To Compile:
	gcc transpose.c -o transpose

### To Install - Just copy into your path. e.g.:
	cp transpose /usr/local/bin/


#### Changes: 2.0
	Another big revision in the code. Whilst 1.91 was great when you specified exact dimensions, it handled other scenarios clumsily. This version handles both known and unkown dimension matrices efficiently and through a common codepath. This version also see the return of the possibility to use 2byte separators and the '--win' switch as a convienent way to set the line separator to '\r\n' - the 'Windows newline.' 
	Also, transposing is no longer the only transformation that can be performed. Cropping, padding, and otherwise reshaping of a delimited text matrix can also be achieved using the --input, --output, and --transpose options.

#### Changes: 1.91
	BUG FIXED - strings were not properly terminated leading to nonsense trailing characters in the output.

#### Changes: 1.90
	The code has been greatly simplified, and hopefully transpose is now more efficient. It also copes better with badly shaped input files.
Where possible, you should use the new options --width and --height to specify the dimensions of the input matrix. Cropping or padding (with empty fields) occurs if the actual input data does not match the specified dimensions. If you don't specify either dimension, the whole file will be scanned in a preliminary run to determine the dimensions required to accomodate all rows and the number of columns in the longest row - clearly this is less efficient than specify the dimensions explicitly. If reading input from a non-seekable source (e.g. a pipe) and not specifying dimensions, you need to use the --withtemp option. Without doing this, the preliminary run will exhaust the input data and the transposing routines will operate on an empty input!
	The line separator now can only be a single character. If you have \r\n separators, you need to convert these before using transpose.

#### Request:
Please test and report any problems. Suggestions for new features are also welcome.   


