# Install 

## Requierements
- Python (3.10.13)
- Java (min ??, max 20)
- WSL
- Pymol

## 0 - Visualization
- Creer un environnement conda avec Pymol.
- RDKit.

## 1 - POCKET DETECTION: P2RANK
Il faut:
1. Utiliser gitbash ou Installer Cygwin (https://www.cygwin.com/)
2. Installer Java (jdk20)
3. Télécharger P2Rank (https://github.com/rdk/p2rank)
4. Exécuter le script make.sh
   - Il y a probablement un problème qui va survenir avec gradlew, qui est une dépendance de Gradle. Pour le résoudre, suivez les étapes suivantes :
   A. Vérifiez quelle version correspond à votre Java (voir ici : https://docs.gradle.org/current/userguide/compatibility.html) et mémorisez celle qui convient pour la compilation/testing.
   B. Ensuite, accédez à gradle>wrapper>gradle-wrapper.properties et changez le numéro de la version de distUrl par celle que vous avez trouvée (par exemple : si vous avez "distributionUrl=https\://services.gradle.org/distributions/gradle-8.5-bin.zip", changez-le en "distributionUrl=https\://services.gradle.org/distributions/gradle-8.1-bin.zip").
   C. Lancez ensuite `./gradlew clean`.
5. Copiez la variable `local_env` depuis `misc` pour avoir la commande `./prank.sh`.
6. Exemple de commande pour voir si cela fonctionne :
   ```bash
   ./prank.sh predict -f ../NSP13/6zsl.cif -o output_here ../NSP13/results/test.ds

SUPER IMPORTANT!
Ne pas installer Gradle ou Prank si cela ne fonctionne pas !!! Se limiter aux réponses de p2rank sur le net. 

# 2 - PRESELECTION DE LIGANTS

- Le script se trouve dans `ligands>ligands_down...>lig_down_script`
