# L'analyse textuelle : Prospéro et les autres

Les chercheurs et chercheuses en sciences humaines et sociales disposent aujourd'hui d'un large éventail d'outils et de méthodes pour analyser des corpus textuels. Afin de se rendre compte de l'évolution de ce champ, de son dynamisme et de la position que Prospéro y occupe, on peut utilement lire l'ouvrage collectif *Analyses textuelles en sociologie* {cite}`brossaud2006` ou l'article de {cite:t}`cointet2018`.


## "Mondes lexicaux" et statistiques fréquentielles
Dans le monde francophone, l'autre logiciel auquel on compare le plus souvent Prospéro est Iramuteq (version freeware d'Alceste). Iramuteq repose sur la "méhode Alceste" mis au point par Max Reinert dans la continuité des methodes développées par Benzecri (AFC) et s'inscrit, à cet égard, dans l'école "française" de l'analyse des données.

> « Le locuteur au cours de son énonciation investit des mondes propres successifs et ces lieux, en imposant leurs objets, imposent du même coup leur type de vocabulaire. En conséquence, l’étude statistique de la distribution de ce vocabulaire devrait pouvoir permettre de retrouver la trace des ‘environnements mentaux’ que le locuteur a successivement investis, trace perceptible sous forme de ‘mondes lexicaux’ » {cite}`max1993`

> [Hypothèse 1] Nous faisons l'hypothèse qu'un corpus de texte peut être considéré comme un ensemble d'énoncés indépendants et redondants, dans la mesure où chaque énoncé est supposé porter l'empreinte d'une même processus sous-jacent dépendant des conditions de production de cet énonce (d'ordre psychique, social, culturel, narratif, etc.) {cite}`reinert1987`

> [Hypothèse 2] Dans un corpus vérifiant l'hypothèse 1, "les énoncés" utilisant plutôt les mêmes vocables renvoient généralement à une même représentation sous-jacente, et ceci avec d'autant plus de certitudes que le nombre d'énoncés est grand.

La méthode Alceste, développée initialement pour l'analyse de contenu en psychologie {cite}`reinert1987`, consiste à appliquer un algorithme de classification hiérarchique descendante à partir d'une matrice ou tableau lexical *énoncés X mots*.On parle de classification hiérarchique descendante, car l'algorithme consiste a "découper" (ou partitionner) le tableau lexical de sorte à maximiser le khi-deux au sein de chaque sous partie {cite}`reinert1987,reinert1990`. L'opération est itérée autant de fois que demandée.

<table>
<thead>
<tr>
<th></th>
<th>mot 1</th>
<th>mot 2</th>
<th>...</th>
<th>mot n</th>
</tr>
</thead>
<tbody>
<tr>
<td>énoncé 1</td>
<td>0</td>
<td>1</td>
<td>...</td>
<td>1</td>
</tr>
<tr>
<td>énoncé 2</td>
<td>1</td>
<td>0</td>
<td>...</td>
<td>0</td>
</tr>
<tr>
<td>...</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>énoncé n</td>
<td>1</td>
<td>1</td>
<td>...</td>
<td>1</td>
</tr>
</tbody>
</table>

## Approche probabiliste du topic modelling
![](./images/topic_modelling.jpeg)

Une autre méthode de "Topic modelling" populaire, notamment anglo-saxon, est le "Latent dirichlet allocation". L'algorithme vise à determiner la probabilité qu'un mot *m* appartienne au topic *t* et que le document *d* contenant *m* appartienne également à *t*

> Latent Dirichlet Allocation (LDA) is used as a topic modelling technique that can classify text in a document to a particular topic. It uses Dirichlet distribution to find topics for each document model and words for each topic model. [https://medium.com/analytics-vidhya/latent-dirichelt-allocation-1ec8729589d4#:~:text=Latent%20Dirichlet%20allocation%20is%20a,rules%2C%20facts%20that%20we%20considered.](a brief explanation)

> It is one of the most popular topic modeling methods. Each document is made up of various words, and each topic also has various words belonging to it. The aim of LDA is to find topics a document belongs to, based on the words in it. Confused much? Here is an example to walk you through it. [https://towardsdatascience.com/latent-dirichlet-allocation-lda-9d1cd064ffa2](A Beginner’s Guide to Latent Dirichlet Allocation(LDA))

> Le modèle Latent Dirichlet Allocation suppose que chaque document est un mélange d’un petit nombre de topics, et que chaque occurrence d’un mot correspond à l’un des sujets du document. Chaque mot se voit attribuer un topic selon la loi de Dirichlet.

![](./images/lda.png)

À partir de cette première distribution, la probabilité d'appartenance de chaque mot de chaque document à un topic *t* est évaluée en fonction :

- De la proportion de mots du document appartenant également au topic *t*

- De la proportion de documents appartenant au topic *t* à cause du mot *m*.

L'algorithme est répété jusqu'à trouver une distribution stabilisée.

Comme pour la "méthode alceste", on considère les documents et les énoncés consituant ces documents comme des "sacs de mots". L'ordre et le role grammatical n'est pas pris en compte. Ainsi, il est habituel de lemmatiser les termes. Le LDA suppose également de constuire un tableau lexical *énoncé X termes*. Toutefois, la méthode de "clustering", qui permet de déterminer les topics, est probabiliste. L'intérêt par rapport à la méthode alecste est que le LDA autorise un document à appartenir à plusieurs topic. Une des principales limites de cette méthode est qu'il faut déterminer en amont le nombre de "topics" caractérisant le corpus. Par ailleurs, il fonctionne assez mal sur des "documents" courts comme les tweets.

## Plongement de mots : Top2Vec, BERTopic

La dernière famille de méthodes de topic modelling, aussi la plus récente, consiste à s'appuyer des modèles de "plongement de mot" (*word embedding*). Là encore, on considère les documents comme des sacs de mot que l'on représente sous forme de tableau lexical (ou matrice). Cette matrice permet d'associer un vecteur à chaque terme et, ainsi, de positionner ce terme dans un espace composé d'un nombre de dimensions réduit. Ces modèles fonctionnent grâce à des algorithmes d'apprentissage. Top2vec (basé sur le modèle d'embedding word2vec de Google) et BERTopic sont les algorithmes les plus souvents cités.

> Word embeddings are a type of word representation that allows words with similar meaning to have a similar representation. Its the collective name for a set of language modelling and feature learning techniques in natural language processing (NLP) where words or phrases from the vocabulary are mapped to vectors of real numbers.
