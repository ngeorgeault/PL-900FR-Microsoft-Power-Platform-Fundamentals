---
lab:
    title: 'Labo 04 : Power BI'
    module: 'Module XX : Build de Power Apps'
---

# PL-900 : Microsoft Power Platform : Notions fondamentales
## Module X, atelier 4 : Power BI

Scénario
========

Bellows College est un organisme éducatif disposant de plusieurs bâtiments sur le campus. Les visiteurs du campus sont actuellement enregistrés dans des journaux papier. Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données sur les visites sur l’ensemble du campus. 

L’administration du campus souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous allez créer des applications et effectuer une automatisation pour permettre au personnel d’administration et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus. 

Dans cet atelier, vous allez créer un tableau de bord Power BI qui visualise les données sur les visites sur le campus.

Étapes générales de l’atelier
======================

Pour concevoir et créer le tableau de bord Power BI vous allez procéder comme suit:

-   Connectez-vous à Common Data Service 
-   Transformez les données pour inclure des descriptions conviviales pour les enregistrements associés (recherches)
-    Créez et publiez un rapport avec diverses visualisations des informations sur les visites du campus
-    Utilisez un langage naturel pour créer des visualisations supplémentaires
-    Créer un affichage mobile


## Conditions préalables

* Réalisation de l’atelier 1 - Modélisation de données

Points à prendre en compte avant de commencer
-----------------------------------

-   À quel public ce rapport est-il destiné ?
-   Comment les participants utiliseront-t-il le rapport ? Appareil courant ? Emplacement ?
-   Avez-vous suffisamment de données à visualiser ?
-   Quelles sont les caractéristiques qu’il est possible d’utiliser pour analyser les données sur les visites ?

Exercice n°1 : Créer des rapports Power BI 
===============================

**Objectif :** dans cet exercice, vous allez créer un rapport Power BI basé sur les données de la base de données Common Data Service.

Tâche n°1 : Préparer les données
---------------------------

1.  Découvrez l’URL de votre organisation

    * Accédez au Centre d’administration Power Platform sur https://aka.ms/ppac.
    * Dans le volet de navigation de gauche, sélectionnez Environnements, puis l’environnement cible.
    * Cliquez avec le bouton droit sur l’**URL de l’environnement** dans le panneau **Détails**, puis sélectionnez **Copier le lien**.
2. Si vous n’avez pas installé Power BI Desktop, accédez à https://aka.ms/pbidesktopstore pour télécharger et installer l’application Power BI.

3. Ouvrez Power BI Desktop, connectez-vous si vous y êtes invité.

4. Sélectionnez **Obtenir les données**.

5. Sélectionnez **Power Plateform**, **Common Data Service**, puis appuyez sur **Connecter**.

6. Collez l’URL d’environnement que vous avez copiée précédemment, puis appuyez sur **OK**.

7. Développez le nœud **Entités**, sélectionnez les entités **bc_Building** et **bc_Visit** et cliquez sur **Charger**.

8. Cliquez sur l’icône **Modèle** dans la barre d’outils verticale de gauche.

9. Faites glisser la colonne **bc_buildingid** du tableau **bc_Building** et déposez-la sur la colonne **bc_building** dans le tableau **bc_Visit**. Une relation sera ainsi créée entre deux entités que Power BI pourra utiliser pour afficher les données associées.

10. Sélectionnez l’icône **Rapport** dans la barre d’outils de gauche.

11. Développez le nœud **bc_Visits** dans le panneau **Champs**.

12. Cliquez sur les points de suspension (« ... ») et sélectionnez **Nouvelle colonne**.

13. Terminez la formule comme suit

    ```
    Column = RELATED(bc_Building[bc_name])
    ```

    Appuyez ensuite sur Entrée. Un nouveau champ sera ajouté avec le nom du bâtiment dans les données de visites.

14. Cliquez sur les points de suspension (« ... ») affichés en regard du champ et sélectionnez **Renommer**. Saisissez **Bâtiment** comme nom de champ.

15. Cliquez sur les points de suspension (« ... ») affichés en regard du champ **bc_visitid** et sélectionnez **Renommer**. Saisissez **Visites** comme nom de champ.

16. Cliquez sur ... à côté du champ **bc_scheduledstart** et sélectionnez **Renommer**. Entrez **Démarrer** comme nom de champ.

