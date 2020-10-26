# labo7-financial

- **Durée**: 4 périodes + travail à la maison

## Objectifs pédagogiques
-  Apprendre à gérer un menu pour donner l’accès à différentes fonctions d’un programme.
-  Organiser un programme un peu plus long.

## Cahier des charges
On vous demande de concevoir puis d’écrire un programme qui permet :
- D’effectuer la conversion EUR / CHF,
- D’effectuer la conversion CHF / EUR,
- De calculer les intérêts annuels d’un prêt à taux fixe.

Le choix de l’opération doit être effectué par l’intermédiaire d’un menu.

## Type Boolean
Souvent lorsque l’on fait des tests en programmation, nous avons besoin d’un résultat vrai ou faux.

Il est possible d’utiliser une variable `int` et de l’utiliser avec une valeur `0` ou `1`, mais cela n’est pas très explicite. Depuis C99, en incluant la libraire `stdbool`, il est possible d’utiliser une variable de type `bool` qui peut prendre comme valeurs `true` ou `false`.

```C
#include <stdbool.h>

    void main(void){
        bool var1 = true;
        bool var2 = false;
        
        // Dans ce cas, il ne faut pas écrire var == true car c'est implicite
        if( var1 ) {
        }
    }
```


## Fonctions imposées
### Getion du menu
Le menu doit afficher les options utilisateur suivantes :
- 0 : quitter
- 1 : calcul des intérêts annuels
- 2 : conversion EURO vers CHF
- 3 : conversion CHF vers EURO

La gestion du menu est confiée à la fonction `gestionMenu` dont le prototype imposé est le suivant :

```C  
    int gestionMenu ( void ); 
```

Cette fonction doit :
1.  Afficher le menu,
1.  Demander à l’utilisateur de saisir une valeur numérique,
1.  Contrôler le choix de l’utilisateur,
1.  Si le choix est correct, la fonction se termine et renvoie la valeur numérique du choix,
1.  Si le choix est incorrect, un message d’information doit être affiché puis la fonction reprend au point 1.

Voici *un exemple* de comment implémenter la boucle pour le menu. Modifier le pour que le style corresponde à votre programme.

```C
    bool saisieIncorrecte = false ;
    do {
        // établissement de la condition de maintien dans la boucle
        saisieIncorrecte = ...
    } while ( saisieIncorrecte );
```

### Calcul des intérêts annuels
La première fonctionnalité accessible depuis le menu doit permettre à l’utilisateur de calculer les intérêts
annuels d’un crédit ou d’un placement. Pour cela, le programme demande le montant du capital, puis le
taux d’intérêt en %. Il affiche ensuite le montant annuel des intérêts correspondants. Présentez les résultats
à l’écran sous la forme d’un tableau facilement lisible, affichant le capital, le taux d’intérêt et le montant des
intérêts annuels.

#### Validation
-  Le taux et le capital doivent être > 0

Le prototype de la fonction pour calculer les intérêts est

```C
    void calculInteretsAnnuels ( void );
```

### Conversions
La première de ces deux fonctions doit demander une valeur en EUR à l’utilisateur et doit afficher la valeur
correspondante en CHF. Le taux à utiliser
est de **1.2**.

La deuxième fonction effectue l’opération inverse.

Les prototypes des fonctions sont
```C
    void conversionEuroChf ( void );
    void conversionChfEuro ( void );
```

#### Validation
-  La valeur doit être > 0

### Quitter
Cette option du menu permet de sortir du programme.

## Affichage 
### Interet
Voilà un exemple d'affichage pour les intêrets, le tableau doit s'adapter pour que l'affichage soit correct.

```C
┌─────────┬──────┬─────────┐
│ Capital │ Taux │ Interet │
├─────────┼──────┼─────────┤
│  123.00 │ 0.10 │    0.12 │
└─────────└──────└─────────┘
```

```C
┌─────────────┬───────┬────────────┐
│ Capital     │ Taux  │ Interet    │
├─────────────┼───────┼────────────┤
│ 10000000.00 │ 36.00 │ 3600000.00 │
└─────────────└───────└────────────┘
```

### Conversions
Voici 2 exemples d'affichage pour les conversions
```C
10.00 [CHF] => 8.33 [EUR]
```

```C
Le montant de 100.00 EUR vaut 120.00 CHF
```

## Aides
N’oubliez pas de traiter le scanf en cas de mauvaise saisie. Dans ce laboratoire, l’utilisateur peut entrer n’importe quoi.

Je vous rappelle que scanf retourne le nombre de valeur saisie :
```C
    int nbr = scanf("%d", &val);
```

Il est aussi possible de vider le buffer avec cette commande
```C
    while (getchar() != '\n') {
    }
```


## Liste des livrables

Mettre les fichiers suivant dans une archive `**zip**` (**pénalité pour les archives `rar`**) et la placer sur Cyberlearn
-  Code source
-  Le fichier exécutable
-  Le fichier de test

L’archive doit être déposée dans le répertoire "Labo07" de Cyberlearn (à la date
demandée sur le site INFO1 de Cyberlearn).
