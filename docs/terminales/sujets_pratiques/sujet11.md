# Sujet NSI 2022 - Sujet 11

## Exercice 1

Écrire une fonction `recherche` qui prend en paramètres un tableau `tab` de nombres entiers triés par ordre croissant et un nombre entier `n`, et qui effectue une recherche dichotomique du nombre entier `n` dans le tableau non vide `tab`.

Cette fonction doit renvoyer un indice correspondant au nombre cherché s’il est dans le tableau, $-1$ sinon.

Exemples:

```python
>>> recherche([2, 3, 4, 5, 6], 5)
3
>>> recherche([2, 3, 4, 6, 7], 5)
-1
```

??? note "Correction"

    ```python
    def recherche(tab, n):
        debut = 0
        fin = len(tab) - 1
        while debut < fin:
            milieu = (debut + fin) // 2
            valeur_centrale = tab[milieu]
            if valeur_centrale == n:
                return milieu
            elif valeur_centrale >n:
                fin = milieu - 1
            else:
                debut = milieu + 1
        return -1

    assert recherche([2, 3, 4, 5, 6], 5) == 3
    assert recherche([2, 3, 4, 6, 7], 5) == -1
    ```

## Exercice 2

Le codage de César transforme un message en changeant chaque lettre en la décalant dans l’alphabet.

Par exemple, avec un décalage de 3, le A se transforme en D, le B en E, ..., le X en A, le Y en B et le Z en C. Les autres caractères (‘!’,’ ?’…) ne sont pas codés.

La fonction `position_alphabet` ci-dessous prend en paramètre un caractère `lettre` et renvoie la position de `lettre` dans la chaîne de caractères `ALPHABET` s’il s’y trouve et `-1` sinon.

La fonction `cesar` prend en paramètre une chaîne de caractères `message` et un nombre entier `decalage` et renvoie le nouveau message codé avec le codage de César utilisant le décalage `decalage`.

```python
ALPHABET='ABCDEFGHIJKLMNOPQRSTUVWXYZ'

def position_alphabet(lettre):
    return ALPHABET.find(lettre)

def cesar(message, decalage):
    resultat = ''
    for ... in message :
        if lettre in ALPHABET :
            indice = ( ... )%26
            resultat = resultat + ALPHABET[indice]
        else:
            resultat = ...
    return resultat
```

Compléter la fonction `cesar`.

Exemples :

```python
>>> cesar('BONJOUR A TOUS. VIVE LA MATIERE NSI !',4)
'FSRNSYV E XSYW. ZMZI PE QEXMIVI RWM !'
>>> cesar('GTSOTZW F YTZX. ANAJ QF RFYNJWJ SXN !',-5)
'BONJOUR A TOUS. VIVE LA MATIERE NSI !'
```

??? note "Correction"

    ```python
    ALPHABET='ABCDEFGHIJKLMNOPQRSTUVWXYZ'

    def position_alphabet(lettre):
        return ALPHABET.find(lettre)

    def cesar(message, decalage):
        resultat = ''
        for lettre in message :
            if lettre in ALPHABET :
                indice = ( position_alphabet(lettre) + decalage)%26
                resultat = resultat + ALPHABET[indice]
            else:
                resultat = resultat + lettre
        return resultat

    assert cesar('BONJOUR A TOUS. VIVE LA MATIERE NSI !',4) == 'FSRNSYV E XSYW. ZMZI PE QEXMIVI RWM !'
    assert cesar('GTSOTZW F YTZX. ANAJ QF RFYNJWJ SXN !',-5) == 'BONJOUR A TOUS. VIVE LA MATIERE NSI !'
    ```
