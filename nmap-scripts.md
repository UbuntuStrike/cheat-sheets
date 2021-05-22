
dns-brute

Script types: prerule, hostrule
Categories: intrusive, discovery
Download: https://svn.nmap.org/nmap/scripts/dns-brute.nse

Attempts to enumerate DNS hostnames by brute force guessing of common subdomains. With the dns-brute.srv argument, dns-brute will also try to enumerate common DNS SRV records.

nmap --script dns-brute --script-args dns-brute.domain=foo.com,dns-brute.threads=6,dns-brute.hostlist=./hostfile.txt,newtargets -sS -p 80

http-backup-finder

Script types: portrule
Categories: discovery, safe
Download: https://svn.nmap.org/nmap/scripts/http-backup-finder.nse

Spiders a website and attempts to identify backup copies of discovered files. It does so by requesting a number of different combinations of the filename (eg. index.bak, index.html~, copy of index.html).

nmap --script=http-backup-finder <target>

mongodb-databases

Script types: portrule
Categories: default, discovery, safe
Download: https://svn.nmap.org/nmap/scripts/mongodb-databases.nse

Attempts to get a list of tables from a MongoDB database.

nmap -p 27017 --script mongodb-databases <host>

shodan-api

Script types:
Categories: discovery, safe, external
Download: https://svn.nmap.org/nmap/scripts/shodan-api.nse

Queries Shodan API for given targets and produces similar output to a -sV nmap scan. The ShodanAPI key can be set with the ‘apikey’ script argument, or hardcoded in the .nse file itself. You can get a free key from https://developer.shodan.io

N.B if you want this script to run completely passively make sure to include the -sn -Pn -n flags.

nmap --script shodan-api x.y.z.0/24 -sn -Pn -n --script-args 'shodan-api.outfile=potato.csv,shodan-api.apikey=SHODANAPIKEY'

http-config-backup

Script types: portrule
Categories: auth, intrusive
Download: https://svn.nmap.org/nmap/scripts/http-config-backup.nse

Checks for backups and swap files of common content management system and web server configuration files.

nmap --script=http-config-backup <target>

http-proxy-brute

Script types: portrule
Categories: brute, intrusive, external
Download: https://svn.nmap.org/nmap/scripts/http-proxy-brute.nse

Performs brute force password guessing against HTTP proxy servers.

nmap --script http-proxy-brute -p 8080 <host>

http-brute

Script types: portrule
Categories: intrusive, brute
Download: https://svn.nmap.org/nmap/scripts/http-brute.nse

Performs brute force password auditing against http basic, digest and ntlm authentication.

This script uses the unpwdb and brute libraries to perform password guessing. Any successful guesses are stored in the nmap registry, using the creds library, for other scripts to use.

nmap --script http-brute -p 80 <host>

http-rfi-spider

Script types: portrule
Categories: intrusive
Download: https://svn.nmap.org/nmap/scripts/http-rfi-spider.nse

Crawls webservers in search of RFI (remote file inclusion) vulnerabilities. It tests every form field it finds and every parameter of a URL containing a query.

nmap --script http-rfi-spider -p80 <host>

http-default-accounts

Script types: portrule
Categories: discovery, auth, intrusive
Download: https://svn.nmap.org/nmap/scripts/http-default-accounts.nse

Tests for access with default credentials used by a variety of web applications and devices.

It works similar to http-enum, we detect applications by matching known paths and launching a login routine using default credentials when found. This script depends on a fingerprint file containing the target’s information: name, category, location paths, default credentials and login routine.

nmap -p80 --script http-default-accounts host/ip

http-put

Script types: portrule
Categories: discovery, intrusive
Download: https://svn.nmap.org/nmap/scripts/http-put.nse

Uploads a local file to a remote web server using the HTTP PUT method. You must specify the filename and URL path with NSE arguments.

nmap -p 80 <ip> --script http-put --script-args http-put.url='/uploads/rootme.php',http-put.file='/tmp/rootme.php'

   
