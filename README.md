# USRP-X410

### look for the device, first turn on the share internet with WSL2.

for example, my internet is 192.168.137.1/24
use:

`2..254 | % { ping -n 1 -w 60 "192.168.137.$_" | Out-Null }
arp -a -N 192.168.137.1`

and find the ip addr of the USRP then use

`uhd_find_devices --args addr=192.168.137.X
`

init it with 

`
uhd_usrp_probe --args addr=192.168.137.2`

### Gnu Radio 

use conda to handle this because UHD 4.6 is old, use:

`conda create -n gr -c conda-forge gnuradio "uhd=4.8.*"
conda activate gr`

and

`gnuradio-companion`



