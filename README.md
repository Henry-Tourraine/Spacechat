Pour lancer le projet, rentrer dans le dossier racine 
et entrer dans un terminal
```bash
python -m http.server <PORT>
```

remplacer le <PORT> par un port disponible.
Cette commande lance un serveur python sur ce port et permet d'accéder
au projet depuis le navigateur.

Ensuite rechercher localhost:<PORT> dans un navigateur pour accéder au projet.

Le bouton "enregistrer" permet d'enregistrer l'application en action (image & son)
NB: penser à mettre en plein écran.
NB: cocher l'option "son" si demandée lors du partage d'écran du navigateur.

Le bouton "Lancer la conversation" joue vos messages.

***Configuration***

Le dossier assets contient tous les fichiers statiques nécessaires à l'application:
Pour être utilisés, ils doivent ensuite être référencés dans le fichier config.json.

* **onMessage** permet d'indiquer qu'un son doit être jouer lorsqu'un nouveau message apparaît.
Si le son doit être jouer pour tous les messages, pas besoin d'ajouter "names" :<br/>
```json
        {
            "action": "play",
            "file": "sms.mp3"
        }
```
<br/>
sinon il faura indiquer les "name" des messages pour lesquels le son doit être joué :<br/>
Plusieurs messages peuvent avoir le même "name".

```json
        {
            "names": [1, 2],
            "action": "play",
            "file": "sms.mp3"
        }
```

Ici le son sms.mp3 sera joué pour le deuxième et troisième message (index commence à zéro).

* **delay** est le délai écoulé entre chaque message en millisecondes.

* **background** est le nom complet de l'image qui servira de fond. Elle doit être dans le dossier "images".

* **messages** est la liste des messages échangé entre "user" et "system"
chaque objet doit contenir la clé "sender" et "content".
S'il y a besoin de retours à la ligne, utiliser le caractère "\n".

<br/>

***Style***

Pour changer le padding ou les margin des messages, utiliser la classe css ".sms".
Pour être spécifique à un utilisateur, ".system .sms" ou ".user .sms".
Pour les espaces entre messages, utiliser margin dans ".messageWrapper".

Le fond des messages peut être changé dans les classes : ".system > div" et ".user > div".