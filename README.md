# <img src="https://raw.githubusercontent.com/IUTInfoAix-M2105/Syllabus/master/assets/logo.png" alt="class logo" class="logo"/> Bases de données avancées 

### IUT d’Aix-Marseille – Département Informatique Aix-en-Provence

* **Cours:** [M3106](http://cache.media.enseignementsup-recherche.gouv.fr/file/25/09/7/PPN_INFORMATIQUE_256097.pdf)
* **Responsable:** [Sébastien NEDJAR](mailto:sebastien.nedjar@univ-amu.fr)
* **Enseignants:** [Sébastien NEDJAR](mailto:sebastien.nedjar@univ-amu.fr)
* **Besoin d'aide ?**
    * La page [Piazza de ce cours](https://piazza.com/univ-amu.fr/fall2017/m3106/home).
    * Consulter et/ou créér des [issues](https://github.com/IUTInfoAix-M3106/TutoJdbc/issues).
    * [Email](mailto:sebastien.nedjar@univ-amu.fr) pour une question d'ordre privée, ou pour convenir d'un rendez-vous physique.

# Test de JDBC 2016
Test de JDBC donné en 2016 aux étudiants de l'IUT d'Aix-Marseille

## Partie 2 (Sébastien NEDJAR)
### Documents autorisés


**Remarque** : *Les événements et les situations de ce sujet étant purement fictifs, toute ressemblance avec des événement et des situations existantes ou ayant existé ne saurait être que fortuite.*

Les Startup Week-End, sont la plus grande communauté de hackathons orienté vers l’entrepreneuriat dans le monde. Ils croisent les regards et les talents des participants pour créer des projets innovants aux potentialités extraordinaires. Un Startup Week-end, c’est un moment unique pour favoriser la rencontre des entrepreneurs, makers, designers, développeurs, graphistes, communicants, artistes, scientifiques… qui se retrouvent pour phosphorer, créer, expérimenter et vibrer ensemble.

Un Startup Week-End, c’est 54h pour inventer, concevoir, fabriquer et tester une idée innovante ayant le potentiel de devenir dès le lundi qui suit, l’une des pépites de demain.

Plusieurs de vos collègues courageux (eux au moins)[1], participent chaque année à cet événement pour imaginer l’entreprise de leur rêve. Pour garder la liste de toutes les idées proposées par les pitchers, ils ont besoin que vous écriviez la couche de persistance de la base de données qu’ils ont conçu. Les idées sont proposées autour de thèmes. Pour faciliter la compréhension des participants, chaque thème possède une description textuelle.


IDEE(*ID_IDEE*, LIBELLE, ID_THEME#, ID_STARTUPER#)

THEME (*ID_THEME*, NOM_THEME, DESCRIPTION)

STARTUPER (*ID_STARTUPER*, NOM, PRENOM, ADRESSE, CATEGORIE)

*Par convention, les clefs primaires sont mises en italique et les clefs étrangères sont postfixées
par le symbole #.*

### Questions

1. Écrire la déclaration de la classe `Startuper` en respectant la convention Java Bean (Constructeur par défaut, setter/getter, equals/hashcode). Il ne vous est demandé que la déclaration, en aucun cas le corps des méthodes.
2. Écrire la déclaration de la classe `DAOIdée` qui implémente l’interface `DAO<Idée>` (La définition de l’interface vous est donnée page suivante). Dans un premier temps, vous n’implémentez aucune méthode de cette classe.
3. Implémenter la méthode `findAll()` de la classe `DAOIdée`.
4. Implémenter la méthode `getById(int id)` de la classe `DAOIdée`. Supposez que les classes `DAOTheme` et `DAOStartuper` vous sont fournies.

```java
public interface DAO<T> {
    // Permet la suppression d'un tuple de la base
    public boolean delete(T obj);
    // Permet de récupérer tous les objets d'une table
    public List<T> findAll();
    // Permet de récupérer un objet via son ID
    public T getById(int id);
    // Permet de créer une entrée dans la base de données par rapport
    // à un objet
    public T insert(T obj);
    // Permet de mettre à jour un tuple dans la base à partir d'un
    // objet passé en paramètre
    public boolean update(T obj);
}
```
________________
[1] Le prochain à lieu en mai 2017 à l’arbois, je ne saurai trop vous conseiller de vous inscrire à la newsletter pour ne surtout pas le manquer (http://www.swaixmarseille.fr/).
