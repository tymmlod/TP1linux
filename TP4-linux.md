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

![alt text](image-46.png)

### 5- Copier clé ssh

![alt text](image-47.png)

### 6 - Teste connection sans mot de passe

![alt text](image-48.png)

## Partie 3 – Sécurisation SSH

Commande : ``` sudo nano /etc/ssh/sshd_config ```

### 1 - Interdisez l’accès root.

![alt text](image-49.png)

###  2 - Désactivez l’authentification par mot de passe.

![alt text](image-50.png)

### 3 - Modifier le port 

![alt text](image-51.png)
![alt text](image-52.png)

### 4 - Testez la connexion avec le nouveau port

![alt text](image-53.png)


## Partie 4 – Transfert de fichiers
### 1 - Transférez un fichier

![alt text](image-54.png)


### 2 - Transférez un dossier

![alt text](image-55.png)

## Partie 5 – Analyse des logs et sécurité
### 1 - Suivez les logs d’authentification
![alt text](image-56.png)


### 2 - Installez Fail2Ban et testez un bannissement

![alt text](image-57.png)
Commande :
```
sudo apt update
sudo apt install fail2ban
sudo systemctl status fail2ban
sudo nano /etc/fail2ban/jail.local

dedans mettre:

[sshd]
enabled = true
port = 2222
logpath = /var/log/auth.log
maxretry = 3
bantime = 600

sudo systemctl restart fail2ban

```

## Partie 6 – Tunnel SSH

Tout d'abord il faut installer apache2 avec la commande ``` sudo apt insatall apache2```

Puis lancer le tunnel avec ```ssh -p 2222 -L 8080:localhost:80 tym@10.198.255.67``

 ![alt text](image-59.png)