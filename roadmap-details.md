# Roadmap signature

## Api 

- [ ] récupération de la liste des promos ( nom + uuid )
- [ ] route pour récuperer les données permettant de créer le chan signature
-- nom + uuid de la promo
-- nom + snowflake  du chargé de projet assigné a la promo
-- nom + snowflake des formateurs liés a la promo
-- noms + snowflake des apprenants liés a la promo

- [ ] forme du json des données attendues : 
```json
{
  "promotion": {
    "uuid": "123e4567-e89b-12d3-a456-426614174000",
    "nom": "Promotion 2023",
    "forum": {
      "snowflake": "123456789012345678",
      "nom": "Forum de la Promotion 2023"
    },
    "chargeDeProjet": {
      "snowflake": "987654321098765432",
      "nom": "Jean Dupont"
    },
    "formateurs": [
      {
        "snowflake": "111111111111111111",
        "nom": "Alice Martin"
      },
      {
        "snowflake": "222222222222222222",
        "nom": "Bob Durand"
      }
    ],
    "apprenants": [
      {
        "snowflake": "333333333333333333",
        "nom": "Élève 1"
      },
      {
        "snowflake": "444444444444444444",
        "nom": "Élève 2"
      },
      {
        "snowflake": "555555555555555555",
        "nom": "Élève 3"
      },
      {
        "snowflake": "666666666666666666",
        "nom": "Élève 4"
      },
      {
        "snowflake": "777777777777777777",
        "nom": "Élève 5"
      },
      {
        "snowflake": "888888888888888888",
        "nom": "Élève 6"
      },
      {
        "snowflake": "999999999999999999",
        "nom": "Élève 7"
      },
      {
        "snowflake": "101010101010101010",
        "nom": "Élève 8"
      },
      {
        "snowflake": "111111111111111112",
        "nom": "Élève 9"
      },
      {
        "snowflake": "121212121212121212",
        "nom": "Élève 10"
      },
      {
        "snowflake": "131313131313131313",
        "nom": "Élève 11"
      },
      {
        "snowflake": "141414141414141414",
        "nom": "Élève 12"
      }
    ]
  }
}
```


## Bot 
### Critères d'acceptabilité de base
-  [ ] le bot peut envoyer des messages dans un chan
- [ ] lel bot peut envoyer des messages privés
- [ ] le bot peut créer des fil de discussion
- [ ] le bot peut modifier le contenu des messages qu'il a créé
- [ ] le bot peut écouter les requetes http provenant du dashboard
- [ ] le bot peut lire / ecrire des fichiers (pour la config et les logs)

### Configuration du bot
- [ ] parsing des données de configuration 
- [ ] population du fichier de config avec toutes les promos actives
- [ ] ecriture du statut du chan (created true /false , active true / false)
created : pour sauvegarder si un chan a ou n'a pas d''interface de signature 
active : pour sauvegarder si un chan est ou n'est pas en pause

### Logging (a rework)
- [ ] utilisation de la creation d'un chan : utilisateur + chan créé + date
``` 
Roberto à créé le chan signature pour la promo xxxxx le xxxxxxx
```
- [ ] changement du satut de pause d'un chan : utilisateur + chan + status (actif / inactif) + date
```
Roberta a mis en pause le bot signature pour la promo promo 1 le xxxxx
```
- [ ] utilisation du bot dans la situation ou un apprenant demande a un formateur si il peut signer
Emetteur + action + destinataire + date
```
Michel a demandé a Micheline si il peut signer le xxxxx
```
- [ ] utilisation du bot dans la situation ou un formateur demande a un ou plusieurs apprentis si il peuvent signer
Emetter + action + destinataire(s)
```
Micheline a demandé a Régis et Georgette de vérifier le status de leur signature le xxxxxx
```
## bot
### Création du message d'interface pour la création des chan signature
- [ ] recuperation des données nécéssaires (liste des promos + chan id)
- [ ] select listant toutes les promos (name: nom de la promo, value: snowflake du chan attitré)
- [ ] verification de la présence du chan de signature dans le chan selectionné
- [ ] bouton de validation
- [ ] message ephemere de validation
- [ ] message ephemere en cas d'impossibilité d'utilisation
- [ ] creation d'un chan avec les fonction d'interface nécessaires
- [ ] creatjion d'une entree dans le journal de log
- [ ] possibilité de mettre a jour la liste

### Création de l'interface de signature (staff -> apprenant)
- [ ] recuperation des données nécessaires (cf partie api)
- [ ] genération du select (liste d'apprenants)
- [ ] creation d'un timer pour limiter l'utilisation
- [ ] verififaction du timer pour permettre ou interdire l'envoi
- [ ] message ephemere de validation
- [ ] message ephemere en cas d'impossibilité d'utilisation
- [ ] validation
- [ ] bouton pour envoyer un message a tout le monde
- [ ] envoi d'un message aux apprenants sélectionnés
- [ ] creation d'une entree dans le journal de log
- [ ] possibilité de mettre a jour la liste

### Création de l'interface de signature (apprenants -> staff)
- [ ] recuperation des données nécessaires (cf partie api)
- [ ] genération du select (liste staff)
- [ ] creation d'un timer pour limiter l'utilisation
- [ ] verififaction du timer pour permettre ou interdire l'envoi
- [ ] message ephemere de validation
- [ ] message ephemere en cas d'impossibilité d'utilisation
- [ ] validation
- [ ] envoi d'un message aux apprenants sélectionnés
- [ ] creation d'une entree dans le journal de log
- [ ] possibilité de mettre a jour la liste

## dashboard

## plan de test
### test unitaires
### test d'integration
### test e2e
