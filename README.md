# TP Neo4j: Prise en main, manipulation et requêtage

L'objectif de ce TP est de mettre en pratique le requêtage via une algèbre en utilisant Cypher dans la base de donnée Neo4j.

Dans une **première partie**, on *installera Neo4j* et on test si cette dernière est bien installé. 

Dans une **seconde partie**, on va créer des nœuds, relations et on chargera les données. 

Dans la **troisième partie** on effectuera des requêtes pour répondre aux différentes questions.

> Pensez à rédiger un compte-rendu au format Markdown dans lequel vous
> indiquerez vos remarques ainsi que les différentes requêtes que vous aurez
> exécuté.


## 1. Installation 

Téléchargez Neo4j Desktop (installable disponible [en cliquant ici](https://bul.univ-lyon2.fr/index.php/s/m6f1w1KQUdLv0wx/download)), suivez les instructions (au pire des cas, dérangez le prof avec une ou deux questions au maximum) et prenez en main Neo4j.

<!-- ⚠️ N'oubliez pas de copier la clé d'activation "*Neo4j Desktop Activation Key*", vous en aurez besoin pour la suite au moment de l'installation.-->

Installez Neo4j depuis le fichier téléchargé en suivant les instructions par défaut. Une fois l'installation terminée, vous ouvrez la base de données Neo4j, si cette dernière ne se lance pas automatiquement.



## 2. Prise en main 

Créer une instance que vous nommerez "R501" (Remplir le formulaire, et ne pas oublier d'introduire un mot de passe sur 8 caractères). Ensuite, vous créez une base de données locale "GoT".

### 2.1 Modélisation en graphe 
Un beau matin, vous vous réveillez en __Westeros__, le monde de Game Of Thrones, sans aucune connaissance historique. Afin d'y survivre, il va falloir intégrer les informations du royaume. Nous allons pour cela utiliser une base de données orientée graphe Neo4J.


Avant toute chose! Vous allez devoir vous ajouter au monde que vous venez de rejoindre.

1. Créer un nouveau personnage avec votre nom et prénom.

<details>
<summary>Indication si vous en avez vraiment vraiment besoin</summary> (Cliquez sur la flèche pour voir l'indice)

> Le label est :personnage. <br>
>{name : 'Eric', nickname : 'Dupont' }

</details>


> (ℹ️)   Il faut apprendre à créer des relations, car le monde de Game Of Thrones est très complexe.

2.  Créez deux personnages et exprimez une relation qui les relie.

> 🪙 Par exemple, un des combats les plus célèbres oppose Oberyn Martell, dit The Viper et Gregor Clegane, dit The Mountain. Gregor Clegane tue Oberyn Martell en duel.

<details>
<summary>Idice 1</summary>

> Créer d'abord les deux nœuds avec l'instruction CREATE.<br>
```
CREATE(gregor:personnage { name : '...', nickname : '...' }) <br>
CREATE(oberyn:...) <br>
```

</details>



<details>
<summary>Idice 2</summary>

Créer une relation de type « :TUE » entre les deux nœuds avec comme attribut : « type : 'duel' »

</details>


3. Affichez l'ensemble des nœuds présents dans votre base de données.


Nous pouvons à présent alimenter notre base d'un ensemble de connaissance dont nous disposons. Pour cela copier et exécuter le code Cypher présent dans ce fichier [Cliquez ici](creationBdGot.cypher).




4. Dans ce qui suit, modélisez en Neo4j les nœuds et relations décrites ci-dessous:

    - Rickard Stark (décédé), ancien Gouverneur du Nord et Seigneur de Winterfell
    - Son fils ainé, Brandon Stark (décédé)
    - Son deuxième fils, Eddard Stark Gouverneur du Nord exécuté par Joffrey Baratheon (décédé)
    - Sa femme, Lady Catelyn Stark (décédé)
        - leur fils ainé Robb Stark (décédé)
        - leur fille ainée Sansa Stark
        - leur fille cadette Arya Stark
        - leur second fils Bran Stark
        - leur dernier fils Rickon Stark (décédé)
    - Sa fille, Lyanna Stark (décédée)
        - Son fils, Jon Snow (ressuscité), Lord commandant de la Garde de nuit

    - Son fils cadet, Benjen Stark, patrouilleur de la Garde de nuit

### 2.2 Verification des ajouts   

1. Affichez le graphe en entier
2. Affichez les personnages féminins (dans le script initial il faudrait faire des set pour rajouter le genre sur les personnages)
3. Affichez les personnages qui ne sont pas décédés

### 3 Requêtes sur Movie DBMS
Dans cette partie, vous devez créer une nouvelle base de données qu'on nomme ``Movies``présente dans **Neo4j**.

 <!-- en utilisant ce [script](https://moodle.univ-lyon2.fr/mod/resource/view.php?id=432682). -->

Puis, répondre aux requêtes suivantes : 

1. Affichez tous les acteurs (```nom```) qui ont joué (```"ACTED_IN"```) dans des films (titre du
film).
2. Affichez tous les films dans lesquels ```Tom Cruise``` a joué.
3. Listez les acteurs et actrices qui ont joué dans ```Stand By Me```.
4. Affichez les acteurs qui ont joué dans au moins 4 films.
5. Affichez combien de films ont été dirigés par ```Tom Hanks```.
6. Affichez les films sortis après 2002.
7. Affichez la liste des acteurs (qui ont joué dans un film) dont leurs années de naissance
(```born```) n'ont pas été renseignées.
8. Rajoutez l'année de naissance de l'actrice ```Naomie Harris``` qui est née en 1976.
9. Affichez la liste d'acteur, leur âge actuel, le titre du film dans lequel l'acteur a joué, l'année
de sortie du film et l'âge de l'acteur quand le film est sorti.
10. Qui ont dirigé le film ```The Matrix```, affichez les noms des personnes et le type de relation.
11. Listez les personnes qui ont au minimum 3 types de relation avec un film.
