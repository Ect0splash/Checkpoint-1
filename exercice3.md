# Quiz - Réponses

---

### 1. Lister la liste des utilisateurs d'un système Linux
cut -d: -f1 /etc/passwd


### 2. Changer les droits du fichier myfile en rwxr--r--
chmod 744 myfile

### 3. Ignorer les fichiers .pdf dans un dépôt Git
Ajouter la règle dans le fichier .gitignore :
echo "*.pdf" >> .gitignore
git add .gitignore
git commit -m "Ajout des fichiers PDF à ignorer"

### 4. Fusionner les branches main et test_valide
Pour fusionner test_valide dans main :
git checkout main
git merge test_valide

### 5. Afficher le texte demandé
echo 'Malgré le prix élevé de 100$, il a dit "Bonjour !" au vendeur :'
echo '- "Bonjour est-ce que ce clavier fonctionne bien ?"'
echo '- "Evidemment ! On peut tout écrire avec, que ce soit des pipe | ou bien des backslash \\ !"'
echo '- "Même des tildes ~ ?"'
echo '- "Evidemment !"'

### 6. Mettre en avant le processus gedit
fg %1

### 7. Matériels réseaux des couches 2 et 3 du modèle OSI
Couche 2 (Liaison de données) :
Matériel : Switch.
Spécificités : Utilisation des adresses MAC pour transmettre les données. Fonctionne au niveau des trames.
Couche 3 (Réseau) :
Matériel : Routeur.
Spécificités : Utilisation des adresses IP pour le routage des paquets entre les réseaux.

### 8. Équivalents PowerShell des commandes bash
Commande Bash	Commande PowerShell
cd	Set-Location
cp	Copy-Item
mkdir	New-Item -ItemType Directory
ls	Get-ChildItem

### 9. Dans la trame Ethernet, qu'est-ce que le payload ?
Le payload est la partie de la trame qui contient les données utiles envoyées par une application ou un protocole. Il est encapsulé entre l'en-tête et le trailer Ethernet.

### 10. Pourquoi les classes IP sont remplacées par le CIDR ?
Le CIDR (Classless Inter-Domain Routing) a remplacé les classes IP car il permet une gestion plus flexible et efficace des adresses IP :

Évite le gaspillage d'adresses grâce à la granularité des sous-réseaux.
Permet d’allouer des blocs d’adresses de tailles adaptées aux besoins (sans se limiter aux classes A, B, ou C).
Améliore le routage en utilisant le regroupement d’adresses (aggregation).
