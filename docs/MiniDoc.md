# Mini-Doc 

    Minidoc est un document rédigé dans le but de documenter ce que je découvre sur le code de Bloodhound à mesure que je le comprends. Je ne garantis si non exhaustivité ni son exactitude. 

## Developpement

Gestion des modules : Certains go.mod ont été modifiés avec des replaces pour une version local d'Azurehound développé en parallèle. Ne pas oublier d'ignorer ou mettre à jour ces modules une fois push. 
Gestion de la génération : main.go dans le dossier shemagen n'était pas fonctionel sur mon set-up. Je l'ai corrigé et il faudra le remettre à son état d'origine. 

## Changement Attributs

La majorité se passe dans le code **Cue**, il faut ajouter des propriétés et ensuite lancer la commande ```just schemagen``` pour les appliquer. 

Il semble y avoir également des choses à changer sur le fichier **go/ein** qui, de ce que j'en comprends, gère le formatage. 

## Ajout/Deletion d'un node

**Bloodhoundgraph.go** Définie l'UI/l'apparence des nodes   
*TODO : Ajouter ou supprimer son Node.* 

**cmd\ui\src\ducks\graph\graphutils.ts** UI.

**BloodHound\cmd\api\src\analysis\azure\queries.go** Is used for data quality, count the number of group,user,groups365 etc...   
*TODO : Ajouter ou Supprimer son type de Node.*

**cmd\api\src\api\v2\azure.go** Gere des requêtes HTTPs pour récupérer des informations sur les entités Azure.   
*TODO: Ajouter osn type de NODE dans les différentes requêtes selon besoin (entity info principalement). Ajouter de nouvelles requêtes au besoin ?* 

**packages\go\analysis\azure\db_ops.go** Appelé notamment par azure.go **cmd\api\src\api\v2\azure.go**, contient de nombreuses fonctions qui effectuent des opérations sur la base de donnée. Normalement pas besoin de toucher, elles sont générales et son appelées par azure.go. 

**cmd\api\src\daemons\datapipe\azure_convertors.go** Désérialise puis si la désérialisation réussie convertit les données bruts en ConvertedAzureData pour être digérées. Appelle des fonctions du fichier **ein.go**.  
*TODO : Ajouter/Supprimer la fonction de conversion pour le node d'intérêt. Ne pas oublier d'ajouter le point d'entrée dans la fonction getKindConvertor*

**cmd\api\src\model\azurequality.go** Définit les structures de données pour la qualité des données.  
*TODO : Ajouter/Supprimer le node d'intérêt**

**cmd\api\src\test\integration\graph.go** Utile pour les tests, à remplir plus tard. 

**cmd\ui\src\ducks\entityinfo\types.ts** Définit les propriétés à afficher pour chaque node. Etends généralement les propriétés de bases.   
*TODO : Ajouter/Supprimer l'interface relative au node d'intérêt*

**cmd\ui\src\ducks\graph\types.ts** Définit des types et des interfaces utilisés pour représenter les nœuds et les liens dans un graphe  
*TODO : Ajouter/Supprimer le node d'intérêt**

**packages\cue\bh\azure\azure.cue** Définitet liste l'intégralité des attributs, des nodes et des relations. Génère la plupart des fonctions pour manipuler le graph.  
*TODO : Ajouter/Supprimer le noeud d'intérêt dans la section "kind"*

**packages\go\analysis\azure\azure.go** contient des fonctions qui déterminent les types de nœuds descendants pour différents types de nœuds Azure dans un graphe  
*TODO : Ajouter/Supprimer le noeud d'intérêt dans la bonne catégorie*

**packages\go\analysis\azure\group365.go** Ce fichier Go contient des fonctions qui récupèrent et peuplent les détails d'une entité Group365 (groupe Microsoft 365) dans une base de données de graphe.  
*TODO : Créer/Supprimer un fichier nommé d'après le noeud d'intérêt. Adapter le code à l'usage du noeud (notamment la fonction PopulateEntityDetails)*

**packages\go\analysis\azure\model.go**contient des définitions de structures de données utilisées pour représenter les détails des entités Azure dans une base de données de graphe. Etend les propriétés définit précédemment.  
*TODO : Ajouter/Supprimer la structure relative au node d'intérêt*

**packages\go\ein\azure.go** Traduis les données du format Azure vers un format plus adapté aux nodes et aux relations  
*TODO : Ajouter/Supprimer les fonctions associées au node d'intérêt*

**packages\go\graphschema\azure\azure.go** Définit des fonctions utilitaires.  
*TODO : Ajouter/Supprimer la variable du node d'intérêt et les "case" le concernant*

**packages\javascript\bh-shared-ui\src\graphSchema.ts** Relatif à l'UI   
*TODO : Ajouter/Supprimer le node d'intérêt et est "case" le concernant*

**packages\javascript\bh-shared-ui\src\utils\content.ts** Contient des définitions de types et des fonctions utilitaires pour gérer les entités et les relations spécifiques à Azure dans un graphe. Il définit les différents types de nœuds et de relations qui peuvent exister dans un graphe Azure, ainsi que des fonctions pour manipuler et interroger ces types.  
*TODO : Ajouter/Supprimer le node d'intérêt et les "sections" que l'on souhaite voir apparaitre/disparaitre.

**cmd\api\src\database\migration\migrations\schema.sql** Gère la création des différents shemas sql.  
*TODO : Ajouter/Supprimer le node d'intérêt pour qu'il soit correctement décompté*

**cmd\api\src\database\dataquality.go** Gère les requêtes pour établir la qualité des données  
*TODO : Ajouter/Supprimer les requêtes MAX et SUM pour le noeud d'intérêt*

**packages\javascript\bh-shared-ui\src\views\DataQuality\TenantInfo.tsx** Définit les informations d'affichage relatif au Tenant azure.  
*TODO : Ajouter/Supprimer le node d'intérêt dans "tenant info"*

**packages\javascript\bh-shared-ui\src\utils\icons.ts** Relatif aux icons des nodes.  
*TODO : Ajouter/Supprimer le node d'intérêt et définir sa représentation et sa couleur*