17. Enregistrez le travail en cours en appuyant sur **Fichier | Enregistrer** et en saisissant le nom de fichier de votre choix.

## Tâche #2 : Créer un graphique et des visualisations temporelles

1. Appuyez sur l’icône du graphique en secteurs dans le panneau **Visualisations** pour insérer le graphique.
2. Faites glisser le champ **Bâtiment** et déposez-le dans la zone cible **Légende**.
3. Faites glisser le champ **Visites** et déposez-le dans la zone cible **Valeurs**.
4. Redimensionnez le graphique en secteurs à l’aide des poignées d’angle afin que tous les composants du graphique soient visibles.
5. Cliquez sur **Nouveau visuel** sur le ruban Power BI, puis sélectionnez l’histogramme empilé dans le volet **Visualisations**. 
6. Faites glisser le champ **Visites** et déposez-le dans la zone cible **Valeurs**.
7. Faites glisser le champ **Début** et déposez-le dans la zone cible **Axe**.
8. Cliquez sur **X** à côté de **Jour** et **Trimestre** pour ne laisser que les totaux **Année** et **Mois**.
9. Redimensionnez le graphique selon les besoins à l’aide des poignées d’angle.
10. Testez l’interactivité du rapport :
    * Sélectionnez différents secteurs sur le graphique en secteurs et observez les changements sur le rapport de temps.
    * Sélectionnez diverses barres sur l’histogramme empilé de temps et observez les changements sur le graphique en secteurs.
    * Extrayez au niveau du mois à l’aide d’icônes ou de la commande **Données/Extraction | Développer le niveau suivant** du ruban.
11. Enregistrez le travail en cours en sélectionnant **Fichier | Enregistrer**.

Exercice n°2 : Créer un tableau de bord Power BI
================================

## Tâche #1 : Publier un rapport Power BI

1. Appuyez sur le bouton **Publier** dans le ruban.

2. Sélectionnez **Mon espace de travail** comme destination, puis appuyez sur **Sélectionner**.

3. Attendez la fin de la publication et cliquez sur **Ouvrez \<nom de votre rapport \>.pbix dans Power BI**.

## Tâche #2 : Créer un tableau de bord Power BI

1. Développez **Mon espace de travail**.
2. Sélectionnez le rapport sous l’en-tête **Rapports**.
3. Sélectionnez **Épingler une page dynamique** sur le menu. Selon la disposition, vous devrez peut-être appuyer sur ... pour afficher des éléments de menu supplémentaires.
4. Sélectionnez **Nouveau tableau de bord** sur l’invite **Épingler au tableau de bord**.
5. Entrez **Gestion du campus** comme un **Nom du tableau de bord** puis appuyez sur **Épingler un élément dynamique**.
6. Sélectionnez le nœud **Mon espace de travail** et sélectionnez le tableau de bord **Gestion du campus**.
7. Testez l’interactivité des graphiques en secteurs et à barres affichés.

## Tâche n°3 : Ajouter des visualisations à l’aide du langage naturel

1. Sélectionnez **Poser une question sur vos données** en haut du tableau de bord
2. Entrez **bâtiments par nombre de visites** dans la zone Questions et réponses. Le graphique à barres s’affiche.
3. Sélectionnez **Épingler un élément visuel**.
4. Sélectionnez **Tableau de bord existant**, sélectionnez le tableau de bord **Gestion du campus** puis appuyez sur **Épingler**.
5. Testez le comportement en cliquant sur le graphique pour accéder aux questions et réponses.

## Tâche 4 : Créer une vue de téléphone mobile

1. Sélectionnez le rapport de la zone **Rapports**.
2. Selon la version de l’interface utilisateur, sélectionnez soit : | Vue mobile ou **Vue web | Vue téléphone**.
3. Réorganisez les vignettes comme vous le souhaitez.
4. Sélectionnez : | Générez un code QR.
5. Si vous avez un appareil mobile, scannez le code à l’aide d’une application de scanner QR disponible sur les plates-formes iOS et Android.
6. Parcourez et découvrez les rapports sur un appareil mobile.

# Défis

* Inclure les plans du campus et des bâtiments dans les tableaux de bord et rapports
* Signaler et analyser les schémas et tendances des visites
* Visualisation des visites qui ont duré trop longtemps
* Diffuser Power BI en continu pour le traitement en temps quasi réel d’un grand campus 