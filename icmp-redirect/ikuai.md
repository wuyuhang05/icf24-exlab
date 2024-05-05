## ICMP Redirect Attack on iKuai IK-Q3000 

### Description

Attacker sending false ICMP Route Control messages, causing the victim to select the route specified by the attacker.

### Steps

The internal IP of the router is 192.168.58.1, victim's is 192.168.58.109, attacker's is 192.168.58.110.

(1) Victims check the default route to server 8.8.8.8:

![image-20240505203349451](/Users/rainair/work/hw/网安导/icf24-exlab/assets/image-20240505203349451.png)

(2) Victims ping server, attacker cannot get its flow by Wireshark:

![image-20240505203550192](/Users/rainair/work/hw/网安导/icf24-exlab/assets/image-20240505203550192.png)

![image-20240505203535061](/Users/rainair/work/hw/网安导/icf24-exlab/assets/image-20240505203535061.png)

(3) attacker using scapy to send false ICMP Redirect messages:

![image-20240505203728824](/Users/rainair/work/hw/网安导/icf24-exlab/assets/image-20240505203728824.png)

(4) victim's router changed from 192.168.1.1 to 192.168.58.110:

![image-20240505203811306](/Users/rainair/work/hw/网安导/icf24-exlab/assets/image-20240505203811306.png)

(5) victim ping server, attack can get its flow by Wireshark:

![image-20240505203908528](/Users/rainair/work/hw/网安导/icf24-exlab/assets/image-20240505203908528.png)

![image-20240505203919636](/Users/rainair/work/hw/网安导/icf24-exlab/assets/image-20240505203919636.png)