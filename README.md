# research
### Markdown cheat-sheet))
https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project
Template 
https://github.com/ritaly/README-cheatsheet/blob/master/README.md
## To Do Next
- Import from txt file



## TOC
* [DNS Records](#dns-records)
* [TXT records](#txt-records)
* [Netcraft for domain record search](*netcraft-for-domain-record-search)
* [Who owns the IP](*who-owns-the-ip)

## DNS Records 
```sh
whois <domain name>
dig @<NS IP> -t AXFR <domain name>
host -t txt <domain name>
```
### TXT records
```sh
host -t txt <domain name>
```
TXT records guide - https://www.cloudflare.com/learning/dns/dns-records/dns-txt-record/
A sender policy framework (SPF) records guide - https://www.cloudflare.com/learning/dns/dns-records/dns-spf-record/

### Netcraft for domain record search
  https://searchdns.netcraft.com/?host
  
### Who owns the IP
  whois 161.225.130.163
  https://check-host.net

### How to exclude <word> 
grep -wv <word> <filename>
grep -wv -e <word1> -e <word2> <filename>
grep -wv 'nologin\|bash' /etc/passwd
  
### How to find IP behind WAF
https://geekflare.com/find-real-ip-origin-address-of-website/
  
### MISC DNS Tools
https://securitytrails.com/
https://www.prepostseo.com/
https://dns-history.whoisxmlapi.com/overview
https://suip.biz/?act=domainiphistory
  
## OSINT (almost)

### Leaked data  
https://search.ddosecrets.com/data/  
https://ddosecrets.com/wiki/Special:AllPages
https://share.vx-underground.org/
  
  
## Port scanning  
### List of interesting ports
-pT:21,22,23,53,80,110,135,143,445,465,587,992,993,1080,1194,1433,5555,6666,6667,8443,9100,10010,U:53,67,68,69,123,137,138,139,161,162,445,514,631,1434,1645,1646,1701,1812,1900,2049,3283,5060,5353
```zsh
sudo nmap -Pn -sS -sU -pT:21,22,23,53,80,110,135,143,445,465,587,992,993,1080,1194,1433,5555,6666,6667,8443,9100,10010,U:53,67,68,69,123,137,138,139,161,162,445,514,631,1434,1645,1646,1701,1812,1900,2049,3283,5060,5353 -T4 -A -r -iL ./patr-hosts.txt -oA scanned-hosts-%D
  
```  
