# Python-program-for-binary-to-octal-conversion

Binary to Octal Conversion in Python
Here, in this section we will discuss the binary to octal conversion in Python.Binary numbers are also known as bits that represent 0 means FALSE and 1 means TRUE, but usually binary numbers are with base 2 and can represent any number in form of 0 and 1. Whereas Octal numbers expressed with base 8 and can represent any number with 0 to 7.

Binary to octal conversion

Method discussed
We will first convert the Binary number into Decimal and then convert the Decimal number into Octal

Make sure that you have gone through these approaches below –

Binary to Decimal Conversion
Decimal to Octal Conversion
Method 1 Code
Run
# function to convert binary to octal
def convert(num):
    octalDigit = 0
    count = 1
    i = 0
    pos = 0
    octalArray = [0] * 32

    while num != 0:
        digit = num % 10
        octalDigit += digit * pow(2, i)
        i += 1
        num //= 10

        # placing current octal-sum for 3 pair in array index position
        octalArray[pos] = octalDigit

        # whenever we have read next 3 digits
        # setting values to default
        # increasing pos so next values can be placed at next array index
        if count % 3 == 0:
            octalDigit = 0
            i = 0
            pos += 1

        count += 1

    # printing octal array in reverse order
    for j in range(pos, -1, -1):
        print(octalArray[j], end='')


binary = 1010
convert(binary)
Output :
Enter binary number: 1010
Decimal : 10
Octal : 12
Related Pages
Decimal to Binary conversion

Decimal to Octal Conversion

Decimal to Hexadecimal Conversion

Permutations in which n people can occupy r seats in a classroom 

Octal to Binary conversion

Quadrants in which a given coordinate lies

Method 2:-
Method 2 uses the concept of grouping 3 successive digits/bits of the binary number and calculating octal digits against each grouping

We use an additional array to store the octal digits at each index.

We will need to print the array in reverse to get actual octal equivalent.

binary to octal conversion in Python
Method 2 Code
Run
# function to convert binary to octal
def convert(num):
    octalDigit = 0
    count = 1
    i = 0
    pos = 0
    octalArray = [0] * 32

    while num != 0:
        digit = num % 10
        octalDigit += digit * pow(2, i)
        i += 1
        num //= 10

        # placing current octal-sum for 3 pair in array index position
        octalArray[pos] = octalDigit

        # whenever we have read next 3 digits
        # setting values to default
        # increasing pos so next values can be placed at next array index
        if count % 3 == 0:
            octalDigit = 0
            i = 0
            pos += 1

        count += 1

    # printing octal array in reverse order
    for j in range(pos, -1, -1):
        print(octalArray[j], end='')


binary = 10101111
convert(binary)
Output :
Enter binary number: 10101111
257
