
#### Description

A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/a917f567b9cc0f1a730a7801b309955df4d2234a8114326857b9759e9e5d0453/myNetworkTraffic.pcap) and try to get the flag.


Inspecting the wireshark network looks cool and got something interesting in the tcp segments 
![[Pasted image 20251124150733.png]]

![[Pasted image 20251124150759.png]]


Doing in GUI wireshark takes time we can see something encoded in base64 , but checking with every other packets in wireshark is hectic so let us try with tshark 

tshark - command line based tool , great for filtering in this case 

![[Pasted image 20251124151012.png]]

tshark -r myNetworkTraffic.pcap -Y "tcp" -T fields -e tcp.segment_data | xxd -p -r | base64 -d 

Filtering the file with these fields 

![[Pasted image 20251124151137.png]]

but extra content has been printed which is not useful to the final flag so let us filter more Specifying length of packets 

tshark -r myNetworkTraffic.pcap -Y "tcp.len== 12" -T fields -e tcp.segment_data | xxd -p -r | base64 -d

![[Pasted image 20251124151419.png]]

But not in order right so let us filter now adding a timestamp field and sort the output and 

tshark -r myNetworkTraffic.pcap -Y "tcp.len== 12 || tcp.len== 4 " -T fields -e frame.time  -e tcp.segment_data | sort k4 | awk '{print $6}' |  xxd -p -r | base64 -d


![[Pasted image 20251124151708.png]]


- `tshark`: Network protocol analyzer (similar to Wireshark, but command-line based).
- `-r myNetworkTraffic.pcap`: Read packets from the `myNetworkTraffic.pcap` file.
- `-Y "tcp.len==12 || tcp.len==4"`: Filter TCP packets with length 12 or 4 bytes.
- `-T fields`: Output the specific fields.
- `-e frame.time`: Display the timestamp of the frame.
- `-e tcp.segment_data`: Extract the TCP segment data (payload).
- **`sort -k4:`**Sorts the output based on the 4th field (typically the timestamp ).
- **`awk '{print $6}':`**Prints the 6th field from the sorted output, which is the actual segment data (TCP payload).
- **`xxd -p -r:`**Converts the data from a hex dump to binary (`r` reverses the hex dump), so the data is in its raw format.
- **`base64 -d:`**Decodes the raw data from Base64 format back into its original binary form.


Final Flag : picoCTF{1t_w4snt_th4t_34sy_tbh_4r_959f50d3}  

