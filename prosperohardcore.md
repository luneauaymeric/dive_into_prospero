# Le coeur de Prospéro


<style type="text/css">

entite{
  background-color: yellow;
}

qualite{
  background-color: pink;
}

marqueur{
  background-color: #33FFF0;
}

epreuve{
  background-color: #4cff33;
}

motoutil{
  background-color:  #ec7063 ;
}

table {
    border-collapse: separate;
    border-spacing: 5px;
  }

td{
    font-size:12pt;
    vertical-align: top;
    padding-left: 1;
    padding-right: 1;
  }

tr:hover {background-color: coral;}

</style>

> « Un espace de représentation : le texte décrit un état de choses, campe un monde, déploie un univers d’êtres et de relations. Un récit : Le texte raconte une histoire, produit une intrigue. Un dialogue : tout texte instaure au moins une relation dialogique. Une argumentation : le texte mobilise des procédés pour convaincre, justifier, défendre ou critiquer, examiner des faits ou des arguments. » {cite:p}`chateauraynaud2003` (p.82-83)

Avant d'être un outil d'exploration de corpus, Prospéro est un langage de description de textes que l'on peut très bien appliquer sans recourir au logiciel. Par exemple, on fait déjà du "Prospéro" si on lit le texte ci-dessous en se demandant quelles sont les *entités*, comment sont-elles *qualifiées*, dans quelles *épreuves* sont-elles engagées, dans quels *mondes* sont-elles prises, s'il y a des *marqueurs*.

> Vendredi prochain, les États membres européens se prononceront probablement dans le cadre de la SCOPAFF sur l'interdiction ou non de trois matières actives présentes dans certains produits phytosanitaires en raison de leur impact éventuel sur la santé des abeilles. Les trois matières actives en question appartiennent à la famille des néonicotinoïdes et sont cruciales pour la culture de la betterave et de la chicorée en Belgique. En cas d'interdiction, la Confédération des Betteraviers Belges (CBB) demande certainement une exception pour ces deux cultures.
>
> Certaines études souligneraient le danger de l'utilisation des néonicotinoïdes sur les cultures qui suivent les betteraves et avec lesquelles les abeilles peuvent potentiellement entrer en contact. D'autres études indiqueraient que ce risque est minime, voire inexistant. Quoiqu'il en soit, certains politiciens se sont prononcés pour une interdiction européenne des néonicotinoïdes.
>
> Leur abandon dans l'enrobage des semences de betteraves sucrières et de chicorées pourrait avoir de graves conséquences pour les betteraviers belges. Les néonicotinoïdes sont actuellement la meilleure protection disponible contre la jaunisse ; une maladie très présente dans nos régions qui peut entraîner plus de 50 % de pertes de récolte en betteraves et en chicorées. Cette perte de revenus viendrait s'ajouter à des conditions de marché déjà difficiles, suite à la suppression des quotas et du prix minimum européens depuis septembre 2017.

Le rôle du logiciel est de rendre possible une telle lecture sur l'ensemble des textes d'un corpus. Pour cela, chaque utilisateur ou utilisatrice hérite d'un jeu de dictionnaires construit au fil des enquêtes passées. Ces dictionnaires sont le coeur du logiciel et leur enrichissement représente certainement l'essentiel du travail avec Prospéro. Dans la pratique, on distingue deux types de dictionnaires :

-   Les dictionnaires de base

-   Les dictionnaires des "concepts"

## Les dictionnaires de base

<table>
<thead>
<tr>
<th>Référent linguistique</th>
<th>Type de base</th>
<th>Exemples</th>
</tr>
</thead>
<tbody>
<tr>
<td>Substantifs</td>
<td>Entités</td>
<td>États membres ; interdiction; matières ; abeilles ; etc.</td>
</tr>
<tr>
<td>Ajectifs</td>
<td>Qualités</td>
<td>européens ; actives</td>
</tr>
<tr>
<td>Adverbes</td>
<td>Marqueurs</td>
<td>probablement ; certainement</td>
</tr>
<tr>
<td>Verbes</td>
<td>Épreuves</td>
<td>prononceront ; appartiennent ; demande</td>
</tr>
<tr>
<td>Articles; prépositions ; pronoms</td>
<td>Mots-outils</td>
<td>les ; sur ; et</td>
</tr>
<tr>
<td></td>
<td>Nombres</td>
<td>135</td>
</tr>
<tr>
<td></td>
<td>Prénoms</td>
<td></td>
</tr>
</tbody>
</table>


