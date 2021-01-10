
# My Data Science Portfolio

Contact: [loicnazaries@yahoo.fr](loicnazaries@yahoo.fr "email contact")

---

---

## Table of contents

- [My Data Science Portfolio](#my-data-science-portfolio)
  - [Table of contents](#table-of-contents)
  - [My « Elevator Pitch »](#my--elevator-pitch-)
  - [My Current Projects](#my-current-projects)
    - [Pipeline d'intégration, de nettoyage et de validation de données](#pipeline-dintégration-de-nettoyage-et-de-validation-de-données)
    - [Dashboard](#dashboard)
    - [Note: Dans l'avenir, une section de *machine learning* sera disponible. Il sera en autre possible de procéder à une modélisation temporelle des emissions des gaz à effet de serre.](#note-dans-lavenir-une-section-de-machine-learning-sera-disponible-il-sera-en-autre-possible-de-procéder-à-une-modélisation-temporelle-des-emissions-des-gaz-à-effet-de-serre)
      - [P.S: application non disponible au moment de la préparation de cette page (10/01/2021).](#ps-application-non-disponible-au-moment-de-la-préparation-de-cette-page-10012021)
  - [My Past Projects](#my-past-projects)
    - [Modélisation des émissions des gaz à effet de serre](#modélisation-des-émissions-des-gaz-à-effet-de-serre)
    - [Élaboration d'un indicateur multiple de performance (« *KPI* »)](#élaboration-dun-indicateur-multiple-de-performance--kpi-)
    - [Modélisation géographique](#modélisation-géographique)
    - [Coopération internationale](#coopération-internationale)
  - [Autres réalisations professionnelles](#autres-réalisations-professionnelles)
    - [Maître de thèse](#maître-de-thèse)
    - [Revue littéraire](#revue-littéraire)
    - [Optimisation de procédés quantitatifs](#optimisation-de-procédés-quantitatifs)
    - [Exploration de l’Écosse](#exploration-de-lécosse)
    - [Écrire une thèse doctorale](#écrire-une-thèse-doctorale)
  - [My Biography](#my-biography)
  - [References](#references)

---

---

## My « Elevator Pitch »

C’est au cours de mes études doctorales que je me suis découvert une vraie passion pour la « ***Data*** » et les **analyses statistiques**. Ce qui me stimule le plus, c'est de pouvoir jongler avec des données et en distiller des informations utiles pour ensuite les retranscrire, notamment, sous la forme de supports visuels simples et impactant de type « ***Dashboard*** ».

Après 13 années passées dans le domaine des **biostatistiques**, je recherche maintenant un nouveau challenge. Mon expérience, mes compétences transverses et mes connaissances dans la gestion de données me procurent un bon socle pour le poste de **Data Analyst/Data Scientist** que je décline en trois principaux piliers :

- *Data Mining*
- *Machine Learning*
- *Data Visualisation* (« *DataViz* »)

Ainsi, l’extraction et l’interprétation de l’information contenue dans des bases de données produisent une **forte valeur ajoutée** aux données permettant de valoriser une **aide à la prise de décision** plus rapide et plus intelligente.

Je recherche une entreprise prête à me donner une chance de m’épanouir professionnellement, de libérer mon potentiel au sein d'une équipe dynamique et soudée et dans un environnement riche en expériences professionnelles. Je veux aussi faire profiter mes qualités humaines telles que la pédagogie, l’adaptabilité ou encore l’humilité.

Je crois en l’apprentissage par la pratique et, dans un futur proche, je souhaite accéder à un poste de Data Scientist spécialisé en [**Recherche Opérationnelle**](https://fr.wikipedia.org/wiki/Recherche_op%C3%A9rationnelle) et [***DataOps***](https://medium.com/data-ops/dataops-in-7-steps-f72ff2b37812).

Pensez-vous que nous avons des objectifs communs ?

---

---

## My Current Projects

---

### Pipeline d'intégration, de nettoyage et de validation de données

Une **base de données relationelle** a été construite à partir de fichiers de type et d'origine multiples (enregistreurs automatiques, mesures manuelles, fichiers au formats variés - .csv, .txt, tableur, *etc.*). Grâce aux fonctionalités Python, ces données ont été uniformisées et "nettoyées" tout en respectant les bonnes pratiques statistiques (par exemple, pas de "*cherry-picking*", ni de "*data dredging*", *etc.* - *cf.*
[*Data Fallacies to avoid*](../loic-nazaries.github.io/documents/data-fallacies-to-avoid.pdf)).

En particulier, les trois étapes suivantes sont importante dans tout project de «  ***Data Science*** » :

1) typage des variables (*category*, *integers*/*floats*, *strings*, *booleans*, *dates*). Très important, en particulier, pour diminuer l'utilisation de la mémoire vive d'un ordinateur ou serveur

2) remplacement (ou *imputation*) des valeurs manquantes ([**Figure 1**](#Figure1)). C'est une étape importante qui permet de préserver la puissance statistique d'un jeux de données

<table><tr>
<td> <img src="../loic-nazaries.github.io/images/ghg_flux_data_missing_data_raw_heatmap.png" alt="BEFORE Transformation" style="width: 250px;"/> </td>
<td> <img src="../loic-nazaries.github.io/images/ghg_flux_data_missing_data_clean_heatmap.png" alt="AFTER Data Transformation" style="width: 250px;"/> </td>
</tr></table>

**Figure 1**:  The replacement of missing values by mathematical approach. Here, when the value of a replicated measurement (usually seven (7) replicates) was missing (*left panel*), it was replaced by the "mean" value of the other replicated samples. The remaining missing values (*right panel*) represent non-replicated data which can be imputed using more powerfull machine learning approaches (not detailed here).

3) transformation des variables pour obtenir une distribution dite « normale » ([**Figure 2**](#Figure2)). Le but est donc de diminuer le nombre de valeurs dite « extrêmes », c'est-à-dire des valeurs très éloignées de la valeur moyenne.

![N2O Data Transformations](../loic-nazaries.github.io/images/n2o_flux_distrib_violinplots.png "N2O Data Transformations")

**Figure 2**: Mathematical transformation of nitrous oxide (N2O) emissions. The various « violin plots » represent different transformation of the raw data in order to seek « normal distribution » *(e.g.* standardised transformation, square-root transformation, *etc.*). The aim is to reach a symetrical distribution and thus avoid (left- or right-handed) tails.

De manière plus générale, il s'agit de préparer les jeux de données pour les étapes d'analyses statistiques et de modélisation (« *machine learning* »)

Ensuite, une analyse temporelle (*time-series analysis*) a été appliquée ([**Figure 3**](#Figure3)) pour tester l'hypothèse scientifique de départ: 

« Quel est l'effet de l'augmentation du dioxide de carbone (CO2) dans l'atmosphère sur les émissions des gaz à effet de serre? »

![Monthly GHG Emissions](../loic-nazaries.github.io/images/GHG_fluxes_time_series.png "Monthly GHG Emissions")

**Figure 3**: Greenhouse gas (GHG) emissions for méthane (CH4 flux - panel a), nitrous oxide (N2O flux - panel b) and carbon dioxide (CO2 flux - panel c). Ambient (blue line) and elevated (red line) atmospherique CO2 concentrations represent the « treatment » applied to test the scientific hypothesis investigated. There is already a strong visible link between the intensity of GHG emissions and the intensity of the rainfall events (panel d). 

---

### Dashboard

Un tableau de bord (« *dashboard* ») interactif a été construit pour observer et tester les émissions des gaz à effet de serrre sous différentes conditions. Cette **application web** appelée « Greenhouse Gas Estimation Portal » a été codé avec la librairie Python [Streamlit.io](https://www.streamlit.io/) et déployée sur [Heroku.com](https://www.heroku.com/). L'application peut être accédée avec le [lien suivant](https://exam-piscine-heroku-redone.herokuapp.com/). Des captures d'ecran sont disponible dans la ([**Figure 4**](#Figure4)).

Il s'agit d'une application entièrement réglable un fois que l'utilisateur a créé un compte. Voici une liste (non-exhaustive) des options disponibles:

- téléchargement du fichier de données (format .csv ou .pkl)
- sélection des variables à inclure dans l'analyse
- typage des variables
- choix des variables dépendantes et indépendantes
- « *dummification* » possible des variables
- génération d'un résumé statistique (moyenne, ecart-type, kurtosis/skewness, percentage des valeurs manquantes, *etc.*)
- agrégation des données par groupe (date, traitement, annéé, *etc.*)
- analyses univariées et bivariées
- analyses de corrélation
- analyses statistiques de type « REML » (*restriction likelyhood*)
- send results to the user by email

<!-- ![Web App Login](../loic-nazaries.github.io/images/streamlit_login_screenshot.png "Streamlit Login") | ![Variable Selection](../loic-nazaries.github.io/images/streamlit_vars_selection_screenshot.png "Streamlit Variable Selection") -->

<table><tr>
<td> <img src="../loic-nazaries.github.io/images/streamlit_login_screenshot.png" alt="Streamlit Login" style="width: 500px;"/> </td>
<td> <img src="../loic-nazaries.github.io/images/streamlit_vars_selection_screenshot.png" alt="Streamlit Variable Selection" style="width: 500px;"/> </td>
</tr></table>

<td> <img src="../loic-nazaries.github.io/images/streamlit_time_series_screenshot.png" alt="Streamlit Time-Series Analysis" style="width: 500px;"/> </td>
<td> <img src="../loic-nazaries.github.io/images/streamlit_email_screenshot.png" alt="Streamlit Email Results" style="width: 500px;"/> </td>

Figure 4: Screenshots of various steps and options available to the user on the web application « Greenhouse Gas Estimation Portal ».

### Note: Dans l'avenir, une section de *machine learning* sera disponible. Il sera en autre possible de procéder à une modélisation temporelle des emissions des gaz à effet de serre.

#### P.S: application non disponible au moment de la préparation de cette page (10/01/2021).

---

---

## My Past Projects

---

### Modélisation des émissions des gaz à effet de serre

<a href="http://www.youtube.com/watch?feature=player_embedded&v=K8RTVdijc0o" target="_blank">
<img src="http://img.youtube.com/vi/K8RTVdijc0o/0.jpg"
alt="EucFACE Travelling View" width="240" height="180" border="10" /></a>

Video 1: Moving up a ring at the EucFACE site (see [EucFACE Presentation](../loic-nazaries.github.io/eucface_presentation.md)).

![EucFACE Canopy View](../loic-nazaries.github.io/images/Completed_EucFace_Rings.jpg "EucFACE Canopy View")

**Picture 1**: Canopy view from Ring 6 at the EucFACE Site.

[1]: Griscom, B.W., Adams, J., Ellis, P.W., Houghton, R.A., Lomax, G., Miteva, D.A., Schlesinger, W.H., Shoch, D., Siikamäki, J. V, Smith, P., Woodbury, P., Zganjar, C., Blackman, A., Campari, J., Conant, R.T., Delgado, C., Elias, P., Gopalakrishna, T., Hamsik, M.R., Herrero, M., Kiesecker, J., Landis, E., Laestadius, L., Leavitt, S.M., Minnemeyer, S., Polasky, S., Potapov, P., Putz, F.E., Sanderman, J., Silvius, M., Wollenberg, E., Fargione, J., 2017. Natural climate solutions. Proceedings of the National Academy of Sciences 114, 11645 LP – 11650. doi:10.1073/pnas.1710465114\n

---

### Élaboration d'un indicateur multiple de performance (« *KPI* »)

Un conglomérat d’agriculteurs australiens a financé une étude dans laquelle j’ai été chargé d’identifier les facteurs biologiques et environnementaux qui sont susceptible d’améliorer les rendements de blé en lien avec les pratiques d’agricultures communes en Australie (chaume brûlé, fertilisation, pâturage, labourage, etc.). Cette expérience était constituée de sites dans plusieurs régions/états de l’Australie. Un ample effort de coordination a été primordial au bon déroulement de cette étude, ainsi qu’une bonne communication avec les propriétaires des terres et les gouvernements locaux. J’ai aussi eu la charge de tenir notre base de données à jour et disponible auprès de mes collaborateurs.

Au terme de mes analyses, j’ai défini un indicateur de performance qui révèle comment chaque pratique agricole impacte le recyclage des nutriments dans le sol, en d’autres mots, la qualité et la quantité des récoltes de blé. Durant ce projet, j’ai appris à ajuster mon discours de manière à le rendre plus compréhensible (travail de vulgarisation) auprès de non-spécialistes, c’est-à-dire les agriculteurs et les acteurs locaux. Voir :

[1]: Nazaries et al., 2019. Response of soil nutrient multi-functionality to agricultural management practices can be predicted by key soil abiotic and biotic properties. En préparation.

---

### Modélisation géographique

J’ai complété une étude décrivant les étapes de modélisation nécessaire pour prédire la répartition géographique de microbes dans le sol responsables de la réduction des concentrations de méthane (un puissant gaz effet de serre) dans l’atmosphère.
Grâce au sponsor du gouvernement écossais, une grande base de données a été formée après un sondage du sol dans toute l’Écosse. L’objectif a été de collecter plusieurs données environnementales (température, pluies, humidité, nutriments, fertilité, composition minérale, etc.) pour mieux décrire les procédés biologiques dans le sol. J’ai réparti les tâches de modélisation entre mes collaborateurs pour faire avancer le processus intellectuel. Une fois les analyses terminées, j’ai écrit un article scientifique pour présenter nos résultats. Cela a été une occasion fantastique pour apprendre à manier des méthodes statistiques pointues. Voir la référence suivante :
          Nazaries, L., et al., 2018. Environmental drivers of the geographical distribution of methanotrophs: Insights from a national survey. Journal of Soil Biology and Biochemistry. doi:10.1016/J.SOILBIO.2018.08.014. Notamment, j’ai rendu publique notre base de données sur le site figshare.com pour permettre à d’autres équipes d’utiliser mes données pour leurs propres études.

---

### Coopération internationale

Après avoir établi une collaboration avec des chercheurs d’Australie, Angleterre, Écosse et USA, j’ai mis en place une série de protocoles afin d’organiser les tâches administratives et techniques nécessaire pour remplir l’objectif de la mission (mesure des gaz à effet de serre). J’ai aussi eu la responsabilité de former les collaborateurs et de coordonner les équipes pour garantir les délivrables.
Une fois les données générées, je les ai agrégé et préparé : enregistrement dans une base de données ; nettoyage ; détection de données aberrantes et de données manquantes ; transformation/normalisation ; exploration. Enfin, j’ai conduit toutes les analyses statistiques, j’ai préparé les résultats (tables et graphes) et j’ai décrit les conclusions dans un rapport de mission. Particulièrement, j’ai présenté les conclusions de cette étude devant les « clients », c’est-à-dire les organismes privés et publiques qui ont financés ma recherche. Grâce à cette expérience, j’ai réussi à gérer des projets de bout-en-bout ainsi qu’à faire face à des problèmes administratifs, techniques et humains. Un des articles issu de cette collaboration est le suivant :
          Martins, C.. S.C., Nazaries, L., et al., 2017. Identifying environmental drivers of greenhouse gas emissions under warming and reduced rainfall in boreal-temperate forests. Journal of Functional Ecology. doi:10.1111/1365-2435.12928.

---

---

## Autres réalisations professionnelles

---

### Maître de thèse

J’ai eu la responsabilité de superviser deux étudiantes. Je les ai soutenues dans la définition et la construction de leur projet de recherche : identification des lacunes scientifiques ; mise en place des protocoles ; formation technique et littéraire ; analyse des données et écriture de leur manuscrit de thèse. Le plus gratifiant a été quand j’ai assisté à leur cérémonie de remise des diplômes.

---

### Revue littéraire

J’ai recherché sur internet des centaines d’études et d’articles en rapport avec mon thème de recherche : les émissions biologiques du gaz méthane qui produit un effet de serre 31 fois plus puissant que the dioxide de carbone (CO2). J’ai dû décrire l’origine des bactéries responsables du cycle du méthane entre l’atmosphère et le sol ainsi que leurs propriétés génétiques et biochimiques. J’ai concentré mes trouvailles en une large revue publiée dans un journal scientifique :
          Nazaries, L. et al., 2013. Methane, microbes and models: fundamental understanding of the soil methane cycle for future predictions. Journal of Environmental Microbiology. doi:10.1111/1462-2920.12149.

---

### Optimisation de procédés quantitatifs

Ou, Surmonter une difficulté.

J’ai été confronté à une situation frustrante au cours de laquelle un system de détection génétique était défectueux. J’ai opéré une recherche bibliographique au cours de laquelle j’ai trouvé un algorithme d’optimisation opérationnelle (approche Taguchi) qui m’a aidé à franchir cet obstacle. Cette approche est beaucoup utilisée dans l’industrie mais j’ai su l’adapté à ma technologie génétique.

---

### Exploration de l’Écosse

Mon projet d’étude nécessitait la sélection de plusieurs sites écologiques pour la mesure de flux de méthane dans l’atmosphère. J’ai dû sélectionner des sites aux quatre coins de l’Écosse afin d’avoir des conditions variées. J’avais aussi la charge de préparer toute la logistique, trouver des collaborateurs disponibles sur plusieurs jours, et ce, durant les quatre saisons de l’année, et pendant trois ans. C’était un projet très difficile et demandant qui m’a permis d’apprendre beaucoup, autant au niveau technique et professionnel qu’au niveau personnel et humain.

---

### Écrire une thèse doctorale

C’était une épreuve très demandante et difficile. On m’a donné un thème de recherche et j’ai dû faire tout le reste : recherche littéraire ; planification des expériences ; génération des données ; analyses statistiques ; et surtout, écriture de ma thèse de fin d’étude. J’ai retranscrit tout ce que j’avais fait pendant plus de trois ans. Au final, j’ai publié cette thèse dont je suis très fier. Cela m’a beaucoup appris : indépendance, autonomie, adaptabilité, organisation, rigueur.

---

---

## My Biography

C’est à l’âge de 10 ans, en CM2, que j’ai décidé de devenir un biologiste. C’était après la dissection d’un cœur de vache… En l’an **2000**, au crépuscule du XXème siècle et au levé du XXIème siècle, j’ai décidé de quitter Bordeaux et le cocon familial pour commencer mon « voyage » académique autour du monde.

Première étape, rien de mieux que Clermont-Ferrand (*Université d'Auvergne*), et ses spécialités fromagères. Là, j’ai reçu une bourse du *département de l’éducation française* pour obtenir un diplôme IUT avec option pharmacologie et expérimentation animale. Au moment de choisir mon stage de recherche, j’ai décidé de me spécialiser en cultures cellulaires au *James Hutton Institute* à Aberdeen en Écosse pour pouvoir améliorer mon anglais bien que l’accent aberdonien soit TRÈS difficile à comprendre !

En **2002**, grâce à une bourse de déplacement offerte pour la première année de ma licence (option microbiologie médicale), je suis resté étudier à la *Robert Gordon Universiy* d’Aberdeen.

En **2004**, comme l’accent écossai n’avait plus de secret pour moi, j’ai décidé d’ajuster « *a wee bit* » (traduction: un petit peu) ma carrière de biologiste en pharmacologie et analyses de laboratoires pour commencer une maîtrise en sciences instrumentales et analytiques, option sciences légales (sciences criminologiques). Petite précision: après ceci, je peux vous dire que toutes ces séries TV ne valent rien !

Cette spécialisation était supportée par une bourse de la *Student Awards Agency Scotland* (SAAS). Malheureusement, il n’était pas possible de trouver un stage en criminologie. Je me suis donc dirigé vers la microbiologie de l’environnement, basé au *James Hutton Institute* (Aberdeen, Écosse).

Après avoir visionné le documentaire [***An Inconvenient Truth (2006)***](https://www.youtube.com/watch?v=Bu6SE5TYrCM) dans lequel Al Gore expose les causes et conséquences du réchauffement climatique accéléré par l’Homme, j’ai décidé de lutter contre le changement climatique à ma manière.

En **2007**, j’ai reçu une bourse du *Macaulay Institute Trust Fund* pour commencer mes études doctorales au *James Hutton Institute* (Aberdeen, Écosse) en collaboration avec *University of Warwick* et *University of Aberdeen*. Mes recherches avaient pour but d'examiner l’effet des changements de pratiques forestières (déforestation / afforestation / reforestation) sur les microorganismes en lien avec la production méthane, un puissant gaz à effet de serre plus de 30 fois plus puissant que le dioxide de carbon (CO2).

Après cette très bonne expérience, j’ai réalisé que je n’avais toujours pas réussi à ralentir la progression de cette « maladie » qu’est le changement climatique… En **2011**, j’ai donc trouvé un poste de *Research Scientist* (chercheur associé) au *Hawkesbury Institute of Environnent*, dépendant de la *Western Sydney University* (Australie). Là-bas (« *The Land Down Under* »), j'ai pu travailler sur de nombreuses thématiques en lien avec l'exploration des effets du changement climatique telles que le réchauffement atmosphérique, l'augmentation de l'intensité et de la fréquence des pluies, ainsi que l'application de fertiliseurs naturels ou synthétiques. En particulier, j'ai mesuré ces effets sur les émissions des gaz à effet de serre.

Durant six ans j’ai essayé de mettre fin à cette maladie de la Terre. Je peux dire sans aucun doute qu’il y a toujours du boulot à faire…

J'ai aussi participé à des études pour améliorer les rendements de blé des cultivateurs de graines grâce à une étude financée par le gouvernement australien et le ministère du *Department of Primary Industry* et le consortium des agriculteurs australiens du *Grain Research and Development Corporation*.

J'ai gardé mes contacts académiques et continu de contribuer à des analyses de données et à écrire des publications scientifiques dans des journaux internationaux de renommés tel que [***Nature***](https://www.nature.com/articles/s41586-020-2128-9).

Mon voyage académique m’a donné la chance de collaborer et visiter de nombreux pays (et villes) au Royaume Uni, USA, Nouvelle-Zélande, Australie, Asie, et Europe évidement. Cette aventure a apporté beaucoup de richesse à mon profil. En particulier, rencontrer des gens de culture parfois très différentes ; enrichir mes compétences professionnelles ; ou encore découvrir des façons différentes d’aborder un sujet de recherche grâce à de nombreuses collaborations internationales et conférences.

Maintenant que je suis revenu en France, la boucle est-elle bloquée ?

---

---

## References
