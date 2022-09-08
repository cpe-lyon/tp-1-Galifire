*Raphaël DUMAS - 3ICS*

# TP 1 - Installation d’Ubuntu Server et prise en main du shell

## Exercice 2. Prise en main de l'interpréteur de commandes

### Manuel

1. Pour identifier le rôle de la commande which, on entre la commande `man which`.
On découvre alors que la commande which doit prendre un nom de fichier en argument, pour en retourner le fichier exécutable et sa location.

2. Pour rechercher un terme dans le manuel, il faut appuyer sur la touche '/' et entrer à la suite les termes ou mots recherchés.

3. Pour quitter le manuel, il suffit d'appuyer sur la touche 'q'.

4. Pour afficher la première page d'une section, ici la section 6, il faut entrer la commande `man -K 6`.
Cela nous envoie alors dans la section dpkg-maintscript-helper, qui nous indique que cela implémente le dpkg (gestionnaire de packages) pour lui ajouter des fonctions qu'il ne peut gérer seul.

### Navigation dans l'arborescence de fichiers

1. Pour se déplacer dans les fichiers, ici le répertoire /var/log/, il faut entrer la commande `cd /var/log/`. Ici la commande cd permet de changer de répertoire (cd : change directory).

2. Pour revenir au dossier racine (ici /var/) de manière relative, la commande à entrer est `cd ..`.

3. Pour revenir au dossier personnel, il faut entrer la commande `cd /home/User`.

4. Dans le cas où l'on veut retourner au dossier précédent sans utiliser de chemin, il faut utiliser la commande `cd -`.

5. Si l'on veut accéder au dossier /root/, sois celui du super-utilisateur, le terminal nous indique que nous n'avons pas la permission d'accéder à ce répertoire.

6. Dans le cas où l'on veut accéder au répertoire root, par l'intermédiaire de la commande `sudo`, cela ne marche pas non plus, car la commande sudo ne s'applique qu'aux programmes, et non pas aux commandes internes.

7. Afin de créer une arborescence, on utilise la commande `mkdir` pour créer des répertoires, et la commande `touch` pour créer des fichiers.

```
~
│
└─── Dossier1
|	 │ Fichier1
│
└─── Dossier2
	└─── Dossier2.1
	└─── Dossier2.2
		│ Fichier2
		│ Fichier3
```


8. Avec la commande `rm` on peut supprimer le Fichier1, mais pas le Dossier1 car celui ci est un répertoire. 
9. Pour le supprimer il faut utiliser une autre commande, `rmdir`.

10. La commande ne fonctionne pas, car le Dossier2 n'est pas vide.
11. Pour supprimer un dossier et son contenu directement, il faut utiliser la commande `rm -r`.


### Commandes MinImportancePhotonSearchDistance

1. Pour afficher l'heure, il faut entrer la commande `date`. `time` permet d'afficher le temps passé dans certains dossiers, et permet de voir les ressources utilisées.

2. `ls` permet d'afficher la liste des fichiers du répertoire actuel. `la` permet la même chose de manière plus avancée : il affiche les fichier "cachés".

3. A l'aide de la commande `which ls`, on peut voir que le programme se trouve dans le répertoire /usr/bin/ls.

4. La commande `ll` permet d'afficher le contenu du répertoire avec le plus de détail possible, permissions, créateur, taille du fichier, date de création, nom du fichier. Grâce à la commande `alias`.

5. Pour afficher les fichiers contenus dans le répertoire /bin/, il faut exécuter la commande `ls /bin/`.

6. La commande `ls ..` permet d'afficher les fichiers contenus dans le répertoire au dessus de celui actuel dans l'arborescence.

7. La commande `pwd` permet d'afficher le chemin complet, de la racine, jusqu'au répertoire actuel.

8. Lorsqu'on l'exécute 2 fois, la commande `echo 'bip' > plop` crée un fichier plop dans lequel on trouve 'bip' écrit une fois. 
9. Si l'on exécute ensuite 2 fois la commande `echo 'bip' >> plop` à rajouté au fichier plop 2 fois l'entrée 'bip', à chaque fois à la fin du fichier. 

10. La commande `sleep 10 | echo 'toto'` interprète 2 commandes différentes, mais les exécute de manière simultanée. D'une part le terminal retourne 'toto', mais d'autre part on doit attendre 10 secondes avant de pouvoir entrer une nouvelle commande (sauf si on l'interrompt).

11. La commande `file` doit prendre un fichier en argument, et retourne simplement le type du fichier.

12. On crée et édite le fichier original via la commande `nano`, après avoir créé le lien physique puis modifié le fichier original, on observe que la modification s'est répliqué sur le fichier lié. Cependant, si l'on supprime le fichier original, le fichier lié subsiste.

13. Après avoir créé un lien symbolique, si l'on modifie le fichier lien_phy, le fichier lié est également modifié. Cela marche également dans le sens inverse. Si l'on supprime l'un des deux fichiers, l'autre existe toujours, mais son contenu est vide.    

14. A l'aide du raccourci clavier ctrl + c, cela interrompt le processus. Pour le stopper, il faut utiliser ctrl + s, pour le reprendre, ctrl + q.

15. Pour afficher les 5 premières lignes du fichier, il faut entrer la commande `head -n 5 /var/log/syslog`. Pour les 15 dernières lignes, ça sera `tail -n 15 /var/log/syslog`. Pour les lignes 10 à 20 la commande sera : `head -n 10 /var/log/syslog | tail -n 20`.

16. La commande `dmesg | less` permet d'afficher les derniers messages retournés par le kernel sur le fonctionnement des différents drivers.

17. Le fichier /etc/passwd contient de nombreuses informations sur les différents utilisateurs enregistrés. Pour afficher le manuel, il faut entrer la commande `man /etc/passwd`

18. Ne sais pas

19. La commande `wc -l /etc/passwd` nous permet de voir qu'il y a au total 34 utilisateurs sur la machine (connectés ou non).

20. Ne sais pas

21. L'exécution de la commande `sudo find / -iname 'passwd'` permet de répertorier tous les fichiers (avec leur chemin entier) contenant 'passwd' dans leur nom.

22. Pour rediriger le résultat de la commande, il faut y ajouter les redirections adéquates. Ainsi, la commande finale sera celle ci : `sudo find / -iname 'passwd' > list_passwd_files.txt 2>/dev/null`.

23. Ne sais pas

24. Grâce à la commande `locate history.log`, on trouve le chemin du fichier : /var/log/apt/history.log.bind

25. Après avoir créé un fichier dans le répertoire personnel, la commande locate est incapable de le détecter.