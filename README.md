# Checkpoint-1
# Exercice 1 - Gestion du stockage 

# Préparation du second disque dur

## Objectif
- **Partition 1** : 6 Go, type `ext4`, nommée **DATA**.
- **Partition 2** : reste du disque, type `swap`, nommée **SWAP**.
- Activer la partition **SWAP** et désactiver celle du premier disque.

![Capture d'écran de la partition]([capture.png](https://github.com/Ect0splash/Checkpoint-1/blob/main/Screenshot/Exercice%201%20-%20Gestion%20du%20stockage/1.PNG))

---

### 1. Identifier le disque
Pour vérifier la présence du disque et ses détails :
lsblk
. Créer les partitions
Utilisez fdisk pour créer deux partitions sur le disque /dev/sdb :


Copier le code
sudo fdisk /dev/sdb
Tapez n pour créer une nouvelle partition.
Choisissez p pour une partition principale.
Pour la première partition :
Numéro de partition : 1.
Début : par défaut (premier secteur).
Fin : +6G.
Pour la deuxième partition :
Numéro de partition : 2.
Début : suivant (par défaut).
Fin : laissez par défaut (jusqu'à la fin du disque).
Changez le type de la deuxième partition en swap :
Tapez t, sélectionnez la partition 2, et entrez 82 pour le type "Linux swap".
Sauvegardez les modifications avec w.

---

### 2. Formater les partitions
Formatez la partition DATA en ext4 et configurez la partition SWAP :

bash
Copier le code
sudo mkfs.ext4 /dev/sdb1 -L DATA
sudo mkswap /dev/sdb2 -L SWAP$

---

### 3. Activer et désactiver le swap
Désactivez l'ancien swap :
bash
Copier le code
sudo swapoff -a
Activez le nouveau swap :
bash
Copier le code
sudo swapon /dev/sdb2
Vérifiez que le swap actif est celui de la partition SWAP :
bash
Copier le code
swapon --show

---

### 4. Monter la partition DATA
Créez un point de montage et montez la partition DATA :

bash
Copier le code
sudo mkdir -p /mnt/DATA
sudo mount /dev/sdb1 /mnt/DATA

---

### 5. Rendre les modifications permanentes
Modifiez le fichier /etc/fstab pour monter automatiquement les partitions et activer le swap au démarrage :

bash
Copier le code
sudo nano /etc/fstab
Ajoutez les lignes suivantes :

css
Copier le code
LABEL=DATA  /mnt/DATA  ext4  defaults  0  2
LABEL=SWAP  none       swap  sw        0  0

---

### 6. Vérifications finales
Vérifiez les partitions :
bash
Copier le code
lsblk
Vérifiez le système de fichiers et les tailles :
bash
Copier le code
df -h
Vérifiez le swap :
bash
Copier le code
swapon --show

