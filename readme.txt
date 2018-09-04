Forked Pasmo assembler


Extra Options:

--cspecsymbols
	Outputs map file in the format CSPEC emulator can read.

--snasmerrors
	Outputs errors messages in snasms format

Comments:
You can now use // and ; to define line comments

labels:
You can now use @ in the same way as _ is pasmo.	



Commands:


SAVEBIN <filename>,<addr>,<length>
	On last pass file will be written to the hdd fromt he assembled memory, if pc is before the last address data is undefined.
example
	SAVEBIN "build/bank4.bin",$c000,PC-$c000



MESSAGE <messages>,...
	emits a message to console output , car output labels and string and constants. seperate with comma.
example
	MESSAGE "CURRENT PC=",PC



PC
	PC can now be used as definition of the current compile address, as well as $.



HEX <hexbytes>
	you can now define big clocks of data using HEX statment

example
	HEX 0002008C8C8C8C8C8C49B6B6498C0001
	


ALIGN <value>
	Aligns ther PC the a boundry
example
	ALIGN 256 aligns the PC so lo byte of address will be 0.


RSSET <value>
	Sets the RS value to <value> if value is not there value will be 0 , used with RS & RW to define structs.
example
	RSSET 0 
	HWSPRITEDATA_OX: rb 1
	HWSPRITEDATA_OY: rb 1
	HWSPRITEDATA_SX: rw 1


SETBANK <value>
	Sets the CURRENTBANK varible to value. Also all labels defined after this command will store the bank it was defined in.
	then you can do ?? before a label to get the bank of that label.
example
	SETBANK 5

DATA:	HEX 0002008C8C8C8C8C8C49B6B6498C0001

	ld hl,DATA (sets the address of data)
	ld a,?? DATA (sets a to the bank "5", of the label data)


