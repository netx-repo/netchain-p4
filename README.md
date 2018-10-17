# net-chain
0. Introduction<br>
-- BMV2-based simple implementation of NetChain (related paper can be found here: https://www.usenix.org/conference/nsdi18/presentation/jin).

1. Content<br>
--client<br>
----client/nc_socket.py<br>
----client/receiver.py<br>
----set_arp.sh<br>
--controller<br>
----controller/config<br>
------controller/config/topo.txt<br>
------controller/config/vring.txt<br>
------controller/config/config.xml<br>
------controller/config/commands[_1,_2,_3]*.txt<br>
----controller/nc_config.py<br>
----controller/p4_mininet.py<br>
----controller/run_test.py<br>
----controller/exe_cmd.py<br>
----controller/fail_recovery.py<br>
----controller/plot.py<br>
--p4src<br>
----p4src/includes<br>
------p4src/includes/checksum.p4<br>
------p4src/includes/defines.p4<br>
------p4src/includes/headers.p4<br>
------p4src/includes/parsers.p4<br>
----p4src/netchain.p4<br>
----p4src/routing.p4<br>
--logs<br>
--.gitignore<br>
--README.md<br>

2. How to run<br>
-- Install required software and dependency for P4 (P4-14).<br>
-- Make sure the directory informations are correct in controller/config/config.xml, then simply run: sudo python controller/run_test.py failure.<br>
-- The program produces results at logs/ the format is [number of virtual groups].tmp_[read/write]_[send/receive].log
-- You can draw figures by running: python plot.py [number of virtual groups]