Le logiciel Prospéro découpe les textes en énoncés. Une chaîne de caractère est considérée comme un énoncé lorsqu'elle se situe entre deux points. En revanche, les autres signes de ponctuations ("?", "!", "...") ne sont pas utilisés comme élément de délimitation des énoncés. Ensuite, à partir des dictionnaires de base, le logiciel repère au sein de chaque énoncé les entités, les qualités, les marqueurs, les épreuves, les mots-outils, les nombres. Si nous reprenons l'exemple ci-dessus, le premier paragraphe contient trois énoncés :

> Vendredi prochain, <motoutil>les</motoutil> <entite>États membres</entite> <qualite>européens</qualite> se <epreuve>prononceront</epreuve> <marqueur>probablement</marqueur> <motoutil>dans</motoutil> <motoutil>le</motoutil> <entite>cadre</entite> <motoutil>de</motoutil> <motoutil>la</motoutil> SCOPAFF <motoutil>sur</motoutil> l'<entite>interdiction</entite> <motoutil>ou</motoutil> <motoutil>non</motoutil> <motoutil>de</motoutil> trois <entite>matières</entite> <qualite>actives</qualite> présentes <motoutil>dans</motoutil> certains <entite>produits</entite> phytosanitaires <motoutil>en</motoutil> raison <motoutil>de</motoutil> <motoutil>leur</motoutil> <entite>impact</entite> éventuel <motoutil>sur</motoutil> <motoutil>la</motoutil> <entite>santé</entite> <motoutil>des</motoutil> <entite>abeilles</entite>.
>
> Les trois <entite>matières</entite> <qualite>actives</qualite> en question <epreuve>appartiennent</epreuve> à la <entite>famille</entite> des néonicotinoïdes et sont <qualite>cruciales</qualite> pour la <entite>culture</entite> de la <entite>betterave</entite> et de la <entite>chicorée</entite> en <entite>Belgique</entite>.
>
> En cas d'interdiction, la <entite>Confédération</entite> des <entite>Betteraviers</entite> <qualite>Belges</qualite> (CBB) <epreuve>demande</epreuve> <marqueur>certainement</marqueur> une <entite>exception</entite> pour ces deux <entite>cultures</entite>.



Il peut arriver que certains termes ne soient pas indexés dans les dictionnaires. Il sera alors considéré comme "indéfini". La première façon d'enrichir ses dictionnaires, c'est donc de classer les indéfinis dans un des types de base. Ainsi, on ajoutera "SCOPAFF" et "néonicotinoïdes" à la liste des entités, et "phytosanitaires" à la liste des qualité.

````{margin}
```{note}
Attention, Prospéro ne gère pas automatiquement le singulier/pluriel, le masculin/féminin. Si on ajoute "néonicotinoïd**es**", il faudra aussi ajouter "néonicotinoïd**e**" pour que Prospéro reconnaisse les deux formes.
```
````

![La liste des indéfinis](images/indefini.png)

On remarque aussi qu'il y a des "expressions" qu'il peut être intéressant d'indexer : "matières actives", "produits phytosanitaires", "santé des abeilles", "Confédération des Betteraviers Belges", "en raison".

> Vendredi prochain, les <entite>États membres</entite> européens se prononceront probablement dans le cadre de la SCOPAFF sur l'interdiction ou non de trois <entite>matières actives</entite> présentes dans certains <entite>produits phytosanitaires</entite> <motoutil>en raison</motoutil> de leur impact éventuel sur la <entite>santé des abeilles</entite>. Les trois <entite>matières actives</entite> en question appartiennent à la <entite>famille des néonicotinoïdes</entite> et sont cruciales pour la culture de la betterave et de la chicorée en Belgique. En cas d'interdiction, la <entite>Confédération des Betteraviers Belges</entite> (CBB) demande certainement une exception pour ces deux cultures.

### Exercice 1

