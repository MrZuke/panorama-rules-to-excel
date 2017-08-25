panorama-rules-to-excel
=======================

Create an Excel Spreadsheet from your firewall rules in Palo Alto Networks Panorama.

Usage
=====
    usage: pan_to_excel.py [-h] -k APIKEY -f FIREWALL -p PANORAMA
    
    Convert Palo Alto Network Firewall rules from Panorama to Microsoft Excel.
      
      optional arguments:
        -h, --help            show this help message and exit
        -k APIKEY, --apikey APIKEY
                              PAN API Token Key
        -f FIREWALL, --firewall FIREWALL
                              Name of Firewall Device Group
        -p PANORAMA, --panorama PANORAMA
                              Panorama Managment URL
      
      i.e. pan_to_excel.py --apikey "23j4kl2j34klj2kl4hf5yf" --firewall "Prod
      firewall 1" --panorama "https://panorama.somewhere.com

Usage Notes
===========
* The "firewall" listing is the device group and will list only rules specific to that device group.  Depending on hierarchy this may display more or less rules than you expect.
* You must generate an API key for the firewall you plan to query.   See Palo Alto documentation for API key generation: https://www.paloaltonetworks.com/documentation/70/pan-os/pan-os/device-management/use-the-xml-api.html

Dependencies
============
Python with the following modules:

* requests
* ElementTree
* xlsxwriter
* argparse

Fork Specifics
============
This fork has the following changes:

* Fixed a bugin wherein "epi" was built "api" breaking the script
* Disabled SSL verify to enable self-signed panorama instances
* Added "services" to query
