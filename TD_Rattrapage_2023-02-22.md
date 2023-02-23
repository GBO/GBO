# TD Rattrapage - 22/02/2023

### Attendu en fin de session :
* Une application console C++ dans un unique fichier .cpp dont le nom commence par **votre nom de famille** et contenant les sources des différents exercices.

### Critères de notation :
* 4 points par exercice + 2 points à la discrétion du correcteur
* Lisibilité du code (commentaires dans le code, sortie explicite, …).
* Respect des exigences *Attendu en fin de session*.
* Respect des exigences de chaque exercice.
* Résultat attendu prouvé par un test : on instancie une ou plusieurs fois la classe pour la manipuler et prouver qu'elle fonctionne comme convenu.

### Conseils :
* Lisez bien les intitulés : le respect des exigences est important.
* Ne restez pas bloqué sur un problème, essayez de contourner (retourner une valeur statique pour un calcul en respectant les consignes par exemple).
* Utilisez l’aide à votre disposition : en bas de cette page, et surtout Internet ;)



# Exercice 1 - Opération
### Exigences :
Créer une classe `Operation` représentant une opération mathematique simple. La classe possède :
* Un attribut `nom` : le nom de la matière étudiée.
* Les accesseurs (getter) pour l'attribut.
* Un constructuer imposant la définition d'un `nom`.
* Une méthode `virtual` `executer` prenant 2 paramètres représentant les opérandes de l'opération.
    * La méthode n'a pas d'implémentation dans cette classe générique (idéalement elle est abstraite).


# Exercice 2 - Addition
### Exigences :
Créer une classe `OperationAddition` héritant d'`Operation` et implémentant l'addition :
* La classe spécialise le `nom` de l'opération avec la valeur `"Addition"`.
* La classe implémente l'addition dans la méthode `executer` : la méthode retourne donc le résultat de l'addition des 2 opérandes en paramètre.

### Tests :
* Instancier une `OperationAddition`.
* Effectuer plusieurs additions en invoquant la methode `executer` avec des opérandes différentes.


# Exercice 3 - Calculatrice
### Exigences :
Créer une classe `Calcultarive` définissant une calculatrice permettant d'effectuer des `Operations`. La classe possède : 
* Un liste d'`Operation` possible (un `vector` de `Operation` par exemple).
* Une méthode exécuter qui fait exécuter une calculatrice :
  1. On demande à l'utilisateur de saisir une première valeur (la première opérande).
  2. On demande ensuite à l'utilisateur de choisir une `Operation` en lui listant les `Operation` que connait la `Calculatrice` (de son `vector` d'`Operation` par exemple).
  3. On demande ensuite à l'utilisateur de saisir une deuxième vlauer (la deuxième opérande).
  4. On affiche le résultat de l'`Operation` sur les 2 opérandes.
  5. Le résultat devient la première opérande et on recommence à l'étape 2.

### Tests :
* Instancier une `Calculatrice`.
* Lui ajouter l'`OperationAddition` créée à l'exercice 2.
* `executer` la `Calculatrice`.


# Exercice 4 - Les autres opérations
### Exigences :
Implémenter 3 nouvelles `Operation` : `OperationSoustraction`, `OperationMultiplication` et `OperationDivision`.

### Tests :
* Ajouter les 3 nouvelles `Operation` à la `Calculatrice` instanciée à l'exercice 3.
* Constater que la `Calculatrice` permet maintenant de faire les 3 nouvelles opérations.



# Aides :
* [Délaration d'une classe](https://en.cppreference.com/w/cpp/language/class) avec le mot-clé [`class`](https://en.cppreference.com/w/cpp/keyword/class)
* Les spécificateurs d'accès : [`private`, `protected` et `public`](https://en.cppreference.com/w/cpp/language/access)
* [Le constructeur](https://en.cppreference.com/w/cpp/language/constructor)
* [L'instanciation d'objet](https://en.cppreference.com/w/cpp/language/object)
* [Les opérateurs d'accès aux membres d'une classe : `.` et `->`](https://en.cppreference.com/w/cpp/language/operator_member_access#Built-in_member_access_operators)
* La création d'instance avec [`new`](https://en.cppreference.com/w/cpp/language/new)
* La libération de mémoire avec [`delete`](https://en.cppreference.com/w/cpp/language/delete)
* La [dérivation de classe](https://en.cppreference.com/w/cpp/language/derived_class) : `class Enfant : public Parent { ... };`.
* Le polymorphisme avec [`virtual`](https://en.cppreference.com/w/cpp/language/virtual)
* Les [classes abstraites](https://en.cppreference.com/w/cpp/language/abstract_class) 
* Les [`vector`](https://en.cppreference.com/w/cpp/container/vector)


# Exemple de rendu nommé NOMDEFAMILLE.cpp
```c++
// Inclusion des librairies
#include <iostream>
#include <vector>

// Utilisation du namespace std pour s'économiser quelques caractères plus bas.
// Sans cette instruction, il faudrait toujours utiliser `std::cout` au lieu de `cout`
using namespace std;

/** Un petit bloc de commentaire pour passer quelques infos sur l'exercice
 * Ma Classe est cool
 */
class MaClasseDemande {
private:
  int unMembrePrive;

public:
  /** Un bloc de commentaire expliquant ma methode */
  int uneMethodePublique(string avecUnParametre) {
    // Et son implémentation
  }
};

// Un main dans lequel j'invoque quelques fonctions d'exercice...
int main(int argc, char **argv)
{
  cout << "TD Noté de Ghislain BOUCHET - EPSI - 19/10/2021" << endl;

  MaClasseDemande monInstance = new MaClasseDemande;
  monInstance->uneMethodePublique("son paramètre");

  return 0;
}
```
