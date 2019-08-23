**!!!ATTENTION!!!**
**From version 20190824.0 on there is a "breaking" change from previous 
versions.  Now use `import fmcapi` to import the package.  Add `fmcapi.` 
in front of all your API class object calls, for example, use 
`fmcapi.ACPRule` instead of just `ACPRule`.**

# fmcapi
Provide an "easier to use" way of interacting with the Cisco FMC's API.
There is a LOT that has yet to be done in order to make this project 
have "feature parity" with all that can be done with the FMC's API.
That said, what is here works!

The fmcapi is published to PyPI.  This means you can install it via pip 
(`pip3 install fmcapi`)

## Features
* Creation and maintenance of the connection with the FMC.  This 
basically is care and feeding of the token.
* Register devices with FMC.
* Deploy changes to FMC managed devices.
* GET/POST/PUT/DELETE of: 
  * Host Objects
  * Network Objects
  * Range Objects
  * Port Objects
  * ICMPv4/ICMPv6 Objects
  * Security Zones Objects
  * Interface Group Objects
  * URL Objects
  * FQDNS Objects
  * IKEv1/IKEv1 IPsec Proposal and Policy Objects
  * DNS Server Groups
  * Access Control Policy (ACP)
  * ACP Rules
  * VLAN Tags
  * Devices/Device Groups/Device HA
  * FTD Device Interfaces
  * IPv4/IPv6 Static Routes
  * NAT Policy
  
* Other features:
  * GET Intrusion Policy
  * GET all Network Objects
  * GET all Device Static Routes
  * GET all Cert Enrollments
  * GET all Extended Access Lists
  * GET all Geolocations
  * GET VariableSet(s)
  * Register FTD Devices
  * Task Status checking.
  * Software Upgrade Deployments.

* This is now an installable Python package via pip!  I'm heavily 
developing this code so you might want to issue the  command 
`pip3 install -U fmcapi` to update your installed version.

## Quickstart on how to use this package
First install it with: `pip3 install fmcapi`
Then to use the code best start a "with" statement that creates an 
instance of the FMC class like this: `with fmcapi.FMC(
host='192.168.11.15', username='admin', password='Admin123', 
autodeploy=False) as fmc:`  Then either code away referencing the fmc 
variable to get to the internal methods of the FMC class **or** utilize 
the various class objects to ease your coding needs.
 
I recorded a quick "howto" video which can be accessed via: 
https://www.youtube.com/watch?v=4NIe3T-HjDw
 
**Note #1:  Check out the TestingUsersScript.py file for ideas on how 
to use fmcapi (until I get around to writing documentation).**

**Note #2:  You can directly send requests to the FMC via the 
send_to_api() method in the FMC class.  This allows you to access any 
of the API features of the FMC.**

## ToDos
* Site2Site VPN Policy.
* ISE SGT.
* Version checking.
* Modify NGIPS device interfaces.
* Move the create_acp_rules FMC method into a class object in the 
api_objects module.
* Build a complete system for all FMC API accessible objects (feature 
parity).  Currently just over 76% of the FMC's version 6.3 API objects 
are represented in the fmcapi.
* **Most importantly:** Write better how-to instructions.  (Anyone 
willing to help?) 
