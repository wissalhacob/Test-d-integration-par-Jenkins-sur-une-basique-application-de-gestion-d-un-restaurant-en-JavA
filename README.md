# Application de Gestion de Restaurant

## Description
Cette application de gestion de restaurant est programmée en Java en utilisant Java Swing pour l'interface utilisateur. L'application permet de gérer les commandes, les menus et les réservations de manière efficace. Ce projet inclut également une intégration continue et des tests d'intégration avec Jenkins.

## Fonctionnalités
- Gestion des commandes
- Gestion des menus
- Gestion des réservations
- Interface utilisateur graphique avec Java Swing

## Prérequis
- Java JDK 8 ou supérieur
- Maven 3.6 ou supérieur
- Jenkins (dernière version recommandée)
- Git

**I. L’outil d’intégration**
******L’outil choisi : Jenkins**
Jenkins est souvent privilégié pour les tests d'intégration en raison de sa flexibilité, de sa facilité d'utilisation, de ses capacités d'automatisation, de sa large gamme de plugins et de son support continu par une communauté active. Ces avantages font de Jenkins un choix solide pour améliorer les processus de tests d'intégration.
**////Installation sur Windows**
//Conditions préalables
//Configuration matérielle minimale :
-256 Mo de RAM
-1 Go d'espace disque (10 Go recommandés si vous exécutez Jenkins en tant que conteneur Docker)
//Configuration matérielle recommandée pour une petite équipe :
-4 Go de RAM ou plus
-50 Go d'espace disque ou plus
**Étapes d'installation à l'aide du programme d'installation Windows MSI**
**Téléchargement :**
-Rendez-vous sur la section Windows de la page de téléchargement de Jenkins pour obtenir une version LTS ou une version hebdomadaire du programme d'installation Windows.
****Installation :**
Une fois le téléchargement terminé, ouvrez le programme d'installation Windows et suivez les étapes ci-dessous pour installer Jenkins.
**Assistant de configuration :**
Lors de l'ouverture du programme d'installation Windows, un assistant de configuration apparaît. Cliquez sur "Suivant" dans l'assistant pour démarrer l'installation.

**Étape 2** : Sélectionnez le dossier de destination
Sélectionnez le dossier de destination pour stocker votre installation Jenkins et cliquez sur Suivant pour continuer.
**Étape 3: **Identifiants de connexion au service
Lors de l'installation de Jenkins, il est recommandé d'installer et d'exécuter Jenkins en tant que service Windows indépendant à l'aide d'un utilisateur local ou de domaine car il est beaucoup plus sûr que d'exécuter Jenkins à l'aide de LocalSystem (équivalent Windows de root) qui accordera à Jenkins un accès complet à votre machine et services.
Pour exécuter le service Jenkins à l'aide d'un utilisateur local ou de domaine, spécifiez le nom d'utilisateur et le mot de passe du domaine avec lequel vous souhaitez exécuter Jenkins, cliquez sur Test Credentials pour tester vos informations d'identification de domaine et cliquez sur Next. 
**Étape 4 :**sélection du port
Spécifiez le port sur lequel Jenkins sera exécuté, bouton Test Port pour valider si le port spécifié est libre sur votre machine ou non. Par conséquent, si le port est libre, il affichera une coche verte comme indiqué ci-dessous, puis cliquez sur Suivant. 

**Étape 5 :** Sélectionnez le répertoire d'accueil Java
Le processus d'installation recherche Java sur votre machine et pré-remplit la boîte de dialogue avec le répertoire de base Java. Si la version Java nécessaire n'est pas installée sur votre machine, vous serez invité à l'installer.
Une fois votre répertoire d'accueil Java sélectionné, cliquez sur Suivant pour continuer.

**Étape 6 :** Configuration personnalisée
Sélectionnez les autres services qui doivent être installés avec Jenkins et cliquez sur Suivant.

