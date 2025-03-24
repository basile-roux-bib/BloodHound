# Mini-Doc 

    Minidoc est un document rédigé dans le but de documenter ce que je découvre sur le code de Bloodhound à mesure que je le comprends. Je ne garantis si non exhaustivité ni son exactitude. 

### Developpement

Gestion des modules : Certains go.mod ont été modifiés avec des replaces pour une version local d'Azurehound développé en parallèle. Ne pas oublier d'ignorer ou mettre à jour ces modules une fois push. 


### Changement Attributs

La majorité se passe dans le code **Cue**, il faut ajouter des propriétés et ensuite lancer la commande ```just schemagen``` pour les appliquer. 

Il semble y avoir également des choses à changer sur le fichier **go/ein** qui, de ce que j'en comprends, gère le formatage. 

### Ajout/Deletion d'un node

Les fonctions utiles se trouvent dans **go/ein**. Ajout de trois fonctions ConvertGroup365ToNode, ConvertGroup365ToOnPremiseNode ainsi que Convert365ToRel sur le modèle des groupes. 

Les fonctions d'encodages et décodages des jsons sont dans **decoders.go"**. 

**incoming_models.go**, je ne sais pas encore à quoi ça réfère exactement, mais j'ai ajouté un model pour microsoft365 dedans

**ingest.go** -> **decoder.go** 