# compilation-ensg-devoir-2019

*NB: Pour toute reponse nécéssitant un schema, vous pouvez utiliser sketchpad (https://sketch.io/sketchpad/) télécharger le résultat au format pdf et me le joindre à votre réponse.*


1 - Quel formalisme doit on aux auteurs John Backus et Peter Naurr ? Et à quoi sert-il ?
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________

2 - Donnez la grammaire capable de lire la syntaxe bien parenthésée suivante :
`[[{}([{}]){{}}]]`
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________

3 - Donnez la grammaire (lexer et parser) capable de lire du XML
exemple :
``` xml
<xml>
  <persons>
    <person firstName="Ada" lastName="Lovelace" />
    <person firstName="Grace" lastName="Hopper"
  </persons>
</xml>
```
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________


4 - Transformez la grammaire suivante afin de résoudre le problème de la recursivité à gauche. **(2 points)**
``` go
E -> E '*' E | E '/' E | '-' E | n | €
```
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________


5 - La grammaire `E -> E '||' E | E | €` est-elle acceptable pour un parseur **LR** ? Pourquoi ?
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________



6 - Cette grammaire est inexact, pourquoi ?
``` go
A -> M '||' A
M -> E '&&' M
E -> '!' A | n
```
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________


7 - Dessinez l'AST correspondant à la formule suivante, avec le respect de la précédence des opérateurs : 
  - `(1 + 1) * 2 * (3 + 4) - 5`

___________________________________________________________________________________________________________________

8 - A partir du premier AST, schematisez ce qu'il se passe dans la pile d'exécution lors de sa resolution
(vous devez dessiner une pile pour chaque étape en précisant les operations effectuées si nécéssaire) **(2 points)**
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________


9 - Dans une machine à pile, à l'aide des operations PUSH n, ADD et MULT écrivez un pseudo programme machine qui correspond à la formule de la question 7 : 
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________


10 - Donnez deux raison pour lesquelles l'interpreteur du premier `Basic` n'est pas performants. Quels grammaire aurait il été impossible d'implémenter avec ce type de parseur ?
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________


11 - Quel est la complexité d'un algorithme **`ll(*)`** ? Et comment l'optimiser (citez le nom de la technique et la decrire) ?
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________

12 - Que veut dire **FRP** et décrir le paradigme
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________

13 - Quel est la différence entre un **typage implicite** et un **typage dynamique**. Peut-on rencontrer les deux concepts dans le même langage ?
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________

14 - Donnez 5 exemples de mots possibles à la grammaire suivante : 
``` go
0* 1 ( 2? 1+ 0 )+
```
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________

15 - La grammaire E -> E + n | n accept elle les formules suivantes :
- [ ] 1 + 1 + 1
- [ ] + 1
- [ ] 1 +
- [ ] +
- [ ] vide
- [ ] 2 + 1 + 1
- [ ] 7
- [ ] e + 1
- [ ] a + a + a

16 - Transformez les formules arithmétiques suivante en **Lisp** ex. `2 + 3 donne ( + 2 3 )` : **(2 points)**
``` go
5 + 7 * 2 * ( 1 + 1 ) / 4
1 + 2 * 7 + ( 2 * 2 ) + 7
```
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________

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
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________
___________________________________________________________________________________________________________________


Bonus - Quel est le meilleur langage au monde ? (20 points)

Algoid ? **oui** / **oui**

Nan.... J'rigole :-)
Bonne continuation à tous :-)
