# Cette application utilise des techniques d'apprentissage supervisées et non supervisées
L'objectif du projet est de créer une application pour corriger les défauts de surface de l'acier en utilisant des méthodes d'apprentissage supervisées et non supervisées.

## Dependencies
Les dépendances suivantes doivent être installées avant d'exécuter le projet.
- [Docker](https://docs.docker.com/get-docker/) - framework pour exécuter l'application sur toutes les plates-formes.
- [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) - Linux shell platform. (Seulement pour les utilisateurs Windows)


## Installation
 
Clonez la branche master du repositorie de votre choix 

```bash
git clone -b master https://github.com/Morue/App_detection_defauts_industriels.git
```

Source dans le dossier cloné et exécutez le script install.sh pour générer une image docker pour le projet.

```bash
./install.sh
```
This will generate the docker image with the necessary dependencies. 

## Usage

Pour exécuter l'application :

Exécutez le script launch_app.sh.
```bash
./launch_app.sh
```
Cela démarrera un conteneur docker avec le nom "defect_detector" qui chargera et exécutera l'application.

![User Interface for ID3](https://github.com/Morue/App_detection_defauts_industriels/blob/main/images/user_interface_entrypoint.png)

L'utilisateur peut spécifier les valeurs d'entrée pour tous les modèles d'apprentissage automatique et former les modèles individuellement.

Pour en savoir plus sur ces modèles :

### Feature Extraction Methods:

- [Grey-Level Co-occurence Matrix](https://scikit-image.org/docs/dev/auto_examples/features_detection/plot_glcm.html
) - Méthode d'extraction de caractéristiques utilisant l'algorithme GLCM.

- [Local Binary Patterns + Grey-Level Co-occurence Matrix](https://towardsdatascience.com/face-recognition-how-lbph-works-90ec258c3d6b
) - Méthode d'extraction de caractéristiques utilisant l'algorithme LBGLCM.

### Machine Learning Models:

- [Random Forest Classifier](https://www.section.io/engineering-education/introduction-to-random-forest-in-machine-learning/) 

- [Extra Trees Classifier](https://www.geeksforgeeks.org/ml-extra-tree-classifier-for-feature-selection/)

- [Gradient Boosting Model](https://machinelearningmastery.com/gentle-introduction-gradient-boosting-algorithm-machine-learning/)

- [Convolutional Neural Networks](https://www.tensorflow.org/tutorials/images/cnn)

Les résultats de la formation peuvent être visualisés sur l'interface utilisateur une fois que tous les modèles ont été formés.

![Exemples de résultats de formation pour les modèles d'apprentissage automatique](https://github.com/jd509/USC-AME-505-ID3-Intelligent-Defect-Detection-System/blob/master/images/sample_accuracy_results.png)

Après la formation, l'interface utilisateur peut être utilisée pour prédire l'étiquette de classification d'une image donnée et identifier le défaut qui lui est associé.

![Defect Predictor](https://github.com/jd509/USC-AME-505-ID3-Intelligent-Defect-Detection-System/blob/master/images/defect_prediction.png)


## À l'intérieur du dépôt

Le référentiel contient des scripts Python pour former et tester le modèle. Il contient également le jeu de données sur lequel le modèle a été formé.

### Scripts
- train_machine_learning_models.py : Script Python pour former les modèles et extraire les fonctionnalités.
- predict_defects.py : Script Python pour prédire le défaut d'une seule image à l'aide de modèles entraînés.
- user_interface.py : Interface utilisateur pour interagir avec l'application.

### Fichiers de configuration
- image_feature_extraction_config.json : JSON file for default parameters to extract features from training dataset
- machine_learning_params.json : Fichier JSON pour les paramètres par défaut permettant d'extraire les fonctionnalités de l'ensemble de données d'entraînement
### Folders
- train_dataset: Contient l'ensemble de données pour six types de défauts de surface : Cracking, Inclusion, Patches, Pitted Surfaces, Scratches, Residues
- test_dataset: Exemples d'images pour tester le modèle
  
## Problèmes connus
Actuellement, il n'y a aucun problème connu pour exécuter l'application. Toutefois, si des problèmes ont été détectés, veuillez ouvrir un forum de problèmes pour le même
## Contribuant
Les demandes d'extraction sont les bienvenues. Pour les modifications majeures, veuillez d'abord ouvrir un problème pour discuter de ce que vous souhaitez modifier.