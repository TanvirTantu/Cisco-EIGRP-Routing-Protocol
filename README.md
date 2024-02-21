EIGRP (Enhanced Interior Gateway Routing Protocol) is a Cisco proprietary routing protocol used for routing decisions within an autonomous system (AS). 
Configuring EIGRP involves several steps:

Enable EIGRP: First, you need to enable EIGRP on the router. This is done in global configuration mode:
Router(config)# router eigrp <AS_number>

Configure Network Interfaces: You need to specify which network interfaces will participate in EIGRP routing. This is done in router configuration mode:
Router(config-router)# network <network_address>

Set the Router ID (Optional): You can manually set the router ID (RID) for EIGRP. If you don't set it, the highest IP address of any active interface is used:
Router(config-router)# eigrp router-id <IP_address>

Adjust Metric Weights (Optional): EIGRP uses several metrics for path selection, including bandwidth, delay, reliability, load, and MTU. You can adjust these metrics using the metric weights command in router configuration mode:
Router(config-router)# metric weights <K1> <K2> <K3> <K4> <K5>

Set Passive Interfaces (Optional): You can set interfaces to passive if you don't want EIGRP to form neighbor relationships on them. This can be useful for interfaces connected to stub networks or networks where you don't want EIGRP traffic:
Router(config-router)# passive-interface <interface>

Authentication (Optional): You can configure authentication to secure EIGRP routing updates:
Router(config-router)# authentication mode <mode>
Router(config-router)# authentication key-chain <chain_name>

View EIGRP Configuration: After configuring EIGRP, you can verify the settings using:
Router# show ip protocols
Router# show ip eigrp neighbors
Router# show ip eigrp topology

Remember to save your configuration changes using the write memory or copy running-config startup-config command to ensure they are retained after a reboot.
