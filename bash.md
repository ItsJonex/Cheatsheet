## INDEX ##
1. [Command Line Arguments](https://github.com/aagontuk/cheatsheets/blob/master/bash.md#command-line-arguments)
2. [Conditional Statement](https://github.com/aagontuk/cheatsheets/blob/master/bash.md#conditional-statement)
3. [`case` Statement](https://github.com/aagontuk/cheatsheets/blob/master/bash.md#case-statement)
4. [Looping](https://github.com/aagontuk/cheatsheets/blob/master/bash.md#looping)
    1. [For Loop](https://github.com/aagontuk/cheatsheets/blob/master/bash.md#for-loop)
    2. [While Loop](https://github.com/aagontuk/cheatsheets/blob/master/bash.md#while-loop)
    3. [Until](https://github.com/aagontuk/cheatsheets/blob/master/bash.md#until)
    4. [break and continue statements](https://github.com/aagontuk/cheatsheets/blob/master/bash.md#break-and-continue)
5. [Array](https://github.com/aagontuk/cheatsheets/blob/master/bash.md#array)
5. [Exit Staus](https://github.com/aagontuk/cheatsheets/blob/master/bash.md#exit-status)

## Command Line Arguments ##
sample code:
```sh
#!/bin/bash

echo "Number of arguments: '$#'"
echo "All arguments(space seperated): '$@'"
echo "Program name: '$0'"
echo "Argument 1: '$1'"
echo "Argument 2: '$2'"
```
sample output:
```
Number of arguments: '2'
All arguments(space seperated): 'hello world'
Program name: './cmd.sh'
Argument 1: 'hello'
Argument 2: 'world'
```
sample code:
```sh
echo "Number of arguments given: $#"

number=1
while [ "$1" != "" ]; do
    echo "Argument $number: $1"
    number=$((number + 1))      # number+=1
    shift
done
```
sample output:
```
Number of arguments given: '2'
Argument 1: hello
Argument 2: world
```

## Conditional Statement ##
```sh
# if-else structure
# if [ Expression ]; then
#       do something
# elif [ Expression ]; then
#       do something else
# else
#       do something else
# fi

number=2

if [ $number -lt "2" ]; then
    echo "Less than 2"
elif [ $number -gt "2" ]; then
    echo "Greater than 2"
else
    echo "Equal to 2"
fi
```

## `case` Statement ##
```sh
# if-else structure
# if [ Expression ]; then
#       do something
# elif [ Expression ]; then
#       do something else
# else
#       do something else
# fi

number=2

if [ $number -lt "2" ]; then
                echo "Less than 2"
elif [ $number -gt "2" ]; then
                echo "Greater than 2"
else
                echo "Equal to 2"
fi
```

## Looping ##

### For Loop ###
```sh
# Structure of the for loop
# for $variable in sequence; do
#	something with the variables
# done

for f in $(ls); do
		echo $f
done
```

### While Loop ###
```sh
# Structure of while loop
# while [ Expression ]; do
#	do something
# done

number=0

while [ $number -lt 10 ]; do
		echo "Number: $number"
		number=$((number + 1))
done
```

### Until ###
```sh
number=0

until [ $number -gt 10 ]; do
		echo "Number $number"
		number=$((number + 1))
done
```

### break and continue ###
Like any other programming languages `break` and `continue`
statement can be applied in a loop

## Array ##

Arrays are defined as `array_name=(0 "name" 4)`
where `array_name` is the name of the array
an `0`, `name` are the elements of the array.
Array can be subscripted and iterated in following
way:

```sh
array_name=(0, "name", 4)

# Print first element of the array
echo ${array_name[1]}

# Iterating through the array
# Print all the elements of the array
for elem in ${array_name[@]}; do
    echo $elem
done
```

## Exit Status ##
```sh
touch
echo $?
```
