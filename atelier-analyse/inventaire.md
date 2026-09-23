# Inventaire des points d'entrée

Le livrable de l'atelier d'analyse. Il dit ce que l'API devra **permettre** — pas comment on
l'écrira.

Une règle : tout ce qui figure ici doit se justifier par la lettre de mission ou par un écran
des maquettes. Si vous ne savez plus d'où vient une ligne, c'est peut-être qu'elle n'en vient
pas. (Seule exception : la section bonus, si vous en ajoutez une.)

---

## Ce que l'utilisateur peut faire

Une action par ligne, en français. Pas encore de chemins.

- **Consulation du réseau** : <br>
  _Pouvoir consulter les voyages et villes desservies sans besoin d'être connecté, on aura accès à la liste de tout les villes de départ et d'arrivée_
- **Compte du voyageur** : <br>
  _Pouvoir créer un compte ainsi s'y connecter. Peut consulter ses informations et ses billets. Le prénom et le nom est falcutatif à l'inscription mais devra avoir un adresse mail éclectronique et d'un mot de passe à renseigner._
- **Recherche d'un voyage** : <br>
  _Permet de spécifier sa ville de départ, d'arrivé, la date et le nombre de passagers. Après cette spécification l'office présente les lancer/voyage disponibles avec chacun leur horraire selon le nombre de passagers ainsi que la durée et prix. Avec la masse à respecter pour leur voyage. Aucun besoin de connection_
- **Réservation** : <br>
  _Permet de mettre dans un panier des voyages avant de finaliser le payement. Pour constituer ce panier il faut obligatoirement être connecter, on peut réserver mais si on est pas connecter il faudra le faire mais il gardera en mémoire ce qu'on avait réserver dès la connection faite. Lorsque le panier validé il procéde au réglement qui lui donnera ses billets. Le payement peut se faire soi par carte bancaire, soit par Bon de transport de l'office. Il aura aussi un récapitulatif du prix de tout les lancers/voyages enregistrer._
- **Billets** : <br>
  _A l'image d'un billet de train, le billet donne droit à l'embarquement et prouve que vous avez bien payer. Il devra se présenter à l'heure et date précise écris sur l'application. Avec des informations sur le trajet l'id du billet, quand il a été emis et sa destination._

## Les points d'entrée

| Ce que ça fait                    | Verbe  | Chemin proposé      | Qui peut l'appeler |
| --------------------------------- | ------ | ------------------- | ------------------ |
| Liste de tout les villes desservi | GET    | /cities             | Tout le monde      |
| Pouvoir créer un compte           | POST   | /register           | Tout le monde      |
| Pouvoir se connecter              | POST   | /login              | Tout le monde      |
| Rechercher un voyage              | QUERY  | /trajets            | Tout le monde      |
| Détails trajet                    | GET    | /trajets/{id}       | Tout le monde      |
| Réserver le trajet                | POST   | /users/{id}/payment | Membre Connecté    |
| Faire le payement                 | POST   | /users/{id}/pay     | Membre Connecté    |
| Récupérer les billets acheté      | GET    | /users/{id}/billets | Membre Connecté    |
| Récupérer le profil utilisateur   | GET    | /users/{id}         | Membre Connecté    |
| Retirer une reservation           | DELETE | /me/payment/{id}    | Membre Connecté    |

## Les données qui circulent

Pour chaque point d'entrée : ce qu'il reçoit, ce qu'il renvoie. Nommez les données comme
l'Office les nomme — les traduire en identifiants techniques, c'est le travail de demain.

### Récupére la liste de tout les villes

Envoie un GET pour recevoir un JSON avec un Code 200

### Créer un compte

Envoie un JSON en POST pour recevoir un code 201

### Se connecter

Envoie un JSON en POST puis reçoit un code 200 et un token d'authentification

### Rechercher un voyage

Envoie un JSON en POST et recoit un JSON avec le code 200

### Détails Trajets

Envoie un GET pour recevoir un JSON avec code 200

### Réserver Trajets

Envoie un POST en JSON pour reçevoir un code 201

### Faire le payement

Envoie un POST en JSON pour reçevoir un code 200

### Récupérer les billets

Envoie un GET pour récupérer un JSON avec le code 200

### Récupérer le profil

Envoie un GET pour récupérer un JSON avec le code 200

### Retirer une réservation

Envoie un DELETE pour récupérer rien

## Ce dont on n'est pas sûrs

Les questions que la lettre et les maquettes ne tranchent pas. Une question notée vaut mieux
qu'une réponse inventée.

-
