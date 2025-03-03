# MicroShell-Rev

# Question d'examen

Cet examen comporte 1 question, microshell :

- [Microshell.c](https://github.com/pasqualerossi/42-School-Exam-Rank-04/blob/main/microshell.c)

si vous pouvez rendre ce code plus court, mais lisible, faites-le-moi savoir !

<br>

## Fichiers exceptés

- microshell.c

## Texte du sujet

Fonctions autorisées :

> malloc, free, write, close, fork, waitpid, signal, kill, exit, chdir, execve, dup, dup2, pipe, strcmp, strncmp


## Le programme
Écrivez un programme qui se comportera comme l'exécution d'une commande shell

- La ligne de commande à exécuter sera les arguments de ce programme

- Le chemin de l'exécutable sera absolu ou relatif mais votre programme ne doit pas construire de chemin (à partir de la variable PATH par exemple)

- Vous devez implémenter "|" et ";" comme dans bash
- nous n'essaierons jamais un "|" immédiatement suivi ou précédé de rien ou de "|" ou ";"

- Votre programme doit implémenter la commande intégrée cd uniquement avec un chemin comme argument (pas de '-' ou sans paramètres)
- si cd a un mauvais numéro d'argument, votre programme doit afficher dans STDERR "erreur : cd : mauvais arguments" suivi d'un '\n'
- si cd échoue, votre programme doit afficher dans STDERR "erreur : cd : impossible de changer le répertoire en path_to_change" suivi d'un '\n' avec path_to_change remplacé par l'argument de cd
- une commande cd ne sera jamais immédiatement suivie ou précédée d'un "|"

- Vous n'avez pas besoin de gérer aucun type de caractères génériques (*, ~ etc...)

- Vous n'avez pas besoin de gérer les variables d'environnement ($BLA ...)

- Si un appel système, à l'exception de execve et chdir, renvoie une erreur, votre programme doit immédiatement afficher "erreur : fatale" dans STDERR suivi d'un '\n' et le programme doit se terminer.

- Si execve a échoué, vous devez imprimer "erreur : impossible d'exécuter executable_that_failed" dans STDERR suivi d'un '\n' avec executable_that_failed remplacé par le chemin de l'exécutable ayant échoué (cela devrait être le premier argument d'execve)

- Votre programme devrait être capable de gérer plus de centaines de "|" même si l'on limite le nombre de "fichiers ouverts" à moins de 30.

## Exemple

par exemple, cela devrait fonctionner :
```
$>./microshell /bin/ls "|" /usr/bin/grep microshell ";" /bin/echo j'adore mon microshell
microcoque
j'adore mon microshell
$>

>./microshell
```

## Astuces
- N'oubliez pas de passer la variable d'environnement à execve
- Ne divulguez pas les descripteurs de fichiers !

## Outil de pratique d'examen

Pratiquez l'examen comme vous le feriez lors du vrai examen - https://github.com/JCluzet/42_EXAM