**Étape 7 :** Installer Jenkins
Cliquez sur le bouton Installer pour lancer l'installation de Jenkins.
De plus, cliquer sur le bouton Installer affichera la barre de progression de l'installation, comme indiqué ci-dessous :
**Étape 8 :** terminer l'installation de Jenkins
Une fois l'installation terminée, cliquez sur Terminer pour terminer l'installation.

Jenkins sera installé en tant que service Windows. Vous pouvez le valider en parcourant la section des services, comme indiqué ci-dessous :

L'installation ne devrait prendre que quelques secondes. Immédiatement après, le programme ouvre localhost :8080 dans votre navigateur par défaut. Cela donne accès à une interface Web, que vous pouvez utiliser pour configurer Jenkins. Mais vous devez d'abord prendre une mesure de sécurité : Jenkins a généré un mot de passe aléatoire pour vous. Celui-ci se trouve dans le répertoire Jenkins, dans le dossier Secrets et enfin dans le fichier initialAdminPassword. Ce fichier peut être ouvert avec n'importe quel éditeur de texte. Copiez la chaîne de caractères et collez-la dans la zone ad hoc de l'interface Web.
Avant de pouvoir commencer à utiliser Jenkins, l'application vous invite à entrer un code généré dans le masque.
Le fichier de mot de passe peut être ouvert avec n'importe quel éditeur.
Maintenant, il est temps de configurer Jenkins. L'assistant de configuration vous demandera si vous souhaitez choisir les plugins à installer ou si vous préférez utiliser le paramétrage par défaut intégrant déjà toutes les améliorations majeures. Si vous utilisez Jenkins pour la première fois, ce choix par défaut vous conviendra certainement. Et ne vous inquiétez pas : des plugins supplémentaires peuvent être facilement installés plus tard.
La sélection par défaut de plugins inclut les améliorations les plus importantes.
Créez ensuite un premier utilisateur. Si vous travaillez seul sur votre projet, vous pouvez ignorer cette étape et utiliser simplement Jenkins en tant qu'administrateur. Dans les paramètres de Jenkins, vous pourrez toujours créer ultérieurement de nouveaux utilisateurs avec des droits différents. Lors de la dernière étape de la configuration, vous avez encore la possibilité de spécifier une URL Jenkins. Le champ correspondant comporte par défaut localhost :8080. Si vous avez installé Jenkins sur un serveur (ce qui devrait être le cas dans un environnement de travail professionnel), indiquez ici le bon chemin d'accès au répertoire Jenkins. Enregistrez les données saisies et terminez la configuration.
Presentation de Jenkins :
Vous démarrez Jenkins avec un environnement de travail complètement vide. Pour démarrer un nouveau projet d’intégration continue, vous devez créer un nouveau job. Pour ce faire, utilisez l’icône visible au milieu de la fenêtre (« create new jobs ») ou l’option de menu « New Item », que vous trouverez à gauche.
Ensuite, il est nécessaire de donner un nom à votre projet et de choisir ce que vous voulez atteindre :
•	Freestyle project : Jenkins associe la gestion des versions à un système de build.
•	Pipeline : créez un pipeline entre plusieurs agents de build.
•	Projet multi-configuration : Choisissez cette option si vous avez un projet qui nécessite une variété de paramètres, par exemple parce que vous utilisez plusieurs environnements de test.
•	Folder : un dossier est un conteneur dans lequel vous pouvez stocker des objets imbriqués.
•	GitHub Organization : cette option fait une recherche dans tous les référentiels d'un compte sur GitHub.
•	Multibranch Pipeline : vous permet de créer directement plusieurs pipelines.

À la page suivante, vous avez de nombreuses options de paramétrage. Et de configuration du projet. 

