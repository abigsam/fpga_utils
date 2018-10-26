# fpga_utils

PCK_FIO: printf style output in VHDL
https://vlnv.livejournal.com/5637.html
Example:
library std;
use std.textio.all;

library printf;
use printf.pck_fio.all;

architecture ...
file output : text open write_mode is "assertTst.lst";
...
process ...
variable l : line;
...
fprint(output,l, "Tc=%3d ns A=%b B=%b x=%b\n",fo(NOW), fo(A), fo(B),fo(x)); 

Produces this output:
Tc=  0 ns A=U B=U x=U
Tc=  0 ns A=U B=U x=0
Tc=  0 ns A=0 B=0 x=0
Tc=  1 ns A=0 B=0 x=1
Tc=  1 ns A=0 B=1 x=1
Tc=  1 ns A=1 B=1 x=1
Tc=  2 ns A=1 B=1 x=0
Tc=  2 ns A=0 B=0 x=0

