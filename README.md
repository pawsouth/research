# Web-site research framework
Ver. 0.01 from 09.04.2022
by southpaw

# TOC

# Description
How to perform basic host analysis.

# Step 1. Site and Domian overview
http://sitename
https://sitename
Create file domains.txt with the domains and sites names.

# Host resolution
Who owns the IP
whois <domain name>
## Host and hosting
host <sitename>
https://check-host.net
host <hostname> | grep "has address" | awk '{print $4}'
cat hosts.txt | grep "has address" | awk '{print $4}' | sort | uniq > IPaddresses.txt

## DNS records
### A
host -t A <domain name>
### NS
host -t NS <domain name>  
### MX
host -t mx <domain name>
### TXT  
host -t txt <domain name>
TXT records guide - https://www.cloudflare.com/learning/dns/dns-records/dns-txt-record/
A sender policy framework (SPF) records guide - https://www.cloudflare.com/learning/dns/dns-records/dns-spf-record/
### Zone Transfer
dig @<NS IP> -t AXFR <domain name>
### MISC DNS Tools
https://securitytrails.com/
https://www.prepostseo.com/
https://dns-history.whoisxmlapi.com/overview
https://suip.biz/?act=domainiphistory
## Site protection
DDoS
### WAF Check
nmap -p80,443 --script http-waf-detect --script-args="http-waf-detect.aggro,http-waf-detect.detectBodyChanges" -iL ./patr-hosts.txt
### Define the host behind the WAF
#### How to find IP behind WAF
https://geekflare.com/find-real-ip-origin-address-of-website/
#### DNS History
https://securitytrails.com/
https://suip.biz/?act=domainiphistory
https://dns-history.whoisxmlapi.com/overview

#### Netcraft for domain record search
https://searchdns.netcraft.com/?host

## Open ports and services
### List of interesting ports
-pT:21,22,23,25,53,80,110,135,143,443,445,465,587,992,993,1080,1194,1433,5555,6666,6667,8443,9100,10010,U:53,67,68,69,123,137,138,139,161,162,445,514,631,1434,1645,1646,1701,1812,1900,2049,3283,5060,5353
### Sample scan
```zsh
sudo nmap -Pn -sS -sU -pT:21,22,23,53,80,110,135,143,445,465,587,992,993,1080,1194,1433,5555,6666,6667,8443,9100,10010,U:53,67,68,69,123,137,138,139,161,162,445,514,631,1434,1645,1646,1701,1812,1900,2049,3283,5060,5353 -T4 -A -r -iL ./patr-hosts.txt -oA scanned-hosts-%D
  
```    
  
## Discovered vunerabilities
### Vuln check
nmap -Pn -sV -p21,22,53,80,443 --script=vulners -iL ./patr-hosts.txt
nikto -h ./hosts-80.txt > patriarchia-hikto.txt
nikto -h <domain/ip> -Format msf+

## Exploits found

## Host user accounts  
### Leaked data  
https://search.ddosecrets.com/data/  
https://ddosecrets.com/wiki/Special:AllPages
https://share.vx-underground.org/
    
# Misc docs
https://cdn.comparitech.com/wp-content/uploads/2019/07/NIkto-Cheat-Sheet.pdf
https://www.tutorialspoint.com/nmap-cheat-sheet

Markdown cheat-sheet))
https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project
Template 
https://github.com/ritaly/README-cheatsheet/blob/master/README.md

  
### How to exclude <word> 
grep -wv <word> <filename>
grep -wv -e <word1> -e <word2> <filename>
grep -wv 'nologin\|bash' /etc/passwd
----
  
## TOC
* [DNS Records](#dns-records)
* [TXT records](#txt-records)
* [Netcraft for domain record search](*netcraft-for-domain-record-search)
* [Who owns the IP](*who-owns-the-ip)

## Port scanning  
### List of interesting ports
-pT:21,22,23,25,53,80,110,135,143,443,445,465,587,992,993,1080,1194,1433,5555,6666,6667,8443,9100,10010,U:53,67,68,69,123,137,138,139,161,162,445,514,631,1434,1645,1646,1701,1812,1900,2049,3283,5060,5353

