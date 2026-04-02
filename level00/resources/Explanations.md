1. La vidéo me donne un indice: "FIND this first file who can run only as flag00..."
2. Je lance donc ``find / -type f -user flag00 2> /dev/null`` qui me renvoie un seul fichier
3. Le contenu du fichier est ``cdiiddwpgswtgt``
4. Je l'essaie en mdp, cela ne marche pas, je le met donc dans dcode pour voir les differentes possibilite de chiffrement, le chiffrement ROT me renvoie nottohardhere, j'ai trouve le mot de passe. 