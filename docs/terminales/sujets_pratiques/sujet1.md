# Sujet 1

## Exercice 1
Écrire une fonction `recherche` qui prend en paramètres `caractere`, un caractère, et `mot`, une chaîne de caractères, 
et qui renvoie le nombre d’occurrences de `caractere` dans `mot`, 
c’est-à-dire le nombre de fois où `caractere` apparaît dans `mot`.

Exemples :

```python
>>> recherche('e', "sciences")
2
>>> recherche('i',"mississippi")
4
>>> recherche('a',"mississippi")
0
```

## Exercice 2

On s’intéresse à un algorithme récursif qui permet de rendre la monnaie 
à partir d’une liste donnée de valeurs de pièces et de billets - le système monétaire est
donné sous forme d’une liste `pieces=[100, 50, 20, 10, 5, 2, 1]` - (on supposera qu’il n’y a pas de limitation quant 
à leur nombre), on cherche à donner la liste de pièces à rendre pour une somme donnée en argument.

Compléter le code Python ci-dessous de la fonction `rendu_glouton` qui implémente cet 
algorithme et renvoie la liste des pièces à rendre.

```python
Pieces = [100,50,20,10,5,2,1]
def rendu_glouton(arendre, solution=[], i=0):
       if arendre == 0:
       return ...
    p = pieces[i]
    if p <= ... :
        solution.append(...)
        return rendu_glouton(arendre - p, solution, i)
    else :
        return rendu_glouton(arendre, solution, ...)
```
