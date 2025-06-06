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
```
(base) sec@sec-ThinkPad-E15-Gen-4:~$ cat < filename1
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
```
cat < file2
## OUTPUT
```
(base) sec@sec-ThinkPad-E15-Gen-4:~$ cat > filename2
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
```
# Comparing Files
cmp file1 file2
## OUTPUT
```
(base) sec@sec-ThinkPad-E15-Gen-4:~$ cmp filename1 filename2
filename1 filename2 differ: byte 1, line 1
```
comm file1 file2
 ## OUTPUT
 ```
(base) sec@sec-ThinkPad-E15-Gen-4:~$ comm filename1 filename2
	anil aggarwal
	barun sengupta
chanchal singhvi
		c.k. shukla
	lalit chowdury
		s.n. dasgupta
sumit chakrobarty
```
diff file1 file2
## OUTPUT
```
(base) sec@sec-ThinkPad-E15-Gen-4:~$ diff filename1 filename2
1c1,2
< chanchal singhvi
---
> anil aggarwal
> barun sengupta
2a4
> lalit chowdury
4d5
< sumit chakrobarty
```

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
```
(base) sec@sec-ThinkPad-E15-Gen-4:~$ cut -c1-3 file11
Hel
Thi
```
cut -d "|" -f 1 file22
## OUTPUT
```
(base) sec@sec-ThinkPad-E15-Gen-4:~$ cut -d "|" -f 1 file22
1001 
1002 
1003 
```
cut -d "|" -f 2 file22
## OUTPUT
```
(base) sec@sec-ThinkPad-E15-Gen-4:~$ cut -d "|" -f 2 file22
 Ram 
 tom 
 Joe 
```

