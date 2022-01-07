[comment]: # "Auto-generated SOAR connector documentation"
# ThreatMiner API

Publisher: Domenico Perre  
Connector Version: 1\.0\.0  
Product Vendor: ThreatMiner  
Product Name: API  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.0\.1068  

This app integrates with the ThreatMiner API to provide investigation activities

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a API asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base\_url** |  required  | string | Base URL for api request

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[lookup domain](#action-lookup-domain) - Check for the presence of a domain in a threat intelligence feed  
[lookup hash](#action-lookup-hash) - Check for the presence of a hash in a threat intelligence feed  
[lookup ip](#action-lookup-ip) - Check for the presence of an IP in a threat intelligence feed  
[whois domain](#action-whois-domain) - Execute whois lookup on the given domain  
[reverse ip](#action-reverse-ip) - Find domain names that share an IP  
[whois ip](#action-whois-ip) - Execute whois lookup on the given IP address  
[lookup av](#action-lookup-av) - Lookup AV String  
[lookup ssl](#action-lookup-ssl) - Search SSL thumbprint  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'lookup domain'
Check for the presence of a domain in a threat intelligence feed

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**domain** |  required  | Domain to lookup | string |  `domain`  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.domain | string |  `domain`  `url` 
action\_result\.data\.\*\.results\.\*\.first\_seen | string | 
action\_result\.data\.\*\.results\.\*\.ip | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.results\.\*\.last\_seen | string | 
action\_result\.data\.\*\.status\_code | string | 
action\_result\.data\.\*\.status\_message | string | 
action\_result\.summary\.domain | string |  `domain` 
action\_result\.summary\.status\_message | string | 
action\_result\.message | string | 
summary\.status\_message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'lookup hash'
Check for the presence of a hash in a threat intelligence feed

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**hash** |  required  | Hash to lookup | string |  `sha256`  `sha1`  `md5` 
**hash\_type** |  required  | Cryptographic Hash, Imphash or SSDEEP to lookup | string |  `hash`  `ssdeep`  `imphash` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.hash | string |  `sha256`  `sha1`  `md5` 
action\_result\.parameter\.hash\_type | string |  `hash`  `ssdeep`  `imphash` 
action\_result\.data\.\*\.av\_detections\.results\.\*\.av\_detections\.\*\.av | string | 
action\_result\.data\.\*\.av\_detections\.results\.\*\.av\_detections\.\*\.detection | string | 
action\_result\.data\.\*\.av\_detections\.status\_code | string | 
action\_result\.data\.\*\.av\_detections\.status\_message | string | 
action\_result\.data\.\*\.hosts\_domains\_and\_ips | string |  `domain` 
action\_result\.data\.\*\.http\_traffic | string | 
action\_result\.data\.\*\.metadata\.results\.\*\.architecture | string | 
action\_result\.data\.\*\.metadata\.results\.\*\.authentihash | string | 
action\_result\.data\.\*\.metadata\.results\.\*\.date\_analysed | string | 
action\_result\.data\.\*\.metadata\.results\.\*\.file\_name | string | 
action\_result\.data\.\*\.metadata\.results\.\*\.file\_size | string | 
action\_result\.data\.\*\.metadata\.results\.\*\.file\_type | string | 
action\_result\.data\.\*\.metadata\.results\.\*\.imphash | string | 
action\_result\.data\.\*\.metadata\.results\.\*\.md5 | string |  `md5` 
action\_result\.data\.\*\.metadata\.results\.\*\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.metadata\.results\.\*\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.metadata\.results\.\*\.sha512 | string | 
action\_result\.data\.\*\.metadata\.results\.\*\.ssdeep | string | 
action\_result\.data\.\*\.metadata\.status\_code | string | 
action\_result\.data\.\*\.metadata\.status\_message | string | 
action\_result\.data\.\*\.mutants | string | 
action\_result\.data\.\*\.registry\_keys | string | 
action\_result\.data\.\*\.report\_tagging | string | 
action\_result\.data\.\*\.report\_tagging\.results\.\*\.URL | string |  `url` 
action\_result\.data\.\*\.report\_tagging\.results\.\*\.filename | string | 
action\_result\.data\.\*\.report\_tagging\.results\.\*\.year | string | 
action\_result\.data\.\*\.report\_tagging\.status\_code | string | 
action\_result\.data\.\*\.report\_tagging\.status\_message | string | 
action\_result\.summary\.hash | string |  `md5`  `sha256` 
action\_result\.summary\.status\_message | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'lookup ip'
Check for the presence of an IP in a threat intelligence feed

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to lookup | string |  `ip`  `ipv6` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.ip | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.related\_samples | string | 
action\_result\.data\.\*\.report\_tagging | string | 
action\_result\.data\.\*\.ssl\_certificates | string | 
action\_result\.data\.\*\.uris | string | 
action\_result\.summary\.ip | string | 
action\_result\.summary\.status\_message | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'whois domain'
Execute whois lookup on the given domain

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**domain** |  required  | Domain to query | string |  `domain` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.domain | string |  `domain`  `url` 
action\_result\.data\.\*\.results\.\*\.domain | string |  `domain` 
action\_result\.data\.\*\.results\.\*\.is\_subdomain | boolean |  `domain` 
action\_result\.data\.\*\.results\.\*\.last\_updated | string | 
action\_result\.data\.\*\.results\.\*\.root\_domain | string |  `domain` 
action\_result\.data\.\*\.results\.\*\.whois\.admin\_info\.City | string | 
action\_result\.data\.\*\.results\.\*\.whois\.admin\_info\.Country | string | 
action\_result\.data\.\*\.results\.\*\.whois\.admin\_info\.Organization | string | 
action\_result\.data\.\*\.results\.\*\.whois\.admin\_info\.Postal\_Code | string | 
action\_result\.data\.\*\.results\.\*\.whois\.admin\_info\.State | string | 
action\_result\.data\.\*\.results\.\*\.whois\.billing\_info\.City | string | 
action\_result\.data\.\*\.results\.\*\.whois\.billing\_info\.Country | string | 
action\_result\.data\.\*\.results\.\*\.whois\.billing\_info\.Organization | string | 
action\_result\.data\.\*\.results\.\*\.whois\.billing\_info\.Postal\_Code | string | 
action\_result\.data\.\*\.results\.\*\.whois\.billing\_info\.State | string | 
action\_result\.data\.\*\.results\.\*\.whois\.creation\_date | string | 
action\_result\.data\.\*\.results\.\*\.whois\.date\_checked | string | 
action\_result\.data\.\*\.results\.\*\.whois\.email\_hashes\.admin | string | 
action\_result\.data\.\*\.results\.\*\.whois\.email\_hashes\.billing | string | 
action\_result\.data\.\*\.results\.\*\.whois\.email\_hashes\.registrant | string | 
action\_result\.data\.\*\.results\.\*\.whois\.email\_hashes\.tech | string | 
action\_result\.data\.\*\.results\.\*\.whois\.emails\.admin | string | 
action\_result\.data\.\*\.results\.\*\.whois\.emails\.billing | string | 
action\_result\.data\.\*\.results\.\*\.whois\.emails\.registrant | string | 
action\_result\.data\.\*\.results\.\*\.whois\.emails\.tech | string | 
action\_result\.data\.\*\.results\.\*\.whois\.expiration\_date | string | 
action\_result\.data\.\*\.results\.\*\.whois\.reg\_info\.City | string | 
action\_result\.data\.\*\.results\.\*\.whois\.reg\_info\.Country | string | 
action\_result\.data\.\*\.results\.\*\.whois\.reg\_info\.Organization | string | 
action\_result\.data\.\*\.results\.\*\.whois\.reg\_info\.Postal\_Code | string | 
action\_result\.data\.\*\.results\.\*\.whois\.reg\_info\.State | string | 
action\_result\.data\.\*\.results\.\*\.whois\.registrant\_info\.City | string | 
action\_result\.data\.\*\.results\.\*\.whois\.registrant\_info\.Country | string | 
action\_result\.data\.\*\.results\.\*\.whois\.registrant\_info\.Organization | string | 
action\_result\.data\.\*\.results\.\*\.whois\.registrant\_info\.Postal\_Code | string | 
action\_result\.data\.\*\.results\.\*\.whois\.registrant\_info\.State | string | 
action\_result\.data\.\*\.results\.\*\.whois\.registrar | string | 
action\_result\.data\.\*\.results\.\*\.whois\.tech\_info\.City | string | 
action\_result\.data\.\*\.results\.\*\.whois\.tech\_info\.Country | string | 
action\_result\.data\.\*\.results\.\*\.whois\.tech\_info\.Organization | string | 
action\_result\.data\.\*\.results\.\*\.whois\.tech\_info\.Postal\_Code | string | 
action\_result\.data\.\*\.results\.\*\.whois\.tech\_info\.State | string | 
action\_result\.data\.\*\.results\.\*\.whois\.updated\_date | string | 
action\_result\.data\.\*\.results\.\*\.whois\.whois\_server | string | 
action\_result\.data\.\*\.status\_code | string | 
action\_result\.data\.\*\.status\_message | string | 
action\_result\.summary\.domain | string |  `domain`  `url` 
action\_result\.summary\.status\_message | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'reverse ip'
Find domain names that share an IP

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP address to query | string |  `ip`  `ipv6` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.ip | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.results\.\*\.domain | string |  `domain` 
action\_result\.data\.\*\.results\.\*\.first\_seen | string | 
action\_result\.data\.\*\.results\.\*\.last\_seen | string | 
action\_result\.data\.\*\.status\_code | string | 
action\_result\.data\.\*\.status\_message | string | 
action\_result\.summary\.domain | string |  `ip`  `domain` 
action\_result\.summary\.ip | string | 
action\_result\.summary\.status\_message | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'whois ip'
Execute whois lookup on the given IP address

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to query | string |  `ip`  `ipv6` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.ip | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.results\.\*\.asn | string | 
action\_result\.data\.\*\.results\.\*\.asn\_name | string | 
action\_result\.data\.\*\.results\.\*\.bgp\_prefix | string | 
action\_result\.data\.\*\.results\.\*\.cc | string | 
action\_result\.data\.\*\.results\.\*\.org\_name | string | 
action\_result\.data\.\*\.results\.\*\.register | string | 
action\_result\.data\.\*\.results\.\*\.reverse\_name | string | 
action\_result\.data\.\*\.status\_code | string | 
action\_result\.data\.\*\.status\_message | string | 
action\_result\.summary\.domain | string |  `domain` 
action\_result\.summary\.ip | string | 
action\_result\.summary\.status\_message | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'lookup av'
Lookup AV String

Type: **investigate**  
Read only: **True**

Lookup AV string to find known hashes\. For example you can lookup 'Trojan\.Enfal'

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**av\_string** |  optional  | The detection name from the AV vendor | string |  `avdetection` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.av\_string | string | 
action\_result\.data\.\*\.report\_tagging\.results\.\*\.URL | string |  `url` 
action\_result\.data\.\*\.report\_tagging\.results\.\*\.filename | string | 
action\_result\.data\.\*\.report\_tagging\.results\.\*\.year | string | 
action\_result\.data\.\*\.report\_tagging\.status\_code | string | 
action\_result\.data\.\*\.report\_tagging\.status\_message | string | 
action\_result\.data\.\*\.samples | string | 
action\_result\.summary\.av\_string | string | 
action\_result\.summary\.status\_message | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'lookup ssl'
Search SSL thumbprint

Type: **investigate**  
Read only: **True**

Lookup an SSL thumbprint against ThreatMiner API and return known IP addresses associated with that same SSL certificate

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**thumbprint** |  required  | SSL Thumbprint | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.thumbprint | string | 
action\_result\.data\.\*\.results\.\*\.ip | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.status\_code | string | 
action\_result\.data\.\*\.status\_message | string | 
action\_result\.summary\.status\_message | string | 
action\_result\.summary\.thumbprint | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 