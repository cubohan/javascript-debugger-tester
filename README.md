# javascript-debugger-tester
Debug/Test javascript code with one line debug() statements with infinite possible combinations of arguments and functions (object) passed in the following pattern:

"^debug([[<?arg1>.+,[ ]*]*[["[-]{2}"<?number_of_arguments_for_funct1>[0-9]+]{0,1},[ ]*<?funct>\b\w{1,}\b[ ]*]+]+);{0,1}$"

i.e

debug ( arg11, arg12..., (optional arg for funct 1 indicating no. of arguments it requires, default is 1)--(NATURAL NO.), funct11, (funct12 follows funct 11 if output of funct11 has to be passed as argument for funct12, and so on till (n) functions; funct12..funct1n are optional, each optionally followed by an argument indicating no. of arguments they expect)funct12..., arg21, arg22..., func21... );

eg:

debug("~print this line~1~", "~print this line~2~", "~print this line~3~", console.log, 17, 16, 15, "--3", add, "--1", funct_divide_by_3, console.log)

OUTPUT:

~print this line~1~

~print this line~2~

~print this line~3~

16

debug(funct1, funct2, funct3, funct4);

Execute funct1; Execute funct2 while passing return value of funct1 as arguments; Execute funct3 while passing return value of funct2 as arguments; Execute funct4 while passing return value of funct3 as arguments;

debug(funct1, "--0", funct2, "--0" funct3, "--0", funct4)

Execute funct1 with no arguments; Execute funct2 with no arguments; Execute funct3 with no arguments; Execute funct4 with no arguments;
