# BloodHound.py
![Python 2.7](https://img.shields.io/badge/python-2.7.x-blue.svg)
![PyPI version](https://img.shields.io/pypi/v/bloodhound.svg)
![License: MIT](https://img.shields.io/pypi/l/bloodhound.svg)

BloodHound.py is a Python based ingestor for [BloodHound](https://github.com/BloodHoundAD/BloodHound), based on [Impacket](https://github.com/CoreSecurity/impacket/).

## Limitations
BloodHound.py currently has the following limitations:
- Only supports default BloodHound (SharpHound) features, so only Groups, Admins, Sessions and Trusts
- Name, command line parameters and features may change in the future
- Kerberos support is not yet complete
- Cross-forest membership resolving is not implemented yet

## Installation and usage
You can install the ingestor via pip with `pip install bloodhound`, or by cloning this repository and running `python setup.py install`, or with `pip install .`.
BloodHound.py requires `impacket`, `ldap3` and `dnspython` to function.

The installation will add a command line tool `bloodhound-python` to your PATH.

To use the ingestor, at a minimum you will need credentials of the domain you're logging in to.
You will need to specify the `-u` option with a username of this domain (or `username@domain` for a user in a trusted domain). If you have your DNS set up properly and the AD domain is in your DNS search list, then BloodHound.py will automatically detect the domain for you. If not, you have to specify it manually with the `-d` option.

By default BloodHound.py will query LDAP and the individual computers of the domain to enumerate users, computers, groups, sessions and local admins. To disable some checks, see the options.