Dans le tableau de bord de Jenkins, vous pouvez voir tous les projets sur lesquels vous travaillez. Ici aussi, le programme matérialise l'état du projet par une couleur. Vous obtenez également des informations sur la Stabilité du build sous la forme d'un bulletin météo. Il s’agit d’une statistique sur la stabilité moyenne des builds du projet. Si plus de 80 % de vos builds réussissent, vous verrez un soleil. En dessous de cette valeur, la météo symbolique se dégrade.

**************************II.	Création de l’application :**********************
//Le langage choisi : Java(JavaSwing)
Java et Java Swing ont été choisis pour créer l'application en raison de la polyvalence de Java et de la richesse de Java Swing pour créer une interface utilisateur conviviale. Ensemble, ils offrent la portabilité du code, des composants graphiques prêts à l'emploi et une flexibilité de personnalisation. De plus, ils bénéficient d'une grande communauté de développeurs pour le support et les ressources en ligne.

L'application développée en utilisant Java Swing est une solution de gestion pour une clinique. Elle comprend trois principales classes : Home, Médecins et Patient.
********La classe Home est la classe principale de l'application. Elle offre aux utilisateurs la possibilité de choisir entre deux rôles : médecin ou patient. En fonction de leur choix, ils seront redirigés vers l'interface correspondante.
********La classe Médecins représente les fonctionnalités destinées aux administrateurs de la clinique. Elle leur permet d'ajouter, de modifier et de supprimer les données des médecins. Les informations concernant chaque médecin incluent le nom, l'adresse, le numéro de téléphone, etc.
********La classe Patient offre des fonctionnalités similaires à celles de la classe Médecin, mais spécifiquement pour les patients. Les administrateurs peuvent ajouter, modifier et supprimer les informations des patients, telles que le nom, l'adresse, le numéro de téléphone, etc.
Une fonctionnalité importante de l'application est la liaison entre les classes Médecin et Patient. Dans les données d'un patient, il y a une liste déroulante permettant de choisir le médecin traitant en utilisant le numéro d'identification national (CIN) du médecin. Cela permet de garder une trace du médecin responsable du suivi et du traitement de chaque patient.
Grâce à cette application, les administrateurs de la clinique peuvent gérer efficacement les données des médecins et des patients, en ajoutant, en modifiant ou en supprimant les informations nécessaires. La liaison entre les médecins et les patients facilite la coordination et le suivi médical au sein de la clinique.
**l’insertion des fichiers  .jar nécessaires :**
•	ant.jar : C'est le fichier JAR principal d’Apache Ant, un outil de construction de logiciels. Il contient les bibliothèques nécessaires pour exécuter et configurer des tâches de construction automatisées. Ant fournit une approche basée sur XML pour la compilation, le déploiement, les tests et d'autres opérations liées au développement de logiciels.
•	ant-junit.jar : Ce fichier JAR est utilisé en conjonction avec Apache Ant pour exécuter des tests unitaires écrits avec JUnit. Il contient les classes et les dépendances nécessaires pour exécuter les tests JUnit lors de la construction du projet avec Ant.
•	hamcrest-core.jar : Hamcrest est un framework de correspondance d'objets utilisé dans les tests unitaires. Le fichier JAR hamcrest-core.jar contient les classes centrales de Hamcrest, qui permettent de définir des assertions et des correspondances plus expressives lors de l'écriture de tests avec des frameworks tels que JUnit.
•	jenkins-cli.jar : C'est le fichier JAR pour l'interface en ligne de commande (CLI) de Jenkins, un serveur d'intégration continue. Il permet d'interagir avec Jenkins à partir de la ligne de commande, ce qui facilite l'automatisation de certaines tâches administratives telles que la création de projets, le lancement de builds, etc.
•	junit.jar : Ce fichier JAR contient les classes et les dépendances nécessaires pour exécuter des tests unitaires avec JUnit, l'un des frameworks de test les plus populaires pour Java. JUnit fournit des annotations, des assertions et des fonctionnalités pour l'écriture et l'exécution de tests unitaires de manière structurée.
•	mysql-connector.jar : C'est le fichier JAR pour le pilote JDBC (Java Database Connectivity) de MySQL. Il permet à une application Java de se connecter à une base de données MySQL et d'interagir avec elle en utilisant des requêtes SQL. Le fichier JAR contient les classes nécessaires pour établir une connexion, exécuter des requêtes et récupérer des résultats à partir de la base de données.
**Git et github :**
Comment utiliser Git dans Eclipse ?

