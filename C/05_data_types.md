# Data Types
- tells how much storage/ memory is to be allocated to a variable

## Primary
- int 
	 - memory size 
	   ```c 
	   printf("%lu",sizeof(int)); // 4 bytes in most of the computers
	   ```
	 - short int -> `1 byte`
	 - long int -> `4 bytes`
	 - int for 16 bit -> 
		 -  signed -> `- 32768 to 32747`  (default)
		 -   unsigned -> `0 to 65535`
	 - int for 32 bit
		 - ``- 2147483648 to 2147483647` 
- float
	- memory size -> `4 bytes`
	- range -> `- 3.4 e38 to 3.4 e38`
	- double -> `8 bytes`  `%lf`
	- long double -> `10 bytes` `%LF`
- char
	- memory size -> `1 byte or 8 bit`
	- signed -> `- 128 to 127`
	- unsigned -> `0 to 255`
- double
- void

## Derived
- array
- structure
- union
- pointers

## User-Defined
- type def
- enumerated

