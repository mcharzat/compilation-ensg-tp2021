# compilation-ensg-devoir-2021

**NB: Pour toute reponse nécéssitant un schema, vous pouvez utiliser sketchpad (https://sketch.io/sketchpad/), télécharger le résultat au format pdf et me le joindre à votre réponse.**


1 - Quel formalisme doit on aux auteurs **John Backus** et **Peter Naurr** ? Et à quoi sert-il ?

Il s'agit du formalisme BNF dit forme de Backus-Naurr. Ce formalisme sert à cadrer ou interpréter syntaxiquement un
langage.


2 - Donnez la grammaire capable de lire la syntaxe bien parenthésée suivante :
`[[{}([{}]){{}}]]`

E -> C | A | P | €
C -> [E]
A -> {E}
P -> (E)


3 - Donnez la grammaire (lexer et parser) capable de comprendre du XML
exemple :
``` xml
<xml>
  <persons>
    <person firstName="Ada" lastName="Lovelace" />
    <person firstName="Grace" lastName="Hopper"/>
  </persons>
</xml>
```

balise = '<' {'/'} [a-z] {[a-z] {' ' keyValue} } {'/'} '>'
keyValue = attribut '=' value
value = '"' [a-zA-Z] {[a-zA-Z]} '"'
attribut =  [a-z] {[a-zA-Z]}


4 - Transformez la grammaire suivante afin de résoudre le problème de la recursivité à gauche. **(2 points)**
``` go
E -> E '*' E | E '/' E | '-' E | n | €
```

E -> nF | '-' nF | €
F -> '*' E | '/' E


5 - La grammaire `E -> E '||' E | E | €` est-elle acceptable pour un parseur **LR** ? Pourquoi ?

Elle n'est pas acceptable car on ne pourra pas réduire. Il y a une boucle infini E -> E.



6 - Cette grammaire est inexact, pourquoi ?
``` go
A -> M '||' A
M -> E '&&' M
E -> '!' A | n
```

Parce que A et M n'ont pas de règle d'arrêt.


7 - Dessinez l'AST correspondant à la formule suivante, avec le respect de la précédence des opérateurs : 
  - `(1 + 1) * 2 * (3 + 4) - 5`

		(-)
	       /   \
	     (*)    (5)
	    /   \
	 (*)     (+)
	/  \    /  \
      (+) (2) (3)  (4)
     /  \
   (1)  (1)


8 - A partir du premier AST, schematisez ce qu'il se passe dans la pile d'exécution lors de sa resolution
(vous devez dessiner une pile pour chaque étape en précisant les operations effectuées si nécéssaire) **(2 points)**

[]
[1] push 1
[1 1] push 1
[2] add
[2 2] push 2
[4] mult
[4 3] push 3
[4 3 4] push 4
[4 7] add
[28] multi
[28 5] push 5
[23] substrack


9 - Dans une machine à pile, à l'aide des operations PUSH n, ADD et MULT écrivez un pseudo programme machine qui correspond à la formule de la question 7 : 

Voir question 8.


10 - Donnez deux raisons pour lesquelles l'interpreteur du premier `Basic` n'est pas performant. Quel grammaire aurait il été impossible d'implémenter avec ce type de parseur ?

Dans les premières versions de Basic, l'interpreteur exécutait le code à mesure qu'il l'analyser. Ce qui implique une complexité
d'optimisation de mémoire. 
Il aurait été impossible d'implémenter un LR puisque LR a besoin de toute l'expression pour créer la grammaire.

11 - Quel est la complexité d'un algorithme **`ll(*)`** ? Et comment l'optimiser (citez le nom de la technique et la decrire) ?

L'algorithme ll(*) a une complexité exponenetielle. Il faut donc utiliser un Packrat pour effectuer un stockage en cache des différents choix, ce qui permet de ne les évaluer qu'une seule fois.


12 - Que veut dire **AOP** et décrire le paradigme

AOP correspond à Aspect Oriented Programming. Il tend à séparer les différentes responsabilités

13 - Quel est la différence entre un **typage implicite** et un **typage dynamique**. Peut-on rencontrer les deux concepts dans le même langage ?

Un typage implicite est résolu par l'analyse alors qu'un typage dynamique est résolu pendant l'exécution. 
On ne peut donc pas les rencontrer dans un même langage.

14 - Donnez 5 exemples de mots possibles à la grammaire suivante : 
``` go
0* 1 ( 2? 1+ 0 )+
```

* 000110
* 121110
* 01210
* 1211110210211021111110110
* 00000111110

15 - La grammaire E -> E + n | n accept elle les formules suivantes :
- [Oui] 1 + 1 
- [Non] + 1
- [Non] 1 +
- [Non] +
- [Non] vide
- [Oui] 2 + 1 + 1
- [Oui] 7
- [Non] e + 1
- [Non] a + a + a

16 - Transformez les formules arithmétiques suivante en **Lisp** ex. `2 + 3 donne ( + 2 3 )` : **(2 points)**
``` go
5 + 7 * 2 * ( 1 + 1 ) / 4
1 + 2 * 7 + ( 2 * 2 ) + 7
```

( + 5 ( * 7 ( * 2 ( / ( + 1 1 ) 4 ) ) ) ) )
( + 1 ( + ( + ( * 2 7 ) ( * 2 2 ) ) 7 ) )  


17 - Comme le ferait un analyseur sémantique, optimisez le programme suivant :
``` go
func main (arg) {
	var a int = arg
	var b int = 7
	var c int = a + b
	var d = c

	if d - a < 5 {
		fmt.Println("La réponse à la question suivante est Algoid, bien entendu ! Mais ne nous distrayons pas. :-)")
	} else {
		fmt.Println("Le résultat de " + a + " + " + b + " est " + d)
	}
}
```

``` go
func main (arg) {
	var d = arg + 7

	if d - arg < 5 {
		fmt.Println("La réponse à la question suivante est Algoid, bien entendu ! Mais ne nous distrayons pas. :-)")
	} else {
		fmt.Println("Le résultat de " + arg + " + " + d - arg + " est " + d)
	}
}
```

Bonus - Quel est le meilleur langage au monde ? (20 points)

Algoid ? **oui** / **oui**

Nan.... J'rigole :-)
Bonne continuation à tous :-)
