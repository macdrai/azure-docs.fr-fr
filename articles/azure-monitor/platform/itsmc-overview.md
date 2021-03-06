---
title: Connecteur de gestion des services informatiques dans Log Analytics
description: Cet article fournit une vue d’ensemble du connecteur de gestion des services informatiques (ITSMC) et des informations sur son utilisation pour superviser et gérer des éléments de travail ITSM dans Log Analytics et résoudre rapidement les problèmes.
ms.subservice: logs
ms.topic: conceptual
author: nolavime
ms.author: v-jysur
ms.date: 05/24/2018
ms.custom: references_regions
ms.openlocfilehash: b4e35296a999070a6f536f4a52cfb7c3a1d4f42a
ms.sourcegitcommit: d22a86a1329be8fd1913ce4d1bfbd2a125b2bcae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96186488"
---
# <a name="connect-azure-to-itsm-tools-by-using-it-service-management-connector"></a>Connecter Azure aux outils ITSM à l’aide du connecteur de gestion des services informatiques

:::image type="icon" source="media/itsmc-overview/itsmc-symbol.png":::

Le connecteur de gestion des services informatiques (ITSMC) vous permet de connecter Azure à un produit ou service Gestion des services informatiques (ITSM) pris en charge.

Des services Azure comme Azure Log Analytics et Azure Monitor fournissent des outils pour détecter, analyser et résoudre les problèmes liés à vos ressources Azure et non Azure. Mais les éléments de travail liés à un problème résident généralement dans un service ou produit ITSM. ITSMC fournit une connexion bidirectionnelle entre Azure et les outils ITSM pour vous permettre de résoudre les problèmes plus rapidement.

ITSMC prend en charge les connexions avec les outils ITSM suivants :

-   ServiceNow
-   System Center Service Manager
-   Provance
-   Cherwell

   >[!NOTE]
> À compter du 1er octobre 2020, les intégrations ITSM de Cherwell et Provance à Azure Alert ne seront plus disponibles pour les nouveaux clients. Les nouvelles connexions ITSM ne seront pas prises en charge. Les connexions ITSM existantes continueront d’être prises en charge.

Avec ITSMC, vous pouvez :

-  Créer des éléments de travail dans votre outil ITSM, en fonction de vos alertes Azure (alertes de métriques, alertes de journal d’activité et alertes Log Analytics).
-  Si vous le souhaitez, vous pouvez synchroniser les données d’incidents et de demandes de modification de vos outils ITSM vers un espace de travail Azure Log Analytics.

Pour plus d’informations sur les conditions légales et la politique de confidentialité, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwLink/?LinkID=522330&clcid=0x9).

Vous pouvez commencer à utiliser ITSMC en effectuant les étapes suivantes :

