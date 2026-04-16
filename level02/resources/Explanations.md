1. ``ls`` -> un seul fichier .pcap -> fichier de package
2. Je transfere le fichier de la vm snow-crash a ma vm kali grace a ``scp``
3. J'ouvre le fichier avec un outils pour lire les pcap: Wireshark
4. Je reconcatene le flux en faisant clique droit Follow > TCP Stream
5. Le contenu me fait comprendre que c'est une page de login
6. Le mot de passe donné est ``ft_wandr...NDRel.L0L``
7. Je l'essaie il ne marche pas
8. En regardant paquet par paquet je remarque que les points ont tous la valeurs 7f qui est DEL en ascci
9. En reformatant le mot de passe, j'ai ``ft_waNDReL0L``
