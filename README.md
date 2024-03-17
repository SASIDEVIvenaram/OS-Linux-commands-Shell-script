# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
^d
```
cat > file2
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
^d
```
### Display the content of the files
cat < file1
## OUTPUT
![alt text](image.png)


cat < file2
## OUTPUT
![alt text](image-1.png)

# Comparing Files
cmp file1 file2
## OUTPUT
![alt text](image-2.png)
comm file1 file2
 ## OUTPUT
![alt text](image-3.png)
 
diff file1 file2
## OUTPUT
![alt text](image-4.png)
#Filters
### Create the following files file11, file22 as follows:
cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```


cut -c1-3 file11
## OUTPUT
![alt text](image-5.png)



cut -d "|" -f 1 file22
## OUTPUT
![alt text](image-7.png)


cut -d "|" -f 2 file22
## OUTPUT
![alt text](image-6.png)

cat > newfile 
```
Hello world
hello world
^d
````
grep Hello newfile 
## OUTPUT
![alt text](image-8.png)

grep hello newfile 
## OUTPUT
![alt text](image-9.png)

grep -v hello newfile 

## OUTPUT
![alt text](image-10.png)


cat newfile | grep -i "hello"

## OUTPUT
![alt text](image-11.png)



cat newfile | grep -i -c "hello"

## OUTPUT
![alt text](image-12.png)

grep -R ubuntu /etc

## OUTPUT

grep -w -n world newfile   

## OUTPUT
![alt text](image-13.png)

cat > newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
egrep -w 'Hello|hello' newfile 
## OUTPUT
![alt text](image-14.png)


egrep -w '(H|h)ello' newfile 
## OUTPUT
![alt text](image-15.png)


egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT
![alt text](image-16.png)



egrep '(^hello)' newfile 
## OUTPUT
![alt text](image-17.png)


egrep '(world$)' newfile 
## OUTPUT
![alt text](image-18.png)


egrep '(World$)' newfile 
## OUTPUT
![alt text](image-19.png)

egrep '((W|w)orld$)' newfile 
## OUTPUT
![alt text](image-20.png)


egrep '[1-9]' newfile 
## OUTPUT
![alt text](image-21.png)

egrep 'Linux.*world' newfile 
## OUTPUT
![alt text](image-22.png)

egrep 'Linux.*World' newfile 
## OUTPUT
![alt text](image-23.png)

egrep l{2} newfile
## OUTPUT
![alt text](image-24.png)


egrep 's{1,2}' newfile
## OUTPUT 
![alt text](image-25.png)

cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```


sed -n -e '3p' file23
## OUTPUT
![alt text](image-26.png)


sed -n -e '$p' file23
## OUTPUT
![alt text](image-27.png)


sed  -e 's/Ram/Sita/' file23
## OUTPUT
![alt text](image-28.png)

sed  -e '2s/Ram/Sita/' file23
## OUTPUT
![alt text](image-29.png)


sed  '/tom/s/5000/6000/' file23
## OUTPUT
![alt text](image-30.png)


sed -n -e '1,5p' file23
## OUTPUT
![alt text](image-31.png)


sed -n -e '2,/Joe/p' file23
## OUTPUT
![alt text](image-32.png)



sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
![alt text](image-33.png)


seq 10 
## OUTPUT
![alt text](image-34.png)


seq 10 | sed -n '4,6p'
## OUTPUT
![alt text](image-35.png)


seq 10 | sed -n '2,~4p'
## OUTPUT
![alt text](image-36.png)


seq 3 | sed '2a hello'
## OUTPUT
![alt text](image-37.png)


seq 2 | sed '2i hello'
## OUTPUT
![alt text](image-38.png)

seq 10 | sed '2,9c hello'
## OUTPUT
![alt text](image-39.png)

sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
![alt text](image-40.png)


sed -n '2,4{s/$/*/;p}' file23
## OUTPUT
![alt text](image-41.png)

# Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
## OUTPUT
![alt text](image-42.png)

cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
uniq file22
## OUTPUT
![alt text](image-43.png)


#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
![alt text](image-44.png)
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```

cat urllist.txt | tr -d ' '
 ## OUTPUT
![alt text](image-45.png)

 
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
![alt text](image-46.png)

# Backup commands
tar -cvf backup.tar ex01
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/d1085875-c427-4fd1-a484-a7d04db54c35)


mkdir backupdir
 
mv backup.tar backupdir
 
tar -tvf backup.tar
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/81f1ae6a-971b-480f-9a91-9a98844c6d7e)


tar -xvf backup.tar
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/45bda56a-e6a0-45f1-9abe-d857b1a4cf88)

gzip backup.tar

ls .gz
## OUTPUT
 
gunzip backup.tar.gz
## OUTPUT

 
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/348b7239-c9e5-4259-a2e3-80333cca7cb4)
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/bb7c3805-d960-4920-8f82-1d61ad7020f0)


cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/50e5ea98-8832-4cb8-91f1-3a1a7e9d4abe)

cat < scriptest.sh 

