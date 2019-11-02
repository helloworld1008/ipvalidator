# IPValidator - A python module for validating IP addresses

IPValidator is a python module that validates IP addresses in IPAM applications. This prevents invalid IP addresses from being entered into the database/system by the user

- It returns a Tuple containing a Boolean flag, Network Address and Broadcast Address of the subnet if the user enters a valid IP address
- It catches a wide variety of errors that can occur when entering an invalid IP address and raises appropriate exceptions
- Can be used in any python-based frameworks such as Django, Flask, etc.

