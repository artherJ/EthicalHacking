*the ISOs are too large to put in the folder hence I have omitted them.*

for CDP table flooding attack:
1.download gns3 and solarwind powershell
2.download VMware workstation and its GNS3 VM
3.download backtracker 5 ios image for Linux/Ubuntu
4.import GNS3 VM onto VMware workstation
5.open GNS3 and open the respective project folder "GNS3 network sim\WAN network simulation"
6.open backtracker 5 in VMware workstation
	"username:root
	 pass:toor"
	then "startx"
	this should promt you logged in, proceed to install Yersinia on backtracker
7.restart backtracker
8.make sure all devices are on in GNS3 topologies
9.use Yersinia to perform said attacks.

for APR spoofing attack:
1.download gns3 and solarwind powershell
2.download VMware workstation and its GNS3 VM
3.download Kali Linux installer image and import it into Vmware workstation, tick "host-only" in network section, as it won't connect to switch otherwise
4.import GNS3 VM & Kali Linux onto VMware workstation
5.open GNS3 and open the respective project folder "GNS3 network sim\APR spoofing"
6.start all nodes
7.open console for R1, it requires further adjustments
	"conf t
	 int f0/0
	 ip addr 192.168.50.1 255.255.255.0
	 no shut"
8.it should start kali for you too, type in username and pass:
	"username: kali
	 pass: kali"
9.configure kali linux to be neighbour of the network,
	"ipv4/custom: 192.168.50.50 255.255.255.0 192.168.50.1"
9.use console to start ettercap perform attacks.




note:
allow extra time for GNS3 VM to spin up before opening project

all devices should have static configurations(ip addresses: "R2:10.1.1.1", "S1:10.1.1.2", "R1:192.168.50.1", "VPC1:192.168.50.10", "VPC1:192.168.50.11")

errors are included within report, additiona errors may include network bridge failure, in that case, make sure cloud node is on GNS3 VM(VMware workstation).

youtube link for CDP table flooding attack: https://youtu.be/4LhBXEUd5_8
youtube link for ARP spoofing attack: https://youtu.be/u4C_BtSCaxU