1.  [Ajoutez ITSMC.](#add-it-service-management-connector)
2.  [Créez une connexion ITSM.](#create-an-itsm-connection)
3.  [Utilisez la connexion.](#use-itsmc)


##  <a name="add-it-service-management-connector"></a>Ajouter un connecteur de gestion des services informatiques

Avant de pouvoir créer une connexion, vous devez ajouter ITSMC.

1. Dans le portail Azure, sélectionnez **Créer une ressource** :

   ![Capture d’écran montrant l’élément de menu Créer une ressource.](media/itsmc-overview/azure-add-new-resource.png)

2. Recherchez **Connecteur de gestion des services informatiques** dans la Place de Marché Azure. Sélectionnez **Créer** :

   ![Capture d’écran montrant le bouton Créer dans la Place de marché Azure.](media/itsmc-overview/add-itsmc-solution.png)

3. Dans la section **Espace de travail OMS**, sélectionnez l’espace de travail Azure Log Analytics où vous voulez installer ITSMC.
   >[!NOTE]
   > * Dans le cadre de la transition en cours de Microsoft Operations Management Suite (OMS) vers Azure Monitor, les espaces de travail OMS sont maintenant appelés *espaces de travail Log Analytics*.
   > * ITSMC peut être installé uniquement dans les espaces de travail Log Analytics des régions suivantes : USA Est, USA Ouest 2, USA Centre Sud, USA Centre-Ouest, US Gov Arizona, US Gov Virginie, Canada Centre, Europe Ouest, Royaume-Uni Sud, Asie Sud-Est, Japon Est, Inde Centre et Australie Sud-Est.


4. Dans la section **Espace de travail Log Analytics**, sélectionnez le groupe de ressources où vous voulez créer la ressource ITSMC :

   ![Capture d’écran montrant la section Espace de travail Log Analytics.](media/itsmc-overview/itsmc-solution-workspace.png)
   >[!NOTE]
   >Dans le cadre de la transition en cours de Microsoft Operations Management Suite (OMS) vers Azure Monitor, les espaces de travail OMS sont maintenant appelés *espaces de travail Log Analytics*.

5. Sélectionnez **OK**.

Quand la ressource ITSMC est déployée, une notification s’affiche en haut à droite de la fenêtre.


## <a name="create-an-itsm-connection"></a>Créer une connexion ITSM

Une fois que vous avez installé ITSMC, vous pouvez créer une connexion.

Pour créer une connexion, vous devez préparer votre outil ITSM afin d’autoriser la connexion à partir d’ITSMC.  

En fonction du produit ITSM auquel vous vous connectez, sélectionnez l’un des liens suivants pour obtenir des instructions :

- [System Center Service Manager](./itsmc-connections.md#connect-system-center-service-manager-to-it-service-management-connector-in-azure)
- [ServiceNow](./itsmc-connections.md#connect-servicenow-to-it-service-management-connector-in-azure)
- [Provance](./itsmc-connections.md#connect-provance-to-it-service-management-connector-in-azure)  
- [Cherwell](./itsmc-connections.md#connect-cherwell-to-it-service-management-connector-in-azure)

Après avoir préparé vos outils ITSM, effectuez les étapes suivantes pour créer une connexion :

1. Dans **Toutes les ressources**, recherchez **ServiceDesk(*nom_de_votre_espace_de_travail*)**  :

   ![Capture d’écran montrant les ressources récentes dans le portail Azure.](media/itsmc-overview/itsm-connections.png)

1. Sous **Sources de données de l’espace de travail** dans le volet gauche, sélectionnez **Connexions ITSM** :

   ![Capture d’écran montrant l’élément de menu Connexion ITSM.](media/itsmc-overview/add-new-itsm-connection.png)
   Cette page affiche la liste des connexions.
1. Sélectionnez **Ajouter une connexion**.

4. Spécifiez les paramètres de connexion comme décrit dans [Configuration de la connexion ITSMC avec vos produits/services ITSM](./itsmc-connections.md).

   > [!NOTE]
   >
   > Par défaut, ITSMC actualise les données de configuration de la connexion toutes les 24 heures. Pour actualiser instantanément les données de votre connexion avec les éventuelles modifications ou mises à jour du modèle, sélectionnez le bouton **Synchroniser** sur le panneau de votre connexion :
   >
   > ![Capture d’écran montrant le bouton Synchroniser dans le panneau de connexion.](media/itsmc-overview/itsmc-connections-refresh.png)


## <a name="use-itsmc"></a>Utiliser ITSMC
   Vous pouvez utiliser ITSMC pour créer des éléments de travail à partir d’alertes Azure, d’alertes Log Analytics et d’enregistrements de journal Log Analytics.

## <a name="template-definitions"></a>Définitions des modèles
   Certains types d’éléments de travail peuvent utiliser des modèles définis par l’outil ITSM.
L’utilisation de modèles vous permet de définir des champs qui seront automatiquement renseignés en fonction de valeurs fixes définies comme faisant partie du groupe d’actions. Vous définissez les modèles dans l’outil ITSM. Vous pouvez définir le modèle que vous souhaitez utiliser dans le cadre de la définition du groupe d’actions.
      
## <a name="create-itsm-work-items-from-azure-alerts"></a>Créer des éléments de travail ITSM à partir d’alertes Azure

Après avoir créé votre connexion ITSM, vous pouvez créer des éléments de travail basés sur des alertes Azure dans votre outil ITSM. Pour créer les éléments de travail, vous utilisez l’action ITSM dans les groupes d’actions.

Les groupes d’actions offrent une méthode modulaire et réutilisable pour déclencher des actions pour vos alertes Azure. Vous pouvez utiliser des groupes d’actions avec des alertes de métriques, des alertes de journal d’activité et des alertes Azure Log Analytics dans le portail Azure.

> [!NOTE]
> Après avoir créé la connexion ITSM, vous devez attendre 30 minutes que le processus de synchronisation se termine.
> 

Utilisez la procédure suivante pour créer des éléments de travail :

1. Dans le portail Azure, sélectionnez **Alertes**.
2. Dans le menu situé en haut de l’écran, sélectionnez **Gérer les actions** :

    ![Capture d’écran montrant l’élément de menu Gérer les actions.](media/itsmc-overview/action-groups-selection-big.png)

   La fenêtre **Créer un groupe d’actions** s’affiche.

3. Sélectionnez l’**Abonnement** et le **Groupe de ressources** où vous voulez créer votre groupe d’actions. Indiquez un **Nom du groupe d’actions** et un **Nom d’affichage** pour votre groupe d’actions. Sélectionnez **Suivant : Notifications**.

    ![Capture d’écran montrant la fenêtre Créer un groupe d’actions.](media/itsmc-overview/action-groups-details.png)

4. Dans la liste des notifications, sélectionnez **Suivant : Actions**.
5. Dans la liste des actions, sélectionnez **ITSM** dans la liste **Type d’action**. Spécifiez un **nom** pour l’action. Sélectionnez le bouton de stylet qui représente **Modifier les détails**.
6. Dans la liste **Abonnement**, sélectionnez l’abonnement dans lequel se trouve votre espace de travail Log Analytics. Dans la liste **Connexion**, sélectionnez le nom de votre connecteur ITSM. Il sera suivi du nom de votre espace de travail. Par exemple, MonConnecteurITSM(MonEspaceDeTravail).

7. Sélectionnez un type d’**Élément de travail**.

8. Si vous voulez remplir des champs prêts à l’emploi avec des valeurs fixes, sélectionnez **Utiliser un modèle personnalisé**. Sinon, choisissez un [modèle](#template-definitions) existant dans la liste **Modèles**, puis entrez les valeurs fixes dans les champs du modèle.

9. Si vous sélectionnez **Créer des éléments de travail individuels pour chaque élément de configuration**, chaque élément de configuration dispose de son propre élément de travail. Il y a un élément de travail par élément de configuration. Il sera mis à jour en fonction des alertes qui seront créées.

   * Dans un cas, vous sélectionnez dans la liste déroulante de l’élément de travail « Incident » ou « Alert » : Si vous décochez la case **Créer des éléments de travail individuels pour chaque élément de configuration**, chaque alerte crée un élément de travail. Il peut y avoir plusieurs alertes par élément de configuration.

   ![Capture d’écran montrant la fenêtre Ticket ITSM.](media/itsmc-overview/itsm-action-configuration.png)
   
   * Dans un cas, vous sélectionnez dans la liste déroulante de l’élément de travail « Event » : Si vous sélectionnez **Créer des éléments de travail distincts pour chaque entrée de journal** dans la sélection des cases d’option, chaque alerte crée un élément de travail. Si vous sélectionnez **Créer des éléments de travail individuels pour chaque élément de configuration** dans la sélection des cases d’option, chaque élément de configuration dispose de son propre élément de travail.
   ![Capture d’écran montrant la fenêtre Ticket ITSM.](media/itsmc-overview/itsm-action-configuration-event.png)

10. Sélectionnez **OK**.

Quand vous créez ou modifiez une règle d’alerte Azure, utilisez un groupe d’actions qui contient une action ITSM. Quand l’alerte se déclenche, l’élément de travail est créé ou mis à jour dans l’outil ITSM.

> [!NOTE]
>
>- Pour plus d’informations sur les tarifs de l’action ITSM, consultez la [page de tarification](https://azure.microsoft.com/pricing/details/monitor/) pour les groupes d’actions.
>
>
>- Le champ de description courte de la définition de règle d’alerte est limité à 40 caractères quand vous l’envoyez à l’aide de l’action ITSM.


## <a name="visualize-and-analyze-the-incident-and-change-request-data"></a>Visualiser et analyser les données d’incident et de demande de modification

En fonction de la configuration choisie lors de l’établissement d’une connexion, ITSMC peut synchroniser jusqu’à 120 jours de données d’incidents et de demande de changement. Le schéma d’enregistrement de journal pour ces données est fourni dans la [prochaine section](#additional-information) de cet article.

Vous pouvez visualiser les données d’incident et de demande de changement à l’aide du tableau de bord ITSMC :

![Capture d’écran montrant le tableau de bord ITSMC.](media/itsmc-overview/itsmc-overview-sample-log-analytics.png)

Le tableau de bord fournit également des informations sur l’état du connecteur. Vous pouvez les utiliser comme point de départ pour analyser les problèmes liés aux connexions.

Vous pouvez également visualiser les incidents synchronisés avec les ordinateurs concernés dans Service Map.

La solution Carte de service détecte automatiquement les composants d’application sur les systèmes Windows et Linux et mappe la communication entre les services. Elle vous permet d’afficher les serveurs comme vous vous les représentez, c’est-à-dire comme des systèmes interconnectés qui fournissent des services critiques. Service Map affiche les connexions entre les serveurs, les processus et les ports sur n’importe quelle architecture connectée par TCP. Aucune configuration autre que l’installation d’un agent n’est exigée. Pour plus d’informations, consultez [Utilisation de Service Map](../insights/service-map.md).

Si vous utilisez Service Map, vous pouvez afficher les éléments de service d’assistance créés dans les solutions ITSM, comme indiqué ici :

![Capture d’écran montrant l’écran Log Analytics.](media/itsmc-overview/itsmc-overview-integrated-solutions.png)


## <a name="additional-information"></a>Informations supplémentaires

### <a name="data-synced-from-your-itsm-product"></a>Données synchronisées à partir de votre produit ITSM
Les incidents et les demandes de changement sont synchronisés entre votre produit ITSM et votre espace de travail Log Analytics, en fonction de la configuration de la connexion.

Cette section présente des exemples de données collectées par ITSMC.

Les champs présents dans **ServiceDesk_CL** varient en fonction du type d’élément de travail que vous importez dans Log Analytics. Voici une liste de champs pour deux types d’éléments de travail :

**Élément de travail :** **Incidents**  
ServiceDeskWorkItemType_s="Incident"

**Fields**

- ServiceDeskConnectionName
- ID du service d’assistance
- State
- Urgence
- Impact
- Priority
- Escalade
- Créé par
- Résolu par
- Fermé par
- Source
- Affecté à
- Category
- Intitulé
- Description
- Date de création
- Date de fermeture
- Date de résolution
- Date de dernière modification
- Computer


**Élément de travail :** **Demandes de modification**

ServiceDeskWorkItemType_s="ChangeRequest"

**Fields**
- ServiceDeskConnectionName
- ID du service d’assistance
- Créé par
- Fermé par
- Source
- Affecté à
- Intitulé
- Type
- Category
- State
- Escalade
- État conflictuel
- Urgence
- Priority
- Risque
- Impact
- Affecté à
- Date de création
- Date de fermeture
- Date de dernière modification
- Date de la demande
- Date de début prévue
- Date de fin prévue
- Date de début du travail
- Date de fin du travail
- Description
- Computer

## <a name="output-data-for-a-servicenow-incident"></a>Données de sortie pour un incident ServiceNow

| Champ Log Analytics | Champ ServiceNow |
|:--- |:--- |
| ServiceDeskId_s| Number |
| IncidentState_s | State |
| Urgency_s |Urgence |
| Impact_s |Impact|
| Priority_s | Priority |
| CreatedBy_s | Ouvert par |
| ResolvedBy_s | Résolu par|
| ClosedBy_s  | Fermé par |
| Source_s| Type de contact |
| AssignedTo_s | Affecté à  |
| Category_s | Category |
| Title_s|  Description courte |
| Description_s|  Notes |
| CreatedDate_t|  Ouvert |
| ClosedDate_t| Fermé|
| ResolvedDate_t|Résolu|
| Computer  | Élément de configuration |

## <a name="output-data-for-a-servicenow-change-request"></a>Données de sortie pour une demande de modification ServiceNow

| Log Analytics | Champ ServiceNow |
|:--- |:--- |
| ServiceDeskId_s| Number |
| CreatedBy_s | Demandé par |
| ClosedBy_s | Fermé par |
| AssignedTo_s | Affecté à  |
| Title_s|  Description courte |
| Type_s|  Type |
| Category_s|  Category |
| CRState_s|  State|
| Urgency_s|  Urgence |
| Priority_s| Priority|
| Risk_s| Risque|
| Impact_s| Impact|
| RequestedDate_t  | Date demandée |
| ClosedDate_t | Date de fermeture |
| PlannedStartDate_t  |     Date de début prévue |
| PlannedEndDate_t  |   Date de fin prévue |
| WorkStartDate_t  | Date de début réelle |
| WorkEndDate_t | Date de fin réelle|
| Description_s | Description |
| Computer  | Élément de configuration |


## <a name="troubleshoot-itsm-connections"></a>Dépanner les connexions ITSM
- Si une connexion échoue à partir de l’interface utilisateur de la source connectée et que le message **Erreur lors de l’enregistrement de la connexion** s’affiche, effectuez les étapes suivantes :
   - Pour les connexions ServiceNow, Cherwell et Provance :  
     - Vérifiez que vous avez correctement entré le nom d’utilisateur, le mot de passe, l’ID client et le secret client pour chacune des connexions.  
     - Veillez à disposer de privilèges suffisants dans le produit ITSM correspondant afin d’établir la connexion.  
   - Pour les connexions Service Manager :  
     - Vérifiez que l’application web est correctement déployée et que la connexion hybride est créée. Pour vérifier que la connexion est établie avec l’ordinateur Service Manager local, accédez à l’URL de l’application web, comme décrit dans la documentation concernant l’établissement d’une [connexion hybride](./itsmc-connections.md#configure-the-hybrid-connection).  

- Si les données de ServiceNow ne sont pas synchronisées dans Log Analytics, vérifiez que l’instance ServiceNow n’est pas en état de veille. Parfois, les instances de développement ServiceNow entrent en veille quand elles restent longtemps inactives. Si ce n’est pas ce qui se passe, signalez le problème.
- Si des alertes Log Analytics se déclenchent mais qu’aucun élément de travail n’est créé dans le produit ITSM, si aucun élément de configuration n’est créé/lié à des éléments de travail ou pour obtenir d’autres informations, consultez ces ressources :
   -  ITSMC : la solution montre un récapitulatif des connexions, éléments de travail, ordinateurs, etc. Sélectionnez la vignette qui a l’étiquette **État du connecteur**. Cela vous permet d’accéder à **Recherche dans les journaux** avec la requête appropriée. Pour plus d’informations, examinez les enregistrements de journal dont `LogType_S` a la valeur `ERROR`.
   - Page **Recherche dans les journaux** : Consultez les erreurs et les informations associées directement à l’aide de la requête `*ServiceDeskLog_CL*`.

## <a name="troubleshoot-service-manager-web-app-deployment"></a>Résoudre les problèmes de déploiement de l’application web Service Manager
-   Si vous rencontrez des problèmes lors du déploiement d’application web, vérifiez que vous disposez des autorisations nécessaires pour créer/déployer des ressources dans l’abonnement.
-   Si l’erreur **Référence d’objet non définie sur une instance d’un objet** s’affiche pendant l’exécution du [script](itsmc-service-manager-script.md), vérifiez que vous avez entré des valeurs valides dans la section **Configuration utilisateur**.
-   Si vous ne parvenez pas à créer l’espace de noms de Service Bus Relay, vérifiez que le fournisseur de ressources nécessaire est inscrit dans l’abonnement. S’il n’est pas inscrit, créez manuellement l’espace de noms Service Bus Relay à partir du portail Azure. Vous pouvez également le créer quand vous [créez la connexion hybride](./itsmc-connections.md#configure-the-hybrid-connection) dans le portail Azure.


## <a name="contact-us"></a>Nous contacter

Si vous avez des questions ou des commentaires concernant le connecteur de gestion des services informatiques, contactez-nous sur [omsitsmfeedback@microsoft.com](mailto:omsitsmfeedback@microsoft.com).

## <a name="next-steps"></a>Étapes suivantes
[Ajouter des produits/services ITSM au connecteur de gestion des services informatiques ](./itsmc-connections.md)