Git est un système de versionning de code, c'est-à-dire un logiciel qui va garder l'historique des modifications d'un code source. Cet historique est riche, car il contient des commentaires, les auteurs des modifications, et souvent plusieurs historiques parallèles (branches) lorsque plusieurs versions d'une même application sont développées en même temps.
En allant dans le menu Window -> Perspective -> Open Perspective -> Other... on peut voir l’item Git.. Le package explorer est remplacé par un explorateur de dépôts Git . maintenant on arrive  à la fenêtre ci-dessous.

En cliquant sur Create a new local Git repository on peut créer un répertoire locale.
Comment utiliser GitHub avec git ?
GitHub est un dépôt public Git, accessible sur Internet. Tout le monde peut créer son projet gratuitement, pourvu qu'il soit open source et accessible aux autres. Sur GitHub, on peut trouver du code utilisé par Facebook, Red Hat, et d’autres entreprises bien connues. Néanmoins, tous les projets GitHub ne sont pas nécessairement open source ni même publics. Certains projets sont privés ou accessibles à certaines personnes seulement. GitHub propose alors une tarification en fonction du nombre de projets et d'utilisateurs.

Jusqu’à présent les « commit » effectués, l’ont été dans le dépôt local sur la machine du développeur. Pour partager ce projet dans GitHub, il convient de le publier dans le dépôt distant du serveur. Pour le faire avec Git sous éclipse il faut sélectionner le projet dans l’explorateur et ensuite utiliser le menu contextuel (Click avec le bouton droit de la souris).
Utiliser le menu: Team / Push Branch master.

En ajoute l’url du repository créé dans GitHub et automatiquement le host et le repository s’ajoutent et on saisit le nom d’utilisation et le mot de passe de notre compte GitHub.
On utilise le bouton « Finish » pour finaliser la publication. À ce stade le dernier commit du projet est publié sur le serveur.

Le lien de notre repository : https://github.com/wissalhacob/test-integration

**III.	Les tests d’intégration continues :**
**Article Jenkins :**
///On crée un article Jenkins de type pipeline :
///On ajoute l’url de notre GitHub repository dans la configuration de l’article 
///Dans la configuration de Jenkins en ajoute les installations nécessaires 
///Générer un fichier build.xml du projet 
 Le fichier "build.xml" est utilisé pour décrire les étapes de construction d'un projet Java, y compris les tests d'intégration. Il fournit une structure et des instructions pour automatiser le processus de construction, permettant ainsi de compiler le code, d'exécuter les tests et de générer les artefacts finaux du projet.
