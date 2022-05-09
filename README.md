# TP02 - PompeAEssence

## 1 - Directives

### 1.1 - Déroulement du TP

- Le projet est réalisé en équipe de 2 personnes
- Vous devez utiliser Git pour gérer vos sources
- Vous devez utiliser SharePoint pour gérer votre document de rapport (Onglet "Fichiers" de votre équipe Teams)
- La remise du travail doit être effectuée sur et à la date indiquée  sur la plateforme d'enseignement

### 1.2 - À remettre sur la plateforme d'enseignement

- Un document word contenant le détail du projet
- Votre code source
- Le lien YouTube de votre vidéo de présentation

### 1.3 - Structure de la remise

- Vous devez remplir le fichier "AUTHORS.md".
  Il donne le nom et matricule des équipiers
- Votre code source doit être dans le répertoire  ```src``` du présent dépôt Git
- Le répertoire source doit suivre la structure d’un projet Platform.io
- Vous devez fournir une vidéo de 5 minutes illustrant le circuit, le code et le fonctionnement :
  - La vidéo doit être déposée sur Youtube avec une option de partage « non listée »
  - Le lien de la vidéo doit être indiqué dans le document word et dans le fichier "AUTHORS.md"

- Le répertoire "documents" doit contenir votre rapport de TP

### 1.4 - Évaluation

L'évaluation du travail est effectuée par les enseignants de l'UE en se basant sur :

- L'historique de Git et de Teams/Sharepoint font office de référence pour évaluer la proportion du travail effectué par chaque équipier

- La qualité et le contenu du code source :

  - Conformité du code et des normes d'écriture utilisées dans le cours
  - Fonctionnalité du code
  - Facilité de lecture du code
  - Modularité
  - Modèle objet
  - Paramétrisation du code
  - Utilisation de constantes
  - Utilisation de fichiers de configuration
  - etc.

- La qualité et le contenu du document word :
  
  - Français
  - Schéma
  - Clarté et précision des explications
  - Mise en page
  - Page de présentation
  - etc.

- La qualité et le contenu de la présentation vidéo :

  - Vidéo
  - Audio
  - Explication orale
  - etc.

Tout partage de code, d'explication, de bouts de texte, etc. est considéré comme du plagiat. Pour plus de détails, consultez le site (et ses vidéos) [Sois intègre du Cégep de Sainte-Foy](http://csfoy.ca/soisintegre) ainsi que [l'article 6.1.12 de la PÉA](https://www.csfoy.ca/fileadmin/documents/notre_cegep/politiques_et_reglements/5.9_PolitiqueEvaluationApprentissages_2019.pdf)

## 2 - Description du projet

L’accommodation "BonService" vient de faire installer une pompe à essence pour augmenter l’achalandage de son commerce.

Votre tâche générale consiste à mettre en place un programme d’affichage d’achat de carburant.

Ce système comprend :

- Un afficheur 4 digits (de 7-segments) qui montre la quantité d’essence ou le prix à payer. Toutes les valeurs sont arrondies au centième.
- Un site web permettant de modifier le prix du litre d’essence
- Pour accéder au site web, votre système doit servir de point d’accès
- Le prix du litre est sauvegardé dans un fichier au format JSON sur la mémoire flash de votre système
- Un bouton poussoir servant à simuler le pistolet de la pompe
- Un bouton poussoir servant à simuler le paiement et la fin de la transaction (rôle du préposé aux pompes)

### 2.1 - Procédures pour la clientèle

À l’arrivée d’un client devant le distributeur, les valeurs sont évidemment « 00.00 ». On affiche toujours deux chiffres avant le point et deux après. Dans votre cas, le point décimal sera simulé par les « : » présents entre les digits 2 et 3.

Quand le pistolet de la pompe est actionné (bouton appuyé), le remplissage débute : le prix s’affiche et augmente dépendamment du prix du litre. Le volume d’essence s’incrémente de 23 litres par minute.
Quand le pistolet de la pompe est relâché, le remplissage cesse.

Après 5 secondes de repos du pistolet (bouton relâché), l’affichage montre, en alternance, le prix à payer et la quantité d’essence. La fréquence d’affichage est de 1000 millisecondes.

Afin de simplifier le problème, le remplissage s’arrête quand le premier entre le volume ou le prix atteint 99.99.

Lorsque le bouton est appuyé à nouveau, le cycle de remplissage se poursuit.

### 2.2 - Procédures pour la gestion des pompes

Lorsque le client a terminé, le préposé aux pompes remet le tout à ZÉRO. Cette action sera simulée par le deuxième bouton indiquant la fin de transaction. La pompe sera prête pour le prochain client.

### 2.3 - Modification du prix du litre

Une interface web est offerte au préposé pour modifier le prix à la pompe. A l’aide de son téléphone cellulaire, il se connecte au réseau offert par la pompe. Il peut ensuite consulter le prix du litre affiché à la pompe ou le modifier.

Si aucun prix n’a été enregistré dans votre système, la pompe doit afficher « 88:88 » et ne pas permettre le service afin de forcer le préposer à indiquer le prix du litre.

(Optionnel : cette dernière action ne peut pas se faire si la pompe est en cours d'utilisation par un client + 5%)

## 3 - Description détaillée du document à remettre

Le document word doit décrire le contexte du projet, sa planification, la répartition des tâches avec un registre des heures passées, les schémas du montage, les diagrammes UML pertinents ainsi que l'inventaire des composants et une estimation des coûts pour une pompe.

## 4 - Répartition des points

1. Document word : (35%)
  - Contexte du projet (5%)
  - Planification, attribution des tâches (5%)
  - Description des étapes du projet (5%)
  - Diagramme de classes (5%)
  - Schéma du montage (5%)
  - Inventaire des pièces et évaluation du coût (5%)
  - Registre des heures consacrées au projet (5%). Le registre doit indiquer la répartition des tâches. Le registre doit montrer les tâches respectives que chaque personne aura fait avec le nombre d’heures par tâche.

2. Vidéo de 5 minutes illustrant le fonctionnement (15%)
  - Présentation rapide du circuit (5%)
  - Présentation rapide de la structure du code et des choix de conception (5%)
  - Présentation du fonctionnement (5%)

3. Code (50%)
  - Bon fonctionnement du programme (30%)
    - Incrémentation du nombre de litres (5%)
    - Simulation du paiement (2,5%)
    - Affichage du prix à payer durant le service (5%)
    - Alternance du prix à payer et du nombre de litres (5%)
    - Site de saisie du prix du litre (5%)
    - Lecture / Sauvegarde du prix du litre (5%)
    - Validation de la présence du prix (2,5%)
  - Respect des bonnes pratiques de programmation modulaire et orientée objet (20%)