cat < newfile 
```
Hello world
hello world
^d
````
cat > newfile 
Hello world
hello world
 
grep Hello newfile 
## OUTPUT
![Screenshot from 2025-02-26 11-39-10](https://github.com/user-attachments/assets/9d6ad080-8433-41d3-92a8-e01319119b4b)

grep hello newfile 
## OUTPUT
![Screenshot from 2025-02-26 11-40-01](https://github.com/user-attachments/assets/bcaccd89-116f-49e2-bfb6-41ab006e705f)

grep -v hello newfile 
## OUTPUT
![Screenshot from 2025-02-26 11-40-22](https://github.com/user-attachments/assets/8928aaba-008a-4006-90b4-71b3c5c88f11)

cat newfile | grep -i "hello"
## OUTPUT
![Screenshot from 2025-02-26 11-40-50](https://github.com/user-attachments/assets/d468422a-5022-4a02-b0d5-fcba29a82fc1)

cat newfile | grep -i -c "hello"
## OUTPUT
![Screenshot from 2025-02-26 11-41-11](https://github.com/user-attachments/assets/7201c4ff-7faa-4a74-8b77-193454936de9)

grep -R ubuntu /etc
## OUTPUT
![Screenshot from 2025-02-26 11-41-42](https://github.com/user-attachments/assets/efc58f00-7934-4fcd-8bd3-34d9971bedca)

grep -w -n world newfile   
## OUTPUT
![Screenshot from 2025-02-26 11-42-28](https://github.com/user-attachments/assets/cd306b86-025d-4e9c-9567-aded2fef44cc)

cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

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
![Screenshot from 2025-03-03 11-43-54](https://github.com/user-attachments/assets/83f87376-697d-48aa-8450-cfe91566f051)

egrep -w '(H|h)ello' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-44-16](https://github.com/user-attachments/assets/44c91b57-be10-4dab-b438-df7a1df92831)

egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-44-16](https://github.com/user-attachments/assets/a77c24a0-d2e3-41ca-8090-c6a59913153b)

egrep '(^hello)' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-44-27](https://github.com/user-attachments/assets/9e8a6b33-1b57-429f-9f0f-b0e157b01728)

egrep '(world$)' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-45-07](https://github.com/user-attachments/assets/d23a35c5-deab-4f2e-8d14-b4bd21e54408)

egrep '(World$)' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-45-19](https://github.com/user-attachments/assets/fd33f786-d769-400f-a576-18ca1d8e0db1)

egrep '((W|w)orld$)' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-45-35](https://github.com/user-attachments/assets/29405ff6-4bff-438f-9a1f-3363d5436e7f)

egrep '[1-9]' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-45-44](https://github.com/user-attachments/assets/f368ae44-99ed-4ebc-8de5-265202d55645)

egrep 'Linux.*world' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-46-04](https://github.com/user-attachments/assets/2074e7af-b1f1-46c7-bc46-18f331f11fd3)

egrep 'Linux.*World' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-46-09](https://github.com/user-attachments/assets/7096c0f7-0d17-4b6b-b412-6ef208f4a56b)

egrep l{2} newfile
## OUTPUT
![Screenshot from 2025-03-03 11-46-43](https://github.com/user-attachments/assets/507f1d65-25f4-4a6b-9a57-f02e93c56d68)

egrep 's{1,2}' newfile
## OUTPUT 
![Screenshot from 2025-03-03 11-46-52](https://github.com/user-attachments/assets/2fa1b95d-6132-4ac1-a208-de5f67bf79f3)

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
![Screenshot from 2025-04-23 10-48-40](https://github.com/user-attachments/assets/1303ed97-2b28-4105-8e03-c7679405fbc9)

sed -n -e '3p' file23
## OUTPUT
![Screenshot from 2025-04-23 10-50-32](https://github.com/user-attachments/assets/e1e98928-4f93-4b09-9863-f253a1f7d62f)

sed -n -e '$p' file23
## OUTPUT
![Screenshot from 2025-04-23 10-51-17](https://github.com/user-attachments/assets/71bd2930-524e-4df9-b8c4-7297a8ecf6d9)

sed  -e 's/Ram/Sita/' file23
## OUTPUT
![Screenshot from 2025-04-23 10-52-06](https://github.com/user-attachments/assets/fa4be412-7000-47d0-b91e-3ec9659a8be3)

sed  -e '2s/Ram/Sita/' file23
## OUTPUT
![Screenshot from 2025-04-23 10-52-36](https://github.com/user-attachments/assets/12b61512-eae0-4878-a49d-9e404b51f2eb)

sed  '/tom/s/5000/6000/' file23
## OUTPUT
![Screenshot from 2025-04-23 10-53-07](https://github.com/user-attachments/assets/4d307bff-cd1e-47c2-b8f6-c12d58cbcf93)

sed -n -e '1,5p' file23
## OUTPUT
![Screenshot from 2025-04-23 10-53-44](https://github.com/user-attachments/assets/288ad2c2-1c97-4fbf-9559-265a9e378c84)

sed -n -e '2,/Joe/p' file23
## OUTPUT
![Screenshot from 2025-04-23 10-54-28](https://github.com/user-attachments/assets/a993a683-2e50-4b70-a4e9-22a715f59c49)

sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
![Screenshot from 2025-04-23 10-55-10](https://github.com/user-attachments/assets/7f4105ba-3f03-4e3f-847a-780d61205a3d)

seq 10 
## OUTPUT
![Screenshot from 2025-04-23 10-55-55](https://github.com/user-attachments/assets/d55e42a2-b1e4-47b6-9b4f-d4b6ca5e6ee6)

seq 10 | sed -n '4,6p'
## OUTPUT
![Screenshot from 2025-04-23 10-59-57](https://github.com/user-attachments/assets/ea7911e1-e8cc-48b7-9b81-f0f85f7a65a6)

seq 10 | sed -n '2,~4p'
## OUTPUT
![Screenshot from 2025-04-23 11-00-23](https://github.com/user-attachments/assets/e0b9f2f3-fc76-4cfb-90f3-b7ec391aa887)

seq 3 | sed '2a hello'
## OUTPUT
![Screenshot from 2025-04-23 11-02-16](https://github.com/user-attachments/assets/0210fe2e-bea9-47c4-a87b-13799fcc8413)

seq 2 | sed '2i hello'
## OUTPUT
![Screenshot from 2025-04-23 11-03-22](https://github.com/user-attachments/assets/9e0e6a69-b8ad-49b0-847a-0e0e05f84683)

seq 10 | sed '2,9c hello'
## OUTPUT
![Screenshot from 2025-04-23 11-04-07](https://github.com/user-attachments/assets/af8525c5-fe96-4a18-ae65-ff057f0f0dd6)

sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
![Screenshot from 2025-04-23 11-04-40](https://github.com/user-attachments/assets/53908db2-3653-434d-a60f-8435824cc93a)

sed -n '2,4{s/$/*/;p}' file23
#![Screenshot from 2025-04-23 11-05-09](https://github.com/user-attachments/assets/5d428039-eab8-421e-b3af-ab12a67a948d)

Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
```
![Screenshot from 2025-04-23 11-06-31](https://github.com/user-attachments/assets/59cd3fc1-4864-4b93-b333-c3b9a0cb0760)

sort file21
## OUTPUT
![Screenshot from 2025-04-23 11-07-24](https://github.com/user-attachments/assets/b2e1741b-dc46-49e2-8dbd-54b9d6632733)

cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
```
![Screenshot from 2025-04-23 11-08-40](https://github.com/user-attachments/assets/c16e0fd0-fab4-4244-9fff-906a69163dec)

uniq file22
## OUTPUT
![Screenshot from 2025-04-23 11-09-07](https://github.com/user-attachments/assets/cf322ff7-96c2-46f5-90fb-8d1d8351dfd2)

#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
![Screenshot from 2025-04-23 11-09-50](https://github.com/user-attachments/assets/8f1a6511-088a-4232-937e-fa0d51e7be61)

cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
![Screenshot from 2025-04-23 11-10-31](https://github.com/user-attachments/assets/3ea4aa75-adb2-4696-a4b0-57d726a973f9)

cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
![Screenshot from 2025-04-23 11-11-06](https://github.com/user-attachments/assets/36d888bf-3027-4a3f-ade5-9e390cc9cf55)

cat urllist.txt | tr -d ' '
 ## OUTPUT
![Screenshot from 2025-04-23 11-11-43](https://github.com/user-attachments/assets/2fd72381-594c-4ace-851c-f9549a640732)

cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
![Screenshot from 2025-04-23 11-12-14](https://github.com/user-attachments/assets/23cfa340-92e8-469b-9e75-de3e5ffbbd26)

#Backup commands
tar -cvf backup.tar *
## OUTPUT
![Screenshot from 2025-04-23 11-13-09](https://github.com/user-attachments/assets/7b56b382-46df-4cfd-9a74-16743f252c63)

mkdir backupdir
 ![Screenshot from 2025-04-23 11-13-37](https://github.com/user-attachments/assets/01b53474-0bb8-4eea-b703-58af855a1c81)

mv backup.tar backupdir
 ![Screenshot from 2025-04-23 11-13-58](https://github.com/user-attachments/assets/f07f397a-1a9a-452f-8398-eb6ca459513e)

tar -tvf backup.tar
## OUTPUT
![Screenshot from 2025-04-23 11-14-29](https://github.com/user-attachments/assets/8b33c602-f8f8-4dea-af41-8e2ed26266a2)

tar -xvf backup.tar
## OUTPUT
![Screenshot from 2025-04-23 11-14-50](https://github.com/user-attachments/assets/8f49b580-ac3f-4baa-801d-b9576208366a)

gzip backup.tar

ls .gz
## OUTPUT
 ![Screenshot from 2025-04-23 11-15-16](https://github.com/user-attachments/assets/16caa951-6f3e-4e05-92ff-d56a2660200d)
![Screenshot from 2025-04-23 11-15-38](https://github.com/user-attachments/assets/0f367174-8ad8-4401-af95-10ee4f925969)

gunzip backup.tar.gz
## OUTPUT
![Screenshot from 2025-04-23 11-16-09](https://github.com/user-attachments/assets/000cd8e5-1b05-44ae-8a8f-5ebdfded2cc3)

# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh ./my-script.sh

## OUTPUT
![Screenshot from 2025-04-23 11-50-20](https://github.com/user-attachments/assets/3869a708-0289-49a8-ba73-38b4c7e50f66)

cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT
![Screenshot from 2025-04-23 11-51-15](https://github.com/user-attachments/assets/bff79ed2-2c02-4f42-a74d-477cee8b5971)

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
^d
 ```

cat scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT
![Screenshot from 2025-04-23 11-52-04](https://github.com/user-attachments/assets/13eabde0-8a23-46a8-85b5-2dccc5ca7911)
 ![Screenshot from 2025-04-23 11-52-34](https://github.com/user-attachments/assets/518704f6-61f1-46d5-a7cf-3e9242236047)

ls file1
## OUTPUT
![Screenshot from 2025-04-23 11-53-16](https://github.com/user-attachments/assets/323193c6-ff71-4db3-a0c3-00ee142c3a00)

echo $?
## OUTPUT 
./one
bash: ./one: Permission denied
 ![Screenshot from 2025-04-23 11-53-51](https://github.com/user-attachments/assets/b092f581-0c36-4489-9ae3-fdde611e8c72)

echo $?
## OUTPUT 
 ![Screenshot from 2025-04-23 11-54-28](https://github.com/user-attachments/assets/4aba292f-40c8-4a5c-828e-40cf9235c4a9)

abcd
 
echo $?
 ## OUTPUT

# mis-using string comparisons
![Screenshot from 2025-04-23 11-54-28](https://github.com/user-attachments/assets/67384ab0-cf71-40a0-8e73-2f10e7c03a72)

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
##OUTPUT



chmod 755 strcomp.sh
 
./strcomp.sh 
## OUTPUT
![Screenshot from 2025-04-23 11-55-20](https://github.com/user-attachments/assets/4d4ccbe7-57ba-4085-a7af-c51fdca04da7)


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
![Screenshot from 2025-04-23 11-55-48](https://github.com/user-attachments/assets/e67defcc-8925-4cc3-b925-6f1df9d51329)

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
![Screenshot from 2025-04-23 11-56-23](https://github.com/user-attachments/assets/7149c1c0-8f27-4753-a951-c66cc22db1f4)

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
##OUTPUT
![Screenshot from 2025-04-23 11-56-56](https://github.com/user-attachments/assets/1b04e08c-4825-4b6e-922b-b6fd064906be)

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
##OUTPUT
![Screenshot from 2025-04-23 11-58-16](https://github.com/user-attachments/assets/7a869760-4997-4dbe-a46f-3da44072c5fe)

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
![Screenshot from 2025-04-23 11-58-54](https://github.com/user-attachments/assets/f2be81a5-8438-4a94-a880-f5b27a27ac7e)

# using the case command
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
 
cat > whiletest
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
 
 
cat untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh
 
 
 
cat forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh
 
 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh
 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
$ chmod 755 forin2.sh
 
$ ./forin2.sh 
 
cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ ./forin3.sh 
 
 cat forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh

## OUTPUT
cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
$ chmod 777 forinfile.sh
$ cat cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam

## OUTPUT


cat forctype.sh 
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

cat forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype.sh
$ ./forctype1.sh 
## OUTPUT

cat fornested1.sh 
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
![Screenshot from 2025-04-23 12-00-24](https://github.com/user-attachments/assets/45fec1da-4b22-412a-aac2-e25a193267d3)

 
cat forbreak.sh 
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
echo "The for loop is completed“
```
## OUTPUT

$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
 
cat forbreak.sh 
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
echo "The for loop is completed“
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 
## OUTPUT
 
cat exread.sh 
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


 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 

## OUTPUT
![image](https://github.com/user-attachments/assets/6bc9889d-e30f-47d9-b164-091e31b01e97)

$ ./exread1.sh 
 
cat funcex.sh
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
## OUTPUT
 ./funcex.sh 

 
 ./funcex.sh 1 2

 
cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh

## OUTPUT
$ ./argshift.sh 1 2 3
 
 catargshift1.sh
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
$ chmod 777 argshift.sh
## OUTPUT
$ ./argshift.sh 1 2 3
 
cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
## OUTPUT
 ./argshift.sh 1 2 3
 
 
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
![image](https://github.com/user-attachments/assets/47974179-5475-4479-bf2f-446880a3066d)


# RESULT:
The Commands are executed successfully.
