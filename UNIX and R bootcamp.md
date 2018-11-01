# UNIX Hands-on

Directory or Folder paths to work on

`/home/ubuntu/Desktop/Unix_and_R basics`

`/home/ubuntu/Desktop/QC`

#### Access the Directories

`Ctrl + alt + t`

`cd Desktop/Unix_and_R_basics`


`ls`						&rarr;List directory contents

`ls –l`					&rarr;List with information in bytes

`ls –a`					&rarr;List with hidden contents

`ls –lh`				&rarr;List with information (Human readable)


#### Basic commands

`cd ..`						      &rarr;Go back to previous directory

`cp file1 file2`        &rarr;Copy file1 and paste contents to file 2

`mv file1 file2`        &rarr;Move or rename file1 to file2

`rm file`               &rarr;Remove file

`rmdir directory`       &rarr;Remove directory

`grep 'keyword' file`   &rarr;Search a file for keywords


#### Try this out

`cd /home/ubuntu/Desktop/Unix_and_ R_basics`

`grep '35' decimal.txt > new_decimal.txt`       &rarr;Create a file with the matched lines

`grep '45' decimal.txt >> new_decimal.txt`      &rarr;Does the same but append

`wc file`                                       &rarr;Count number of lines/word/characters in file

`cat decimal.txt`                               &rarr;Dump a file to the screen 

`more decimal.txt`                              &rarr;Progressively dump a file to the screen

`less decimal.txt`                              &rarr;Gives preview of the file

`vi decimal.txt`                                &rarr;Edit a file using vi editor

`gedit decimal.txt`                             &rarr;Edit a file using the gedit editor

`head decimal.txt`                              &rarr;Show the first few lines of a file

`head -25 decimal.txt`                          &rarr;Show the first 25 lines of a file

`tail decimal.txt`                              &rarr;Show the last few lines of a file

`tail -25 decimal.txt`                          &rarr;Show the last 25 lines of a file

#### Sort

`sort alpha.txt`              &rarr;Alphabetic  

`sort -f -s alpha.txt`        &rarr;Capitals first

`sort -f -r alpha.txt`        &rarr;Reverse

`sort -f -s -u alpha.txt`     &rarr;Unique

#### AWK


`awk '{print}' decimal.txt`

`awk '/25/ {print}' decimal.txt`

`awk '/^[0-9]/ {print}' decimal.txt`

`awk '/[0-9]$/ {print}' decimal.txt`

`awk  '{if ($1 ~/20/) print}' decimal.txt`

`awk '{if ($3 ~/[1-9]0/) print}' decimal.txt`

`awk  '{if ($2 == "data_end") print $1}' decimal.txt`

#### SED

`cat data.txt`


`cat data.txt | sed 's/t/T/'`	 	          &rarr;Substitute

`cat data.txt`

`sed -i 's/t/T/g' data.txt`   			      &rarr;Change original file

`cat data.txt`

`sed -n '2p' data.txt`          		      &rarr;print second line

`sed -n '2,4p' data.txt`      			      &rarr;print 2-4 lines

`sed -n '/th/w data_new.txt' data.txt`   	&rarr;Match is written

`cat data_new.txt`



# R basics (Hands-on)

Creating vectors
```R
v <- 123
s <- "a string"
t <- TRUE
letters
length(letters)
```

Functions for creating vectors
```R
seq(1, 3)
1:3
rep(1:2, 3)
vector(mode="character", length=5)
```

Vectorized Arithmetic
```R
1:3 + 10:12
1 + 1:5
paste(1:5, "A", sep="")
```

Matrices and n dimensional arrays
```R
x <- matrix(1:10, nrow=2)
dim(x)
x
as.vector(x)
```

List and function
```R
lst = list(a=1:3, b = "ciao", c = sqrt)
lst
lst[1]
lst[[1]]
lst$c(81)
```

Data Frames
```R
df <- data.frame(type=rep(c("case", "control"), c(2, 3)), time=rexp(5))
df$time
```

Matrices subsetting
```R
x = matrix(1:9, ncol=3)
x[ x > 6 ]
x[ x > 6 ] = 0
x
```

Import files (CSV)
```R
MyData<-read.csv(file="simple.csv", header=TRUE, sep=",")
```

String function
```R
s <- c("apple", "banana", "lychee")
paste(s, "X", sep="_")
paste(s, collapse=", ")
```

Composition of functions
```R
square = function(x) x*x
square(10)
square(1:4)
```

Calling function from other functions - Composition
```R
sumsq = function(x) sum(square(x))
sumsq(1:10)
```
