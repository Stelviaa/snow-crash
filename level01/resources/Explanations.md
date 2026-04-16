1. Check fichiers liés à flag01 : "find / -type f -user flag01 2> /dev/null" ne trouve rien
2. Check infos système sur flag01 : "cat /etc/group" rien d'intéressant, "cat /etc/sudoers" permission denied, "cat /etc/passwd" -> flag01:42hDRfypTqqnw:3001:3001::/home/flag/flag01:/bin/bash
3. Hash visible -> Appel au frérot John the ripper (password cracker) :
- echo "flag01:42hDRfypTqqnw" > hash.txt
- john --show hash.txt -> abcdefg