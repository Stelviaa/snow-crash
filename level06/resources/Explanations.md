1. Le dossier contient du code php avec son executable
2. Je passe le code dans un formatter, pour pouvoir le lire
3. Apres quelques recherche sur internet je remarque que cette regex, ``"/(\[x (.*)\])/e"``, permet d'executer du code, qui plus est envoye en argument, dans un certain format
4. Je ``chmod 777 .`` pour creer un fichier, puisque le programme en attends un en entrer
5. Je mets ``[x ${`getflag`}]`` qui permet de matcher avec la regex, le code est interprete grace au `.
