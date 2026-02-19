# TP – Administration SSH et Serveur Web Nginx

## Partie 1 – Mise en place de l’environnement virtualisé
### 1 - Créez une VM Ubuntu

![alt text](image/image-30.png)

### 2 - Vérifiez que la VM a une IP accessible depuis la machine hôte

![alt text](image/image-31.png)

## Partie 2 – Serveur SSH

### 1 - Installez le serveur SSH sur la VM.

![alt text](image/image-32.png)

### 2 - Vérifiez que le service SSH fonctionne et écoute sur un port.

![alt text](image/image-33.png)

### 3 - Connectez-vous depuis la machine hôte 

![alt text](image/image-34.png)


### 4 - Générez une clé SSH sur la machine cliente

![alt text](image-1.png)

### 5- Copier clé ssh

![alt text](image.png)

### 6 - Teste connection sans mot de passe

![alt text](image-2.png)

## Partie 3 – Sécurisation SSH

Commande : ``` sudo nano /etc/ssh/sshd_config ```

### 1 - Interdisez l’accès root.

![alt text](image-4.png)

###  2 - Désactivez l’authentification par mot de passe.

![alt text](image-5.png)

### 3 - Modifier le port 

![alt text](image-3.png)
![alt text](image-6.png)

### 4 - Testez la connexion avec le nouveau port

![alt text](image-7.png)


## Partie 4 – Transfert de fichiers
### 1 - Transférez un fichier

![alt text](image-8.png)


