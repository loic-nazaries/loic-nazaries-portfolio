# My Data Science Portfolio

Quelques examples de mon travail d'**analyse de données**.

---

Table des matières

- [My Data Science Portfolio](#my-data-science-portfolio)
  - [Mon *Elevator Pitch*](#mon-elevator-pitch)
  - [Mes compétances en science des données](#mes-compétances-en-science-des-données)
  - [Mes projets actuels](#mes-projets-actuels)
    - [Pipeline d'intégration, de nettoyage et de validation de données](#pipeline-dintégration-de-nettoyage-et-de-validation-de-données)
    - [Tableau de bord](#tableau-de-bord)
  - [Mes projets passés](#mes-projets-passés)
    - [Modélisation des émissions des gaz à effet de serre](#modélisation-des-émissions-des-gaz-à-effet-de-serre)
    - [Élaboration d'un indicateur multiple de performance (KPI)](#élaboration-dun-indicateur-multiple-de-performance-kpi)
    - [Modélisation géographique](#modélisation-géographique)
    - [Coopération internationale](#coopération-internationale)
  - [Mes *Scripts/Gists*](#mes-scriptsgists)
    - [Créer un environnement virtuel avec Python](#créer-un-environnement-virtuel-avec-python)
    - [Créer un environnement virtuel avec Conda](#créer-un-environnement-virtuel-avec-conda)
    - [Créer un dépôt de projet avec GitHub](#créer-un-dépôt-de-projet-avec-github)
    - [Déployer une application web avec Heroku](#déployer-une-application-web-avec-heroku)
    - [Pipeline d'un projet de *Data Science*](#pipeline-dun-projet-de-data-science)
  - [Autres réalisations professionnelles](#autres-réalisations-professionnelles)
    - [Maître de thèse](#maître-de-thèse)
    - [Revue littéraire](#revue-littéraire)
    - [Optimisation de procédés quantitatifs](#optimisation-de-procédés-quantitatifs)
    - [Exploration de l’Écosse](#exploration-de-lécosse)
    - [Écrire une thèse doctorale](#écrire-une-thèse-doctorale)
    - [Mes publications scientifiques](#mes-publications-scientifiques)

---

---

## Mon *Elevator Pitch*

Doué d'une grande appétance pour les **statistiques**, l'analyse exploratoire de données et le « **machine learning** », j'aime pouvoir jongler avec des données et en distiller des informations utiles pour ensuite les retranscrire, notamment, sous la forme de supports visuels simples et impactant de type « ***Dashboard*** ». Je consulte fréquemment les sites spécialisés pour découvrir de nouvelles technologies pour les appliquer plus tard dans mes projets de « ***Data Science*** ».

Je crois en l’apprentissage par la pratique et, dans un futur proche, je souhaite accéder à un poste de Data Scientist spécialisé en [**Recherche Opérationnelle**](https://fr.wikipedia.org/wiki/Recherche_op%C3%A9rationnelle "Recherche Opérationnelle - Wikipedia.org") et [***DataOps***](https://medium.com/data-ops/dataops-in-7-steps-f72ff2b37812 "DataOps - Medium.com").

Pensez-vous que nous avons des objectifs communs ?

Jetez un coup d'oeil à ma [Biographie](/my_biography.md).

---

---

## Mes compétances en science des données

La [**Figure 0**](#figure-0) est le « **Plan de Métro** » de mes compétences en *Data Science* appliqué au métier de **Data Analyst/Data Scientist**.

Les « **lignes** » en circulation sont:

- *Data Mining - Descriptive & Exploratory Data Analysis*
- *Data Preparation*
- *Forecasting*
- *Analysis of Variance*
- *Database Management System - Business Intelligence*
- *Machine Learning*
- *Data Visualisation - Dashboarding*

More to come!

[![Metro Map Data Science](/images/MetroMap_Data_Analyst_16-10-2020.png "Click Me!")](/metro_map.md)

**Figure 0**: Metro Map of my **Data Analyst/Data Scientist** skills in the field of **Data Science**.

---

---

## Mes projets actuels

---

### Pipeline d'intégration, de nettoyage et de validation de données

Une **base de données relationelle** a été construite à partir de fichiers de type et d'origine multiples (enregistreurs automatiques, mesures manuelles, fichiers au formats variés - .csv, .txt, tableur, *etc.*). Grâce aux fonctionalités Python, ces données ont été uniformisées et "nettoyées" tout en respectant les bonnes pratiques statistiques (par exemple, pas de "*cherry-picking*", ni de "*data dredging*", *etc.* - *cf.*
[*Data Fallacies to avoid*](/documents/data-fallacies-to-avoid.pdf)).

En particulier, les trois étapes suivantes sont importante dans tout project de « ***Data Science*** » :

1. Typage des variables (*category*, *integers*/*floats*, *strings*, *booleans*, *dates*). Très important, en particulier, pour diminuer l'utilisation de la mémoire vive d'un ordinateur ou serveur

2. Remplacement (ou *imputation*) des valeurs manquantes ([**Figure 1**](#figure-1)). C'est une étape importante qui permet de préserver la puissance statistique d'un jeux de données

    | Before Imputation                                                                                                          | After Imputation                                                                                                            |
    | -------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
    | ![Missing Values BEFORE Imputation](/images/ghg_flux_data_missing_data_raw_heatmap.png "Missing Values BEFORE Imputation") | ![Missing Values BEFORE Imputation](/images/ghg_flux_data_missing_data_clean_heatmap.png "Missing Values AFTER Imputation") |

    **Figure 1**:  The replacement of missing values by mathematical approach. Here, when the value of a replicated measurement (usually seven (7) replicates) was missing (*top*), it was replaced by the "mean" value of the other replicated samples. The remaining missing values (*bottom*) represent non-replicated data which can be imputed using more powerfull machine learning approaches (not detailed here).

3. Transformation des variables pour obtenir une distribution dite « normale » ([**Figure 2**](#figure-2)). Le but est donc de diminuer le nombre de valeurs dite « extrêmes », c'est-à-dire des valeurs très éloignées de la valeur moyenne.

    ![N2O Data Transformations](/images/n2o_flux_distrib_violinplots.png "N2O Data Transformations")

    **Figure 2**: Mathematical transformation of nitrous oxide (N<sub>2</sub>O) emissions. The various « violin plots » represent different transformation of the raw data in order to seek « normal distribution » *(e.g.* standardised transformation, square-root transformation, *etc.*). The aim is to reach a symetrical distribution and thus avoid (left- or right-handed) tails.

De manière plus générale, il s'agit de préparer les jeux de données pour les étapes d'analyses statistiques et de modélisation (« *machine learning* »)

---

### Tableau de bord

Un tableau de bord (« *dashboard* ») interactif a été construit pour observer et tester les émissions des gaz à effet de serrre sous différentes conditions. Cette **application web** appelée « Greenhouse Gas Estimation Portal » a été codé avec la librairie Python [Streamlit](https://www.streamlit.io/ "Streamlit.io") et déployée sur [Heroku.com](https://www.heroku.com/ "Heroku.com"). L'application peut être accédée par le [lien suivant](https://exam-piscine-heroku-redone.herokuapp.com/ "Greenhouse Gas Estimation Portal App").

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
- analyses statistiques de type « REML » (*restriction likelihood*)
- send results to the user by email

Des captures d'ecran sont disponibles dans la ([**Figure 3**](#figure-3)).
Elles reflètent certaines des options disponibles à l'utilisateur.

| Login to GHG Estimation Portal                                                                                     | Variable Selection                                                                                                |
| ------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| ![Login Screenshot](/images/streamlit_login_screenshot.png "Login Screenshot")                                     | ![Variable Selection Screenshot](/images/streamlit_vars_selection_screenshot.png "Variable Selection Screenshot") |
| Time-Series Analysis                                                                                               | Email Option                                                                                                      |
| ![Time-Series Analysis Screenshot](/images/streamlit_time_series_screenshot.png "Time-Series Analysis Screenshot") | ![Email Option Screenshot](/images/streamlit_email_screenshot.png "Email Option Screenshot")                      |

**Figure 3**: Screenshots of various steps and options available to the user on the web application « Greenhouse Gas Estimation Portal ».

Note: Dans l'avenir, une section de *machine learning* sera disponible. Il sera en autre possible de procéder à une modélisation temporelle des emissions des gaz à effet de serre.

P.S: application non disponible au moment de la préparation de cette page (10/01/2021).

---

---

## Mes projets passés

---

### Modélisation des émissions des gaz à effet de serre

Analyse des émissions de gaz à effet de serre dans des conditions de concentrations atmosphériques en CO<sub>2</sub> élevées.

Voir la section [EucFACE Site Presentation](/eucface_site_presentation.md) pour une description détailléé du projet, incluant l'hypothèse scientifique testée, matériel et méthodes et les réferences bibliographiques principales.

[![Inside a ring at EucFACE](http://img.youtube.com/vi/K8RTVdijc0o/0.jpg)](http://www.youtube.com/watch?v=K8RTVdijc0o "EucFACE Crane Shot - YouTube.com")

**Video 1**: Moving up a ring at the EucFACE site.

![EucFACE Canopy View](/images/Completed_EucFace_Rings.jpg "EucFACE Canopy View")

**Picture 1**: Canopy view from Ring 1 at the EucFACE Site.

Une analyse temporelle (*time-series analysis*) a été appliquée ([**Figure 4**](#figure-4)) pour tester l'hypothèse scientifique de départ:

> « Quel est l'effet de l'augmentation du dioxide de carbone (CO<sub>2</sub>) dans l'atmosphère sur les émissions des gaz à effet de serre? »

![Monthly GHG Emissions](/images/GHG_fluxes_time_series.png "Monthly GHG Emissions")

**Figure 4**: Greenhouse gas (GHG) emissions for méthane (CH<sub>4</sub> flux - panel a), nitrous oxide (N<sub>2</sub>O flux - panel b) and carbon dioxide (CO<sub>2</sub> flux - panel c). Ambient (blue line) and elevated (red line) atmospherique CO<sub>2</sub> concentrations represent the « treatment » applied to test the scientific hypothesis investigated. There is already a strong visible link between the intensity of GHG emissions and the intensity of the rainfall events (panel d).

Ces travaux ont été publiés par [Martins, Nazaries *et al.*, 2021](/scientific_publications.md "[Martins, Nazaries *et al.*, 2021 - Functional Ecology").

---

### Élaboration d'un indicateur multiple de performance (KPI)

Un conglomérat d’agriculteurs australiens a financé une étude dans laquelle j’ai été chargé d’identifier les facteurs biologiques et environnementaux qui sont susceptible d’améliorer les rendements de blé en lien avec les pratiques d’agricultures communes en Australie (chaume brûlé, fertilisation, pâturage, labourage, etc.). Cette expérience était constituée de sites dans plusieurs régions/états de l’Australie. Un ample effort de coordination a été primordial au bon déroulement de cette étude, ainsi qu’une bonne communication avec les propriétaires des terres et les gouvernements locaux. J’ai aussi eu la charge de tenir notre base de données à jour et disponible auprès de mes collaborateurs.

Au terme de mes analyses, j’ai défini un indicateur de performance qui révèle comment chaque pratique agricole impacte le recyclage des nutriments dans le sol, en d’autres mots, la qualité et la quantité des récoltes de blé. Durant ce projet, j’ai appris à ajuster mon discours de manière à le rendre plus compréhensible (travail de vulgarisation) auprès de non-spécialistes, c’est-à-dire les agriculteurs et les acteurs locaux. Voir la publication [Nazaries *et al.*, 2021](scientific_publications.md "Nazaries *et al.*, 2021 - Agriculture, Ecosystems and Environment").

---

### Modélisation géographique

J’ai complété une étude décrivant les étapes de modélisation nécessaire pour prédire la répartition géographique de microbes dans le sol responsables de la réduction des concentrations de méthane (un puissant gaz effet de serre) dans l’atmosphère.
Grâce au sponsor du gouvernement écossais, une grande base de données a été formée après un sondage du sol dans toute l’Écosse. L’objectif a été de collecter plusieurs données environnementales (température, pluies, humidité, nutriments, fertilité, composition minérale, etc.) pour mieux décrire les procédés biologiques dans le sol. J’ai réparti les tâches de modélisation entre mes collaborateurs pour faire avancer le processus intellectuel. Une fois les analyses terminées, j’ai écrit un article scientifique pour présenter nos résultats. Cela a été une occasion fantastique pour apprendre à manier des méthodes statistiques pointues. Voir la publication [Nazaries *et al.*, 2018](/documents/scientific_publications/Nazaries_et_al_2018.pdf "Nazaries *et al.*, 2018 - Soil Biology and Biochemistry").

Notamment, j’ai rendu publique notre base de données sur le site figshare.com pour permettre à d’autres équipes d’utiliser mes données pour leurs propres études.

---

### Coopération internationale

Après avoir établi une collaboration avec des chercheurs d’Australie, Angleterre, Écosse et USA, j’ai mis en place une série de protocoles afin d’organiser les tâches administratives et techniques nécessaire pour remplir l’objectif de la mission (mesure des gaz à effet de serre). J’ai aussi eu la responsabilité de former les collaborateurs et de coordonner les équipes pour garantir les délivrables.
Une fois les données générées, je les ai agrégé et préparé : enregistrement dans une base de données ; nettoyage ; détection de données aberrantes et de données manquantes ; transformation/normalisation ; exploration. Enfin, j’ai conduit toutes les analyses statistiques, j’ai préparé les résultats (tables et graphes) et j’ai décrit les conclusions dans un rapport de mission. Particulièrement, j’ai présenté les conclusions de cette étude devant les « clients », c’est-à-dire les organismes privés et publiques qui ont financés ma recherche. Grâce à cette expérience, j’ai réussi à gérer des projets de bout-en-bout ainsi qu’à faire face à des problèmes administratifs, techniques et humains. Un des articles issu de cette collaboration est [Martins, Nazaries *et al.*, 2017](/documents/scientific_publications/Martins_et_al_2017.pdf).

---

---

## Mes *Scripts/Gists*

---

### Créer un environnement virtuel avec Python

Dans tout projet data, il est important de pouvoir créer un **environnement technique** reproductible par une autre personne ou sur un autre ordinateur. Ceci signifie que le langage de programmation (Python, par example) et la version des librairies utilisées lors de l'ecriture d'un script doivent être établis dès le début du projet.

Pour cette raison, il est courant de créer un **environnement virtuel** qui va contenir toutes ces données ainsi que la structure des dossiers contenant les fichiers essentiels au projet.

Voici donc un **script**, ou ***gist***, qui détaille les differents étapes de la création d'un environnement virtuel avec Python. Dans ce cas précis, le module "**venv**" de **Python** est utilisé.

Le *gist* est disponible sur ce [ici](/documents/scripts_gists/create_a_virtual_environment_with_python.md "Create a Virtual Environment with Python - GitHub Pages") ainsi que sur [GitHub Gist](https://gist.github.com/loic-nazaries "Create a Virtual Environment with Python - GitHub Gist").

---

### Créer un environnement virtuel avec Conda

Ici, la gestion des librairies Python nécessaires au projet data sont gérées par [**Conda**](https://docs.conda.io/en/latest/ "Conda documentation"). Il s'agit du même principe de création d'un **environment virtuel**.

La difference avec un le module "venv" est que la version de Python (par example version 2.7 *vs.* 3.9.1) est aussi installée.

Le *gist* est disponible sur ce [ici](/documents/scripts_gists/create_a_virtual_environment_with_conda.md "Create a Virtual Environment with Conda - GitHub Pages") ainsi que sur [GitHub Gist](https://gist.github.com/loic-nazaries "Create a Virtual Environment with Conda - GitHub Gist").

---

### Créer un dépôt de projet avec GitHub

Bientôt !

---

### Déployer une application web avec Heroku

Bientôt !

---

### Pipeline d'un projet de *Data Science*

Bientôt!

---

---

## Autres réalisations professionnelles

---

### Maître de thèse

J’ai eu la responsabilité de superviser deux étudiantes. Je les ai soutenues dans la définition et la construction de leur projet de recherche : identification des lacunes scientifiques ; mise en place des protocoles ; formation technique et littéraire ; analyse des données et écriture de leur manuscrit de thèse. Le plus gratifiant a été quand j’ai assisté à leur cérémonie de remise des diplômes.

---

### Revue littéraire

J’ai recherché sur internet des centaines d’études et d’articles en rapport avec mon thème de recherche : les émissions biologiques du gaz méthane qui produit un effet de serre 31 fois plus puissant que the dioxide de carbone (CO<sub>2</sub>). J’ai dû décrire l’origine des bactéries responsables du cycle du méthane entre l’atmosphère et le sol ainsi que leurs propriétés génétiques et biochimiques. J’ai concentré mes trouvailles en une large revue publiée dans un journal scientifique (voir [Nazaries *et al.*, 2013](/documents/scientific_publications/Nazaries_et_al_2013b.pdf "Nazaries *et al. 2013 - Environmental Microbiology")). Methane, microbes and models: fundamental understanding of the soil methane cycle for future predictions. Journal of Environmental Microbiology. doi:<https://10.1111/1462-2920.12149>.

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

### Mes publications scientifiques

Cliqué [ici](/scientific_publications.md) pour accéder à la liste des publications.
