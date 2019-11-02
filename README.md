# IPValidator - A python module for validating IP addresses

IPValidator is a python module that validates IP addresses in IPAM applications. This prevents invalid IP addresses from being entered into the database/system by the user

- It returns a Tuple containing a Boolean True flag, Network Address and Broadcast Address of the subnet if the user enters a valid IP address
- It catches a wide variety of errors that can occur when entering an invalid IP address and raises appropriate exceptions
- Can be used in any python-based frameworks such as Django, Flask, etc.

## Requirements

- Python (3.6 & above)
- Pip

## Installation

This module needs to be installed using pip

```bash
pip install ipvalidator

```

## How to use
Here's an example of calling IpValidator constructor on a valid IP address from the python shell
```bash
import ipvalidator

ip = ipvalidator.IpValidator('192.168.10.1/24')

ip.check_ip()
```
The output to stdout is 
```
(True, '192.168.10.0', '192.168.10.255')
```

Shown below is an example of calling IpValidator constructor on an invalid IP address from the python shell
```bash
ip = ipvalidator.IpValidator('300.168.10.1/24')
```

The output to stderr is 
```bash
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/root/Scripts/packaging_folder/ipvalidator/ipvalidator.py", line 20, in __init__
    self.check_all_octets()
  File "/root/Scripts/packaging_folder/ipvalidator/ipvalidator.py", line 61, in check_all_octets
    raise IpValidationError("The first octet must be between 1 to 223")
ipvalidator.IpValidationError: The first octet must be between 1 to 223
```

```bash
>>> ip = ipvalidator.IpValidator('192.168.10.300/24')
```

The output to stderr is 
```bash
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/root/Scripts/packaging_folder/ipvalidator/ipvalidator.py", line 20, in __init__
    self.check_all_octets()
  File "/root/Scripts/packaging_folder/ipvalidator/ipvalidator.py", line 65, in check_all_octets
    raise IpValidationError("Octet value must be between 0 to 255")
ipvalidator.IpValidationError: Octet value must be between 0 to 255
```
