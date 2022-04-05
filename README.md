# research

Host discovery

dig @9<NS IP> -t AXFR <domain name>
whois <domain name>


TXT records
code
host -t txt <domail name>

  TXT records guide - https://www.cloudflare.com/learning/dns/dns-records/dns-txt-record/
  
  A sender policy framework (SPF) records guide - https://www.cloudflare.com/learning/dns/dns-records/dns-spf-record/

Netcraft for domeain record search
  https://searchdns.netcraft.com/?host
  
Who owns the IP
  whois 161.225.130.163
  https://check-host.net

  
  exclude <word> 
grep -wv <word> <filename>
grep -wv -e <word1> -e <word2> <filename>
grep -wv 'nologin\|bash' /etc/passwd

-pT:21,22,23,53,80,110,135,143,445,465,587,992,993,1080,1194,1433,5555,6666,6667,8443,9100,10010,U:53,67,68,69,123,137,138,139,161,162,445,514,631,1434,1645,1646,1701,1812,1900,2049,3283,5060,5353

sudo nmap -Pn -sS -sU -pT:21,22,23,53,80,110,135,143,445,465,587,992,993,1080,1194,1433,5555,6666,6667,8443,9100,10010,U:53,67,68,69,123,137,138,139,161,162,445,514,631,1434,1645,1646,1701,1812,1900,2049,3283,5060,5353 -T4 -A -r -iL ./patr-hosts.txt -oA scanned-hosts-%D
  
  