Dans les deux textes disponibles [ici](https://framagit.org/Aymericluneau/prospero_formation/-/tree/master/textes) ou [là](https://cloud.prefigura.social/index.php/s/5XGPtbbnknmyaiW?path=%2FcorpusStagiaires) (un communiqué de presse de la Confédération des Betteraviers Belges et un communiqué de presse de Nature et Progrès Belgique)

-   Identifiez les différents types de base (entité, qualité, marqueur, épreuve)

-   Quelles expressions avez-vous repérées ? À quels types appartiennent-elle ?



## Dictionnaires de concepts

La question des expressions, qui en un sens suppose déjà un travail interprétatif, permet d'enchaîner avec les dictionnaires des concepts. Ces dictionnaires reflètent en effet le travail d'analyse et les hypothèses du chercheur.


<table>
  <thead>
    <tr>
      <th>Concepts</th>
      <th>Définition</th>
      <th>Types de base concernés</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Être-fictif</td>
      <td>Groupement des appellations d'une même entité. Identifié grâce au symbole "@"</td>
      <td>Entités uniquement</td>
    </tr>
    <tr>
      <td>Collection</td>
      <td>Instance de groupement de type taxonomique </td>
      <td>Entités uniquement</td>
    </tr>
    <tr>
      <td>Catégorie</td>
      <td>Regroupe des termes selon une logique sémantique</td>
      <td>Entités, qualités, épreuves, marqueurs</td>
    </tr>
  </tbody>
</table>

<br>

Les **êtres-fictifs** font écho à la notion d'"actant" dans la sémantique structurale de {cite:t}`greimas2002`. Ils regroupent les entités qui font référence à un même objet ou actant. Par exemple, on peut considérer que "bettraviers", bettraviers belges", "Confédération des Betteraviers Belges" font référence à l'"être-fictif" BETTRAVIERS@. La constitution d'être-fictifs est particulièrement utile lorsqu'on travaille sur les partis et personnalités politiques.

- PS@ : Parti socialiste, rue de Solférino, parti à la rose, etc.

- LFI@ : LFI, La France Insoumise, le Parti de Jean-Luc Mélenchon

````{margin}
```{note}
Un mot en lettres capitales suivi d'une arobase est la convention d'écriture utilisée pour signifier qu'il s'agit d'un être-fictif.
```
````

Les **collections** prennent la forme de taxonomies ou de répertoires. Elles se rapprochent de la notion de "monde" {cite}`greimas2002`. Les collections rendent compte en effet des univers de référence des textes {cite}`chateauraynaud2003` (p.221). On pourra dire d'un article dans lequel la "collection" des organisations internationales est présente qu'il se réfère au monde des politiques internationales. Tandis que la présence d'une collection d'agences d'expertise comme l'EFSA, l'ANSES caractérisent souvent les textes qui parlent de controverses sanitaires ou environnementales. Dans Prospéro, les collections sont reconnaissables au fait que leurs noms sont écris en lettre capitale ponctués d'un astérique. Par exemple, la collection "ENNEMIS-DES-ABEILLES\*" rassemble les éléments chimiques, physiques ou biologiques qui représentent un risque pour la santé des abeilles.

````{margin}
```{note}
Un mot en lettres capitales suivi d'un astérisque est la convention d'écriture utilisée pour signifier qu'il s'agit d'une collection.
```
````

Enfin, les **catégories** permettent de typifier des registres discursifs : politiques, scientifiques, polémiques ou encore critiques. Par exemple, on fait l'hypothèse que des expressions comme "la nature", "action pour l'environnement", "alternatives énergétiques" ou "développement durable" connotent un "discours environnementalistes". Tandis que "science", "méthode", "preuve", "facteur" caractérisent une "rhétorique scientifique". Par ailleurs, comme cela a été dit, il existe des :

- catégories de qualités telle que la catégorie "discours critiques" qui regroupe des mots comme "anormal" ou "absurde"

- catégories de marqueurs réunissant par exemple les adverbes qui expriment l'incertitude ("potentiellement", "probablement", "certainement")

- catégories d'épreuve comme "Accuser" ("accuse", "a mis en cause", "a admonesté")


## Exercice 2

Dans les deux textes disponibles [ici](https://framagit.org/Aymericluneau/prospero_formation/-/tree/master/textes) ou [là](https://cloud.prefigura.social/index.php/s/5XGPtbbnknmyaiW?path=%2FcorpusStagiaires) (un communiqué de presse de la Confédération des Betteraviers Belges et un communiqué de presse de Nature et Progrès Belgique)

-   Quels sont les êtres-fictifs que nous pouvons créer pour "faciliter" la compréhension des textes ? Même question pour les collections ?

-   Avez-vous identifié des ensembles d'entités, de qualité ou de marqueurs qui pourraient être regroupés au sein de catégories ? Que nous apprennent-ils sur l'argumentation des acteurs ?

## Références

```{bibliography}
:filter: docname in docnames
```
