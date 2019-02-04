# Math check - 75

```c
#include<stdio.h>
#include<string.h>
void main()
{
	char s[23], string[23];
	printf("Enter the flag\n");
	scanf("%s",s);
	int i=1;
	for(int count=1; count<=23; count++)
	{
		i+=A;
		i%=23;
		string[count-1]=s[i];
	}

	printf("%s",string);
}

//FUM!SM4GBTD_CT{L4}C0R1I

//A is for you to find. The above is the output.
```

As we know the flag format ( BITSCTF{flag_goes_here} ) we can estimate A to be 5. Then i created a Python script which uses a placeholder flag to get the original positions of output chars.

```python
A = 5

output = 'FUM!SM4GBTD_CT{L4}C0R1I'
input_string = 'BITSCTF{abcdefghijklmn}'

i = 1
test_out = ''

for index in range(23):
    i += A
    i %= 23
    test_out += input_string[i]

flag = ''
for j in 'abcdefghijklmn':
    flag += output[test_out.find(j)]

print('BITSCTF{'+flag+'}')
```

Flag: `BITSCTF{M0DUL4R_M4G1C!}`
