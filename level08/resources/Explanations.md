1. Presence de deux fichiers -> token et un executable level08
2. Essaie de lancer executable avec token , message d'erreur : You may not access 'token'
3. utilisation de ghidra pour decompiler code
4. Le code decompiler affiche que le message d'erreur s'affiche seulement quand le nom du fichier, donne en argument, contient le mot token
5. ``chmod 777 .`` pour pouvoir creer simlink
6. Pas les droits necessaire pour renommer le file token, donc je creer un simlink ver token avec la commande: ``ln -s /home/user/level08/token /home/user/level08/a``
7. Cela m'affiche le contenu, et c'est le mot de passe pour se connecter a flag08, je lance getflag et j'ai mon flag
