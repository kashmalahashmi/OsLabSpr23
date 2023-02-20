task 01:

![t1](https://user-images.githubusercontent.com/123877043/220101920-89bfcd04-2968-4281-b9db-0e0b0f47264d.png)

#!/bin/bash
if [ "$#" -ne 3 ]; then
  echo "Error: Exactly three numbers must be provided as arguments"
  exit 1
fi
min=$1
if [ "$2" -lt "$min" ]; then
  min=$2
fi
if [ "$3" -lt "$min" ]; then
  min=$3
fi
echo "The min of $1 $2 and $3 is $min"

task 02:

#!/bin/bash
for i in {1..5}; do
  name="test0$1"
  mkdir $name
  cd $name
  mkdir 01
  cd 01
  touch test.txt
  date > test.txt
  cd ..
  mkdir 02
  cd 02
  touch test.txt
  date > test.txt
  cd ..
  cd ..
  done

![t2](https://user-images.githubusercontent.com/123877043/220108945-1222c80b-0986-4c8e-be13-cf6602abb7cb.png)
 
 task 03:
 [merged.txt](https://github.com/kashmalahashmi/OsLabSpr23/files/10784380/merged.txt)
 
 #!/bin/bash
# Find all the test.txt files and merge their contents into one file
find . -type f -name test.txt -exec cat {} + >> merged.txt

![t3](https://user-images.githubusercontent.com/123877043/220109749-1ffa622d-97f6-4c6f-a983-22166abbeaa4.png)


 task 04;
 
#!/bin/bash
# Find all the text files and write their names to a file
find ./test* -type f -name "*.txt" -print > fileNames.txt

[fileNames.txt](https://github.com/kashmalahashmi/OsLabSpr23/files/10784396/fileNames.txt)


![t4](https://user-images.githubusercontent.com/123877043/220110482-ee8bb7b2-3a56-4a17-9c7a-48f9d0e4cf68.png)

task 05:

#!/bin/bash
# Remove all the text files in the subfolders of the test directories
find ./test* -type f -name "*.txt" -delete


![t5](https://user-images.githubusercontent.com/123877043/220111584-c75ebb80-a773-4ac4-a411-1732848105ff.png)

all txt files has been deleted.

task 06:

#!/bin/bash
if [[ $# -eq 0 ]]; then
  echo "Please provide an integer argument."
  exit 1
fi

n=$1

if ! [[ "$n" =~ ^[0-9]+$ ]]; then
  echo "Argument must be a positive integer."
  exit 1
fi

a=0
b=1
echo "Fibonacci sequence for n=$n:"

if (( n == 0 )); then
  echo "0"
  exit 0
fi

echo -n "$a "

if (( n > 1 )); then
  echo -n "$b "

  for (( i=2; i<$n; i++ ))
  do
    c=$((a+b))
    echo -n "$c "
    a=$b
    b=$c
  done
fi

echo ""
exit 0


![t6](https://user-images.githubusercontent.com/123877043/220112221-33c111ae-e26e-47fb-8c88-82344965f3b2.png)