```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
 ```
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/c04772d5-249d-48d6-8fe3-d649cd4f3ddf)

 
ls file1
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/8d5dc2e3-d6fb-4808-abc4-a8cd1857ad9e)

echo $?
## OUTPUT 
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/f67ae7c5-16fd-4fb6-9622-ea036b3f6a92)

./one
bash: ./one: Permission denied

echo $?
## OUTPUT 
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/e5dd5dd9-69c7-4807-8ceb-5ac6c7e7d0a3)

echo abcd
echo $?
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/7977fb0a-df67-4368-bd7b-00ca839d19e6)

# mis-using string comparisons

cat < strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/3b9d18c5-2a72-4266-aebd-6657258470fc)

chmod 755 strcomp.sh
./strcomp.sh 

## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/894b79df-c738-462a-ad2c-c151a06f6974)

# check file ownership
cat < psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```
./psswdperm.sh
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/690db9b2-2a13-4f55-9618-63d70d89953b)

# check if with file location
cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 
```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```
./ifnested.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/35189e95-0861-4c28-91b0-a26889e135fc)

# using numeric test comparisons
cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```

cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```

$ chmod 755 iftest.sh
 
$ ./iftest.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/ee7466e0-74a5-40a2-aa4e-3bd619c9e86f)

# check if a file
cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```

cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

$ chmod 755 ifnested.sh
 
$ ./ifnested.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/1448257c-5e29-47fd-a65d-640dae7671fa)

# looking for a possible value using elif
cat elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/421253d5-6574-485c-adcb-1142ebd82689)

# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/5e88fdd6-2b73-465f-9a2a-04b0e0845cb7)

# using the case command/
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
$ chmod 755 casecheck.sh 
 
$ ./casecheck.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/8ef82243-4b34-447c-b6d1-abb33adac470)

cat > whiletest.sh
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
$ chmod 755 whiletest.sh
 
$ ./whiletest.sh
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/76e69964-338e-4109-9448-977242d3c0eb)

cat > untiltest.sh 
```bash
#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh
$ ./untiltest.sh

## OUTPUT:
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/533b700f-2114-4b23-935b-713e4e172ddb)

cat > forin1.sh 
```bash
#!/bin/bash
#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh
$ ./forin1.sh

## OUTPUT:
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/04c88577-87cf-4f4f-bae9-90f092077156)


cat > forin2.sh 
```bash
#!/bin/bash
# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh
$ ./forin2.sh
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/40550f25-5f51-4b68-8d09-7d865fc91704)

cat > forin3.sh 
```bash
#!/bin/bash
# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ chmod 755 forin3.sh
$ ./forin3.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/f688fffc-8620-42e0-b0e7-38d4ce2c0543)

cat > forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh
$ forin1.sh
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/53babe95-0f13-42d9-9e31-dc81b12f2dc2)

cat > forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file"
done
```
$ chmod 777 forinfile.sh
$ cat > cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam
$ ./forinfile.sh
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/0cf084c0-0dec-4172-a70b-c1f1721673df)

cat > forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````
$ chmod 755 forctype.sh
$ ./forctype.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/4b43b32e-f435-4944-825d-25e0c7abb299)

cat > forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype1.sh
$ ./forctype1.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/c68a9a8b-f4a1-4886-a7c0-2204976fe237)

cat > fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```
$ chmod 755 fornested1.sh
 
$ ./fornested1.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/4e3423f6-6836-4a0b-88f5-11e6faec879a)

 
cat > forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed"
```


$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/015dd29a-489f-4578-a55b-a1ffdcb2c4e2)

cat > forcontinue.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed"
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/37a3a88c-7f42-4f8b-8c01-cce95793b903)

cat > exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
$ chmod 755 exread.sh 
 
$ ./exread.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/7fd00c0b-38ed-424f-93ca-cc3e921301e4)


cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. "
``` 
$ chmod 755 exread1.sh 
$ ./exread1.sh 
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/6cf35f1f-00bc-4e40-9c2b-adff53df6671)

cat > funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
$ chmod 755 funcex.sh
$ ./funcex.sh  
$ ./funcex.sh 1 2
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/742b48c6-ef27-4fd5-94ac-0334be11fc53)

cat > argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh
$ ./argshift.sh 1 2 3
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/fbe6daee-0164-41ac-b42a-8bb286404932)

cat > argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
$ chmod 777 argshift1.sh
$ ./argshift1.sh 1 2 3
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/9cf392b6-1721-451b-af6f-09ef56121cdf)

cat >argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```

$ ./argshift.sh 1 2 3
## OUTPUT
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/b5c81291-b620-49b2-8b74-34cc3d0e36cf)

 
cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```
awk -f nc.awk data.dat
## OUTPUT 
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/54c6f28c-a541-46d7-abc6-9a5c1908f992)

cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
## OUTPUT 
![image](https://github.com/SASIDEVIvenaram/OS-Linux-commands-Shell-script/assets/118707332/fe0ed355-9a87-4833-b3ba-73798b2cadee)


# RESULT:
The Commands are executed successfully.
