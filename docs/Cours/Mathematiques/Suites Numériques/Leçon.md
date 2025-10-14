# Notion de suite numérique

## Définir une suite

Définition : Une suite numériques ($u_n$) un nombre réel noté $u_n$.

!!! info "Définition"
    Une suite numériques ($u_n$) un nombre réel noté $u_n$.

Exemple :

* On considère la liste ordinnée des nombres pairs rangés dans l'ordre croisant :
    * 0 ; 2 ; 4 ; 6. On note $u_n$ l'ensemble des "éléments" de cette suite de nombres, tels que :
        * $u_0=0$, $u_1=2$, $u_2=4$, $u_3=6$ ...

Remarques :

* Le premier terme de la suite est appelée *terme initial*. C'est le plus soucent le premier terme de rang 0, noté $u_0$, ou le terme de rang 1, noté $u_1$.
* BLABLA

## Formule les plus importantes :

### I. Suite Aritmétique
#### Définition 
$$
u_{n+1}=u_n+r
$$

#### Formule explicite
$$
u_n=u_p+(n-p)r
$$

Raison $r = u_{n+1}-u_n$
#### Somme de n terme
$$
S_n = n \frac{u_1+u_n}{2}
$$

### II. Suite Géométrique
#### Définition 
$$
u_{n+1}=q \times u_n
$$

#### Formule explicite
$$
u_n=u_p \times q^{n-p}
$$

Raison $q = \frac{u_{u+1}}{u_n}$
#### Somme de n terme
$$
S_n = u_1 \times \frac{1-q^n}{1-q}
$$
