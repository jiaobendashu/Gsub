# Gsub
One command to get subdomains.


## Need
- [subfinder](https://github.com/projectdiscovery/subfinder)
- [ksubdomain](https://github.com/knownsec/ksubdomain)
- [httprobe]([httprobe](https://github.com/tomnomnom/httprobe))
- [httpx](https://github.com/projectdiscovery/httpx)


## Usage
Download [subfinder](https://github.com/projectdiscovery/subfinder/releases/) & [ksubdomain](https://github.com/knownsec/ksubdomain/releases) & [httprobe](https://github.com/tomnomnom/httprobe) & [httpx](https://github.com/projectdiscovery/httpx/releases),and make sure they are all in the same directory.

## Example
```bash
┌──(root💀kali)-[/home/jiaobendashu/Soft/Gsub]
└─# ls
httprobe  httpx  ksubdomain  subfinder
```

## Shell
`You just need to change the value of domain.`

```bash
┌──(root💀kali)-[/home/jiaobendashu/Soft/Gsub]
└─# domain=dj.com;./subfinder -d ${domain} -nC -max-time 5 -timeout 5 -r 156.154.70.5, 156.154.71.5 -silent -nW |./ksubdomain -verify -silent | ./httprobe -c 50 |./httpx -no-color -cdn -websocket -retries 3 -web-server -cname -ip -title -status-code -follow-redirects | sed 's/ /,/g;' > Gsub_${domain}.txt
```

## Result
```bash
┌──(root💀kali)-[/home/jiaobendashu/Soft/Gsub]
└─# cat Gsub_${domain}.txt
```

## Thanks
- subfinder
- ksubdomain
- httprobe
- httpx