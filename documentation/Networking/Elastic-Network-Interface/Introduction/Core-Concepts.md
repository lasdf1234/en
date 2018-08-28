# Core concept
Before operating the Elastic Network Interface, please understand the following basic concepts and professional terms of the Elastic Network Interface in detail.

| English | Chinese | Description |
| :- | :- | :- |
| Elastic Network Interface | 弹性网卡 | Elastic Network Interface is a virtual network interface that can be independently applied for and can be elastically plugged from the Virtual Machine |
| Primary Network Interface | 主网卡 | Primary network interface is a special-type Elastic Network Interface that is created with the Virtual Machine and has the same life cycle as the Virtual Machine |
| Secondary Network Interface | 辅助网卡 | Secondary network interface is a type of Elastic Network Interface that can be created and deleted independently and can be plugged elastically|
| Primary IP | 主IP | The first Private IP address allocated when the Elastic Network Interface was created can be specified by the user or allocated by the system and cannot be modified and released |
| Secondary IP | 辅助IP | Other Private IP addresses other than Primary IP, which are allocated by the Elastic Network Interface, can be specified by the user or allocated by the system and can be released |
| Elastic IP | 弹性公网IP | The Elastic IP is a public IP address that can be applied independently and flexibly associated and disassociated with Private IP |
| Security Group | 安全组 | Security Group is a distributed and stateful firewall that filters traffic to and from an Elastic Network Interface |
| MAC | MAC地址 | MAC address is the unique identifier for an Elastic Network Interface |