# Leçon
En Java, le programme minimal (qui ne fait rien) est :

```java
class Main {
   public static void main(String[] args) {
   }
}
```

Nous allons compléter ce programme minimal pour qu'il fasse quelque chose.   
En Java, tout programme s'organise en classes, et en blocs à l'intérieur des classes. Pour nos vérifications, nous testons la classe nommée _Main_. Quand on teste une classe, c'est le bloc nommé _main_ à l'intérieur qui est exécuté. 

Pour afficher du texte, on écrit `System.out.println` puis, entre parenthèses, le texte à afficher, entre guillemets. Ainsi, pour afficher le mot « Bonjour », on écrira le code suivant :

```java
class Main {
   public static void main(String[] args) {
      System.out.println("Bonjour");
   }
}
```

Par la suite, nous indiquerons le résultat d'un programme avec un trait rouge et une petite flèche. Par exemple, pour le programme qui affiche le texte « Bonjour » :

```java
class Main {
   public static void main(String[] args) {
      System.out.println("Bonjour");
   }
}

# Bonjour
```

Ce résultat est appelé la _sortie_ du programme : c'est ce qui ressort de son exécution.

**Vous ne devez pas écrire la flèche « ↳ » ou le texte « Bonjour » directement dans votre programme !**

Pour afficher plusieurs lignes de texte, il faut écrire des instructions d'affichage successives terminées par un point-virgule (une par ligne) :

```java
class Main {
   public static void main(String[] args) {
      System.out.println("Bonjour !");
      System.out.println("Comment vas-tu ?");
   }
}

#Bonjour !
#Comment vas-tu ?

```
Quand on écrit un programme informatique, il faut être très rigoureux car un simple caractère mal placé peut perturber l'ordinateur du robot. Si le format de votre code n'est pas bon, il ne va pas aller plus loin et va simplement vous indiquer que vous avez commis une erreur.

Quand ça arrive, il faut d'abord tenter de comprendre le message d'erreur et ensuite relire attentivement la zone de code concernée, en particulier pour s'assurer qu'il ne manque pas de symbole tel qu'une parenthèse ou un guillemet.

Voici quelques exemples de messages d'erreur.
Attention aux points-virgules !

Si on oublie le point-virgule, cela produit une erreur :

```java
class Main {
   public static void main(String[] args) {
      System.out.println("Bonjour")
   }
}

line 3: error: Syntax error, insert ";" to complete BlockStatements

```
Si on traduit ce texte, il nous dit justement qu'on a oublié le « ; ».
Attention aux parenthèses !

Si on oublie une parenthèse, cela produit une des erreurs suivantes : 

```java
class Main {
   public static void main(String[] args) {
      System.out.println "Bonjour");
   }
}

error: Syntax error on token "println", ( expected after this token
```

```java
class Main {
   public static void main(String[] args) {
      System.out.println "Bonjour";
   }
}
↳

Syntax error on token "println", AssignmentOperator expected after this token
```
Attention aux guillemets !

Si on ne place pas correctement les guillemets, cela produit une des erreurs suivantes : 

```java
class Main {
   public static void main(String[] args) {
      System.out.println("Bonjour);
   }
}

error: String literal is not properly closed by a double-quote
```

```java
class Main {
   public static void main(String[] args) {
      System.out.println(Bonjour tout le monde);
   }
}

error: Syntax error, insert ")" to complete MethodInvocation
error: Syntax error, insert ";" to complete BlockStatements
error: Syntax error on token "le", ( expected
```
Conclusion

Il faut être précis et ne rien oublier. Si l'on rencontre une erreur, on pensera à bien tout vérifier. Les messages décrivent très souvent la source exacte du problème, en anglais : il faut les lire et essayer de comprendre leur signification.

Un message d'erreur vous donnera aussi toujours le numéro de la ligne qui a causé le souci. Ce numéro n'est pas toujours exact : l'ordinateur peut n'être dérangé qu'après votre erreur. Il vous faudra donc souvent regarder avant l'emplacement indiqué. 

Si on oublie la ligne qui fournit les instructions pour bouger le robot, comme dans le programme suivant : 

```java
class Main {
   public static void main(String[] args) {
      haut();
      droite();
      bas();
      gauche();
   }
}

line 3: error: The method haut() is undefined for the type Main
      haut();
      ^^^^
line 4: error: The method droite() is undefined for the type Main
      droite();
      ^^^^^^
line 5: error: The method bas() is undefined for the type Main
      bas();
      ^^^
line 6: error: The method gauche() is undefined for the type Main
      gauche();
      ^^^^^^
```
Chaque erreur indique que la fonction à la ligne indiquée est inconnue.

Si on obtient des erreurs de ce genre, on pensera donc à vérifier que l'on a bien écrit la ligne donnant accès aux fonctions du robot. 