Ajouter :               
-${build.dir} : Cette variable fait référence au répertoire de construction (build directory). Il est utilisé pour inclure les fichiers compilés ou générés lors de la construction du projet dans le classpath.
-${lib.dir}/* : Cette expression fait référence à un répertoire appelé "lib.dir" contenant des fichiers JAR. L'étoile "*" est utilisée pour inclure tous les fichiers présents dans ce répertoire dans le classpath. Il est courant d'inclure les dépendances externes d'un projet dans un répertoire "lib" et de les ajouter au classpath de cette manière.
-C:\Programmes\apache-ant-1.9.16-bin\apache-ant-1.9.16\lib\junit-4.13.2-javadoc.jar : Il s'agit d'un chemin absolu vers le fichier JAR "junit-4.13.2-javadoc.jar". Ce fichier JAR est ajouté au classpath pour inclure la documentation de JUnit lors de l'exécution des tests. Cela permet d'accéder à la documentation Javadoc associée à JUnit lors de l'exécution des tests.

la propriété "classpath" définit les éléments à inclure dans le classpath, y compris les fichiers générés lors de la construction, les dépendances du projet et un fichier JAR de documentation spécifique (junit-4.13.2-javadoc.jar).
La propriété "classpath" est définie avec la valeur du répertoire de construction (build.dir) et du répertoire des bibliothèques (lib.dir) concaténés avec tous les fichiers présents dans le répertoire spécifié par la propriété "test.dir".
La propriété "test.dir" est définie avec le chemin du répertoire contenant les fichiers de test d'intégration. Dans cet exemple, le chemin est "C:\Users\hacob\Desktop\eclipse\Clinique/test".

Un répertoire "reports" est créé dans le répertoire de construction (build.dir). Ce répertoire sera utilisé pour stocker les rapports de test.
La tâche "junit" est utilisée pour exécuter les tests d'intégration. Les éléments suivants sont configurés dans la tâche :
Le chemin de classe (classpath) est spécifié en utilisant la propriété "${classpath}" qui a été définie précédemment.
Un élément "formatter" est ajouté pour spécifier que le rapport de test doit être généré au format XML.
La tâche "batchtest" est utilisée pour définir les fichiers de test à exécuter. Elle utilise un élément "fileset" pour spécifier le répertoire "${test.dir}" et inclut tous les fichiers correspondant au motif "**/*Test.java". Cela signifie que tous les fichiers de test se terminant par "Test.java" dans le répertoire "${test.dir}" seront exécutés.
Les résultats des tests sont enregistrés dans le répertoire "${build.dir}/reports" à l'aide de l'attribut "todir" de la tâche "batchtest".
Ce code exécute les tests d'intégration en utilisant JUnit comme framework de test. Les résultats des tests sont stockés dans le répertoire de construction et formatés en XML.

 Créer un fichier Jenkinsfile dans le chemin du projet 

•	"clean" : Cette étape utilise la commande "ant clean" pour nettoyer votre projet Java Swing. Cela peut inclure la suppression des fichiers générés lors de la compilation précédente ou tout autre nettoyage spécifique à votre projet.
•	"compile" : Cette étape utilise la commande "ant compile" pour compiler votre projet Java Swing. Cela permet de générer les fichiers .class à partir des fichiers source de votre projet.
•	"Test" : Cette étape utilise la commande "ant test" pour exécuter les tests de votre projet Java. Cette étape est destinée à l'exécution des tests unitaires ou d'autres tests automatisés pour vérifier le bon fonctionnement de votre application.
•	"Package" : Cette étape utilise la commande "ant package" pour créer un package ou un artefact de votre projet Java. Cela peut être un fichier JAR ou tout autre format d'archive contenant les fichiers nécessaires à votre application.
•	"Build" : Cette étape utilise la commande "ant build" ou "ant jar" pour construire votre projet Java. Cela peut inclure la compilation, les tests, le packaging et d'autres tâches nécessaires pour préparer votre projet pour le déploiement.
•	"Run" : Cette étape utilise la commande "ant run" pour exécuter votre projet Java. Cela permet de lancer votre application et de vérifier son bon fonctionnement.
Chaque étape est définie dans un bloc "stage" avec une liste d'étapes spécifiques à exécuter dans le bloc "steps". Les étapes sont exécutées séquentiellement, ce qui signifie que chaque étape est exécutée après l'achèvement de l'étape précédente.
Il convient de noter que les étapes de "Build" et "Run" mentionnées dans le ne sont pas spécifiques aux tests d'intégration. Elles peuvent être utiles pour d'autres phases du processus de développement, telles que la construction de l'application finale et son exécution dans un environnement réel.
Lancer un Build :
![image](https://github.com/user-attachments/assets/2eb84737-fc22-46c6-8df3-3eac857c08cd)
