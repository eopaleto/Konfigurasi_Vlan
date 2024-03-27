# Konfigurasi Vlan Satryo Pangestu TK4B

![image](https://github.com/eopaleto/Konfigurasi_Vlan/assets/126212773/ebd8d042-2d7c-4774-baeb-4229b96ab865)

![image](https://github.com/eopaleto/Konfigurasi_Vlan/assets/126212773/f8b19433-1c49-4531-89c6-e097181a416e)

**1. Buat dan beri nama Vlan di S1**

**S1**  
S1# config t  
S1#(config)# vlan 10  
S1#(config-vlan)# name Faculty/Staff 
S1#(config)# vlan 20  
S1#(config-vlan)# name Students
S1#(config)# vlan 30  
S1#(config-vlan)# name Guest(Default)
S1#(config)# vlan 99  
S1#(config-vlan)# name Mangement&Native
S1#(config)# vlan 150  
S1#(config-vlan)# name VOICE

**S2**
  
S2(config)#vlan 10  
S2(config-vlan)#name Faculty/Staff  
S2(config-vlan)#vlan 20  
S2(config-vlan)#name Students  
S2(config-vlan)#vlan 30  
S2(config-vlan)#name Guest(Default)  
S2(config-vlan)#vlan 99  
S2(config-vlan)#name Management&Native   
S2(config-vlan)#vlan 150  
S2(config-vlan)#name VOICE   

**S3**

S3(config)#vlan 10  
S3(config-vlan)#name Faculty/Staff  
S3(config-vlan)#vlan 20  
S3(config-vlan)#name Students  
S3(config-vlan)#vlan 30  
S3(config-vlan)#name Guest(Default)  
S3(config-vlan)#vlan 99  
S3(config-vlan)#name Management&Native  
S3(config-vlan)#vlan 150  
S3(config-vlan)#name VOICE  

**2. Assign VLANs to the active ports on S2.**

**S2**
- VLAN 10: FastEthernet 0/11  
- VLAN 20: FastEthernet 0/18  
- VLAN 30: FastEthernet 0/6
  
S2(config)# interface f0/11   
S2(config-if)# switchport mode access  
S2(config-if)# switchport access vlan 10  

S2(config-if)#interface f0/18  
S2(config-if)#switchport mode access  
S2(config-if)#switchport access vlan 20  

S2(config-if)#interface f0/6  
S2(config-if)#switchport mode access  
S2(config-if)#switchport access vlan 30  
S2(config-if)#  

**S3**

- VLAN 10: FastEthernet 0/11
- VLAN 20: FastEthernet 0/18
- VLAN 30: FastEthernet 0/6

S3(config)#interface f0/11  
S3(config-if)#switchport mode access  
S3(config-if)#switchport access vlan 10  

S3(config-if)#interface f0/18  
S3(config-if)#switchport mode access  
S3(config-if)#switchport access vlan 20  

S3(config-if)#interface f0/6  
S3(config-if)#switchport mode access  
S3(config-if)#switchport access vlan 30  

**3. Assign the VOICE VLAN to FastEthernet 0/11 on S3.**

S3(config)# interface f0/11  
S3(config-if)# mls qos trust cos  
S3(config-if)# switchport voice vlan 150  

**4. Verify Loss of Connectivity**

![image](https://github.com/eopaleto/Konfigurasi_Vlan/assets/126212773/4c015067-c0f8-4448-a360-d1478713851a)

![image](https://github.com/eopaleto/Konfigurasi_Vlan/assets/126212773/f5f434fc-7080-40e7-8885-60d89fd56f52)
