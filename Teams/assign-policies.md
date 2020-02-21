---
title: Attribution de stratégies aux utilisateurs de Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez les différentes méthodes d’attribution de stratégies aux utilisateurs de Microsoft Teams.
f1keywords: ''
ms.openlocfilehash: cb1c5fd43379388327de5e517409f01f7f52ed1b
ms.sourcegitcommit: d7be89019dd5a3b88b0840bddf1b88fea8598ea7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170760"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Attribution de stratégies aux utilisateurs de Microsoft teams

> [!NOTE]
> **Deux des fonctionnalités de Microsoft teams abordées dans cet article, l’attribution de stratégie de [lot](#assign-a-policy-to-a-batch-of-users) et l' [attribution de stratégies aux groupes](#assign-a-policy-to-a-group), sont actuellement en version préliminaire.**

En tant qu’administrateur, vous utilisez des stratégies pour contrôler les fonctionnalités d’équipes disponibles pour les utilisateurs de votre organisation. Par exemple, il existe des stratégies d’appel, des stratégies de réunion et des stratégies de messagerie pour n’appeler qu’un seul nom.

Les organisations ont différents types d’utilisateurs dotés de besoins uniques et de stratégies personnalisées que vous créez et attribuez les paramètres de stratégie à différents ensembles d’utilisateurs en fonction de vos besoins.

Pour faciliter la gestion des stratégies au sein de votre organisation, teams permet d’attribuer des stratégies aux utilisateurs de différentes manières. Vous pouvez affecter une stratégie directement aux utilisateurs, individuellement ou à l’échelle via une affectation de lot ou à un groupe dont l’utilisateur est membre. Vous pouvez également utiliser des packages de stratégie pour affecter une collection prédéfinie de stratégies aux utilisateurs de votre organisation possédant des rôles similaires. L’option que vous choisissez dépend du nombre de stratégies que vous gérez et du nombre d’utilisateurs auxquels vous attribuez.

Cet article décrit les différentes façons dont vous pouvez attribuer des stratégies aux utilisateurs et les scénarios recommandés pour les situations dans lesquelles utiliser.

## <a name="which-policy-takes-precedence"></a>Quelle est la stratégie prioritaire ?

Un utilisateur dispose d’une stratégie efficace pour chaque type de stratégie. Il est possible, ou même probable, que l’utilisateur dispose d’une stratégie directement affectée et qu’il soit membre d’un ou plusieurs groupes auxquels une stratégie du même type est affectée. Dans ces types de scénarios, quelle stratégie est prioritaire ?  La stratégie d’effectivité d’un utilisateur est déterminée conformément aux règles de priorité, comme suit.

Si un utilisateur dispose d’une stratégie (individuelle ou par le biais d’une affectation de lot), cette stratégie est prioritaire. Dans l’exemple suivant, la stratégie effective de l’utilisateur est la stratégie de réunion carrée d’Lincoln, qui est directement affectée à l’utilisateur.

![Diagramme montrant comment une stratégie attribuée directement est prioritaire](media/assign-policies-example-directly-assigned.png)

Si un utilisateur n’a pas directement affecté une stratégie d’un type donné, la stratégie affectée à un groupe dont l’utilisateur est membre de a la priorité. Si un utilisateur est membre de plusieurs groupes, la stratégie présentant le niveau de [classement des affectations de groupe](#group-assignment-ranking) le plus élevé pour le type de stratégie donné est prioritaire.

Dans cet exemple, la stratégie effective de l’utilisateur est la stratégie d’exécution et la stratégie HD, qui présente le niveau d’attribution le plus élevé par rapport aux autres groupes dont l’utilisateur est membre et auquel une stratégie du même type de stratégie est affectée.  

![Diagramme montrant comment une stratégie héritée du groupe est prioritaire](media/assign-policies-example-group.png)

Si un utilisateur n’est pas directement affecté à une stratégie ou n’est pas membre de tous les groupes auxquels une stratégie est affectée, l’utilisateur obtient la stratégie globale (par défaut de l’organisation par défaut) pour ce type de stratégie. Voici un exemple :

![Diagramme illustrant le niveau de priorité d’une stratégie globale](media/assign-policies-example-global.png)

Pour en savoir plus, voir [règles de précédence](#precedence-rules).

## <a name="ways-to-assign-policies"></a>Méthodes d’attribution de stratégies

Vous trouverez ci-dessous une vue d’ensemble des méthodes permettant d’attribuer des stratégies aux utilisateurs et les scénarios recommandés pour chacun. Cliquez sur les liens pour en savoir plus.

|Procédez comme suit  |Si...  | Utilisation de...
|---------|---------|----|
|[Assigner une stratégie à des utilisateurs individuels](#assign-a-policy-to-individual-users)    | Vous débutez en équipe et vous commencez simplement à attribuer une ou plusieurs stratégies à un petit nombre d’utilisateurs. |Centre d’administration Microsoft teams ou cmdlets PowerShell dans le module PowerShell de Skype entreprise Online
| [Assigner un package de stratégie](#assign-a-policy-package)   | Vous devez affecter plusieurs stratégies à des ensembles d’utilisateurs spécifiques de votre organisation qui ont des rôles identiques ou similaires. Par exemple, attribuez le package de stratégie éducation (enseignant) aux enseignants de votre établissement scolaire pour leur permettre d’accéder à l’ensemble des conversations, appels et réunions, ainsi que le package d’étude (étudiant d’école secondaire) aux étudiants secondaires pour limiter certaines fonctionnalités, comme appels privés.  |Centre d’administration Microsoft teams ou cmdlets PowerShell dans le module PowerShell teams|
|[Attribuer une stratégie à un lot d’utilisateurs](#assign-a-policy-to-a-batch-of-users) (en préversion)   | Vous devez attribuer des stratégies à d’importants ensembles d’utilisateurs. Par exemple, vous pouvez attribuer une stratégie à des centaines ou des milliers d’utilisateurs de votre organisation à la fois.  |Cmdlets PowerShell dans le module PowerShell teams|
|[Assigner une stratégie à un groupe](#assign-a-policy-to-a-group) (en Preview)   |Vous devez attribuer des stratégies en fonction de l’appartenance d’un utilisateur à un groupe. Par exemple, vous souhaitez attribuer une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité ou d’une unité d’organisation.| Cmdlets PowerShell dans le module PowerShell teams|
| Assigner un package de stratégie à un lot d’utilisateurs (bientôt disponible) |||
| Assigner un package de stratégie à un groupe (bientôt disponible)   | ||

## <a name="assign-a-policy-to-individual-users"></a>Assigner une stratégie à des utilisateurs individuels

Procédez comme suit pour attribuer une stratégie à un utilisateur individuel ou à un petit nombre d’utilisateurs à la fois.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft teams

Pour attribuer une stratégie à un utilisateur :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis cliquez sur l’utilisateur.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de l’utilisateur, puis sur **modifier les paramètres**.
3. Sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **appliquer**.

Pour attribuer une stratégie à un maximum de 20 utilisateurs à la fois, voir [modifier les paramètres utilisateur d’équipes en bloc](edit-user-settings-in-bulk.md).

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la page de stratégie.
2. Sélectionnez la stratégie que vous voulez affecter en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **gérer les utilisateurs**.
4. Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Chacun d’eux dispose d’un ensemble de cmdlets pour le gérer. Utilisez l' ```Grant-``` applet de cmdlet d’un type de stratégie donné pour affecter la stratégie. Par exemple, utilisez l' ```Grant-CsTeamsMeetingPolicy``` applet de cmdlet pour attribuer une stratégie de réunion teams à des utilisateurs. Ces applets de service sont inclus dans le module PowerShell de Skype entreprise Online et sont décrits dans la référence de l’applet de connexion [Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

 Téléchargez et installez le [module PowerShell de Skype entreprise Online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (si vous ne l’avez pas déjà fait), puis exécutez la commande suivante pour vous connecter à Skype entreprise Online et commencer une session.

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

Dans cet exemple, nous affectons une stratégie de réunion teams nommée Stratégie de réunion étudiant à un utilisateur nommé reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Pour en savoir plus, voir [gestion des stratégies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).

## <a name="assign-a-policy-package"></a>Assigner un package de stratégie

Un package de stratégie dans teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs qui ont des rôles similaires ou similaires au sein de votre organisation. Chaque package de stratégie est conçu à l’aide d’un rôle d’utilisateur et comprend des stratégies et des paramètres de stratégie prédéfinis qui prennent en charge les activités typiques pour ce rôle. Voici quelques exemples de packages de stratégie : le package éducation (enseignant) et le module Healthcare (Medical Worker).

Lorsque vous attribuez un package de stratégie aux utilisateurs, les stratégies du package sont créées et vous pouvez personnaliser les paramètres de chaque stratégie du package pour répondre aux besoins des utilisateurs.

Pour en savoir plus sur les packages de stratégie, y compris des instructions détaillées sur la manière de les affecter et de les gérer, voir [gérer les packages de stratégie dans teams](manage-policy-packages.md).

## <a name="assign-a-policy-to-a-batch-of-users"></a>Attribuer une stratégie à un lot d’utilisateurs

[!INCLUDE [preview-feature](includes/preview-feature.md)]
 
Avec une affectation de stratégie de lot, vous pouvez attribuer une stratégie à un grand nombre d’utilisateurs à la fois sans avoir à utiliser de script. Utilisez l' ```New-CsBatchPolicyAssignmentOperationd``` applet de commande pour signaler un lot d’utilisateurs et la stratégie que vous voulez affecter. Les affectations sont traitées en tant qu’opérations en arrière-plan et chaque lot est généré. Vous pouvez ensuite utiliser l' ```Get-CsBatchPolicyAssignmentOperation``` applet de commande pour effectuer le suivi de l’avancement et de l’état des devoirs d’un lot.

Un lot peut contenir jusqu’à 20 000 utilisateurs. Vous pouvez spécifier des utilisateurs selon leur ID d’objet, leur nom d’utilisateur principal (UPN), leur adresse SIP (Session Initiation Protocol) ou leur adresse de messagerie.

> [!NOTE]
> Pour l’instant, l’affectation de stratégie de lot n’est pas disponible pour tous les types de stratégies d’équipe. Pour obtenir la liste des types de stratégie pris en charge, voir [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) .

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installer le module Microsoft teams PowerShell et s’y connecter

> [!NOTE]
> Les applets de contrôle se trouvent dans la version préliminaire du module PowerShell Teams. Suivez ces étapes pour commencer par désinstaller la version disponible en général du module PowerShell Teams (s’il est installé), puis installez la dernière version préliminaire du module à partir de la Galerie de tests PowerShell.

Si ce n’est déjà fait, exécutez la commande suivante pour inscrire la Galerie de tests PowerShell comme source fiable.

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

Si vous avez installé la version disponible en général du module PowerShell Teams, exécutez la commande suivante pour la désinstaller.

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

Exécutez la commande suivante pour installer le module Microsoft teams PowerShell le plus récent à partir de la Galerie de tests PowerShell.

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

Exécutez la commande suivante pour vous connecter à teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```

Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installez et connectez-vous à Azure AD PowerShell pour le module Graph (facultatif)

Vous pouvez également [Télécharger et installer le module Azure ad PowerShell pour Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (le cas échéant) et vous connecter à Azure AD pour récupérer la liste des utilisateurs de votre organisation.

Exécutez la commande suivante pour vous connecter à Azure AD.

```powershell
Connect-AzureAD
```

Lorsque vous y êtes invité, connectez-vous à l’aide des informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Teams.

### <a name="assign-a-policy-to-a-batch-of-users"></a>Attribuer une stratégie à un lot d’utilisateurs

Dans cet exemple, nous utilisons l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour assigner une stratégie d’installation d’application nommée Stratégie de configuration des applications humaines à un lot d’utilisateurs répertoriés dans le fichier Users_ids. Text.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

Dans cet exemple, nous allons nous connecter à Azure AD pour récupérer une collection d’utilisateurs, puis attribuer une stratégie d’échange nommée nouvelle stratégie de messagerie à un lot d’utilisateurs spécifiés à l’aide de leur UPN.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

Pour en savoir plus, voir [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).

### <a name="get-the-status-of-a-batch-assignment"></a>Obtenir l’état d’une affectation par lot

Exécutez la commande suivante pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par ```New-CsBatchPolicyAssignmentOperation``` l’applet de commande pour un lot donné.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Si la sortie indique qu’une erreur s’est produite, exécutez la commande suivante pour obtenir plus d’informations sur les erreurs ```UserState``` qui se trouvent dans la propriété.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Pour en savoir plus, consultez la rubrique [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="assign-a-policy-to-a-group"></a>Assigner une stratégie à un groupe

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Attribution de stratégie aux groupes vous permet d’affecter une stratégie à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une unité d’organisation. L’affectation de stratégie est propagée aux membres du groupe conformément aux règles de priorité. Les membres étant ajoutés ou supprimés d’un groupe, leurs affectations de stratégie héritées sont mises à jour en conséquence.

Vous pouvez utiliser ```New-CsGroupPolicyAssignment``` l’applet de cmdlet pour attribuer une stratégie à un groupe. Vous pouvez spécifier un groupe à l’aide d’un ID d’objet, d’une adresse SIP ou d’une adresse de messagerie.

Lorsque vous affectez la stratégie, celle-ci est immédiatement affectée au groupe. Toutefois, Notez que la propagation de l’affectation de stratégie aux membres du groupe est effectuée en tant qu’opération en arrière-plan et peut prendre un certain temps selon la taille du groupe. Il en va de même lorsque la stratégie n’est pas attribuée à un groupe, ou lorsque les membres sont ajoutés à un groupe ou supprimés.

> [!NOTE]
> Pour l’instant, l’affectation de stratégie à des groupes n’est pas disponible pour tous les types de stratégie d’équipe. Pour obtenir la liste des types de stratégie pris en charge, voir [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Ce que vous devez savoir sur l’attribution de stratégies aux groupes

Avant de commencer, il est important de comprendre les règles de précédence et le classement des affectations de groupe.

#### <a name="precedence-rules"></a>Règles de précédence

Pour un type de stratégie donné, la stratégie effective d’un utilisateur est déterminée conformément aux éléments suivants :

- Une stratégie attribuée directement à un utilisateur est prioritaire sur une autre stratégie du même type affectée à un groupe. En d’autres termes, si un utilisateur reçoit directement une stratégie d’un type donné, il n’hérite pas d’une stratégie du même type d’un groupe. En d’autres termes, si un utilisateur possède une stratégie d’un type donné qui lui a été directement affecté, vous devez supprimer cette stratégie de l’utilisateur pour pouvoir hériter d’une stratégie du même type d’un groupe.
- Si un utilisateur ne dispose pas directement d’une stratégie et est membre de deux groupes ou plus, et qu’il dispose d’une stratégie du même type qui lui est affecté, il hérite de la stratégie du groupe affecté dont le classement est le plus élevé.
- Si un utilisateur n’est pas membre de groupes auxquels une stratégie est affectée, la stratégie globale par défaut de l’Organisation pour ce type de stratégie s’applique à l’utilisateur.

La stratégie effective d’un utilisateur est mise à jour en fonction de ces règles lorsqu’un utilisateur est ajouté ou supprimé d’un groupe auquel est affectée une stratégie, qu’une stratégie n’est pas attribuée à partir d’un groupe ou qu’une stratégie attribuée directement à l’utilisateur est supprimée.

#### <a name="group-assignment-ranking"></a>Classement des affectations de groupe
 
Lorsque vous affectez une stratégie à un groupe, vous spécifiez le classement de l’affectation de groupe. Il est utilisé pour identifier la stratégie qu’un utilisateur doit hériter en tant que stratégie effective si l’utilisateur est membre de deux groupes ou plus et qu’une stratégie du même type est affectée à chaque groupe.

Le classement des affectations de groupe est relatif par rapport à d’autres affectations de groupe du même type. Par exemple, si vous attribuez une stratégie d’appel à deux groupes, définissez le classement d’une affectation sur 1 et l’autre sur 2, avec 1 en tant que classement le plus élevé. Le classement des affectations de groupe indique l’appartenance au groupe qui est la plus importante ou la plus pertinente par rapport à d’autres appartenances aux groupes en ce qui concerne l’héritage.
 
Imaginons, par exemple, que vous avez deux groupes, que vous stockez des employés et des responsables du magasin. Les deux groupes se voient attribuer une stratégie d’appel d’équipes, et les employés de la stratégie d’appel et de la stratégie d’appel des responsables de la boutique sont respectivement. Dans le cas d’un responsable du Windows Store qui se trouve dans les deux groupes, son rôle en tant que responsable est supérieur à celui d’un employé, de sorte que la stratégie d’appel attribuée au groupe responsables du magasin doit présenter un niveau de classement supérieur.

|Groupe |Nom de la stratégie d’appel teams  |Classement|
|---------|---------|---|
|Responsables du Windows Store   |Stratégie d’appel des directeurs du Windows Store         |1|
|Magasin employés    |Politique d’appel des employés du Store      |deuxième|

Si vous ne spécifiez pas de classement, l’affectation de la stratégie est affectée du plus petit classement.

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installer le module Microsoft teams PowerShell et s’y connecter

> [!NOTE]
> Les applets de contrôle se trouvent dans la version préliminaire du module PowerShell Teams. Suivez ces étapes pour commencer par désinstaller la version disponible en général du module PowerShell Teams (s’il est installé), puis installez la dernière version préliminaire du module à partir de la Galerie de tests PowerShell.

Si ce n’est déjà fait, exécutez la commande suivante pour inscrire la Galerie de tests PowerShell comme source fiable.

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

Si vous avez installé la version disponible en général du module PowerShell Teams, exécutez la commande suivante pour la désinstaller.

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

Exécutez la commande suivante pour installer le module Microsoft teams PowerShell le plus récent à partir de la Galerie de tests PowerShell.

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

Exécutez la commande suivante pour vous connecter à teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```

Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.

### <a name="assign-a-policy-to-a-group"></a>Assigner une stratégie à un groupe

Dans cet exemple, nous utilisons l' ```New-CsGroupPolicyAssignment``` applet de cmdlet pour assigner une stratégie de réunion équipes nommée Stratégie de réunion des responsables de revente à un groupe dont le classement de devoirs est 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

Pour en savoir plus, voir [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).

### <a name="get-policy-assignments-for-a-group"></a>Obtenir des affectations de stratégie pour un groupe

Utilisez l' ```Get-CsGroupPolicyAssignment``` applet de cmdlet pour obtenir toutes les stratégies attribuées à un groupe. Notez que les groupes sont toujours répertoriés par leur ID de groupe même si l’adresse ou l’adresse de messagerie SIP a été utilisée pour affecter la stratégie.

Dans cet exemple, nous récupérons toutes les stratégies affectées à un groupe spécifique.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

Dans cet exemple, nous renvoyons tous les groupes auxquels une stratégie de réunion équipes est affectée.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

Pour en savoir plus, consultez la rubrique [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).

### <a name="remove-a-policy-from-a-group"></a>Supprimer une stratégie d’un groupe

Utilisez l' ```Remove-CsGroupPolicyAssignment``` applet de cmdlet pour supprimer une stratégie de groupe. Lorsque vous supprimez une stratégie d’un groupe, les priorités des autres stratégies du même type attribuées à ce groupe et dont le classement est inférieur sont mises à jour. Par exemple, si vous supprimez une stratégie de classement de 2, les stratégies dont le classement est 3 et 4 sont mis à jour pour refléter leur nouveau classement. Les deux tables suivantes montrent cet exemple.

Vous trouverez ci-dessous une liste des affectations et des priorités pour une stratégie de réunion Teams.

|Nom du groupe  |Nom de la stratégie  |Classement|
|---------|---------|---------|
|Ventes    |Politique de vente       | 1        |
|Région ouest     |Politique de la région ouest         |deuxième         |
|Division    |Politique de division         |3         |
|Complémentaire   |Politique subsidiaire        |4         |

Si nous supprimons la politique de la région ouest du groupe région ouest, les affectations et les priorités de la stratégie sont mises à jour comme suit.

|Nom du groupe  |Nom de la stratégie  |Classement|
|---------|---------|---------|
|Ventes    |Politique de vente       | 1        |
|Division    |Politique de division         |deuxième         |
|Complémentaire   |Politique subsidiaire        |3        |

Dans cet exemple, nous supprimons la stratégie de réunion teams d’un groupe.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

Pour en savoir plus, consultez la rubrique [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).

### <a name="change-a-policy-assignment-for-a-group"></a>Modifier une affectation de stratégie pour un groupe

Après avoir affecté une stratégie à un groupe, vous pouvez utiliser l' ```Set-CsGroupPolicyAssignmentd``` applet de cmdlet pour modifier l’affectation de stratégie de ce groupe comme suit :

- Changer le classement
- Modifier la stratégie d’un type de stratégie donné
- Modification de la stratégie d’un type de stratégie donné et du classement

Dans cet exemple, nous affectons à la stratégie de parc d’appels de groupe une stratégie nommée SupportCallPark et le classement de l’affectation à 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

Pour en savoir plus, consultez la rubrique [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).

### <a name="change-the-effective-policy-for-a-user"></a>Modification de la stratégie d’effectivité d’un utilisateur

Voici un exemple illustrant la modification de la stratégie d’effectivité d’un utilisateur qui a directement affecté une stratégie.

Tout d’abord, nous ```Get-CsUserPolicyAssignment``` utilisons l’applet de ```PolicySource``` connexion conjointement avec le paramètre pour obtenir des informations sur les stratégies de diffusion de réunion associées à l’utilisateur. Pour en savoir plus, consultez la rubrique [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

La sortie montre que l’utilisateur a été directement affecté à une stratégie de diffusion de réunion teams nommée événements de l’employé, qui est prioritaire sur la stratégie nommée événements dynamiques du fournisseur qui est affectée à un groupe auquel l’utilisateur appartient.

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

À présent, nous supprimons la stratégie d’événements des employés de l’utilisateur. Cela signifie que l’utilisateur ne dispose plus d’une stratégie de diffusion de réunion teams et qu’il hérite de la stratégie d’événements en direct du fournisseur qui est affectée au groupe auquel l’utilisateur appartient. 

Utilisez l’applet de commande suivante dans le module PowerShell Skype entreprise pour effectuer cette opération.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Pour ce faire, vous pouvez utiliser l’applet de commande suivante dans le module PowerShell teams pour procéder à la mise à niveau en utilisant une affectation de stratégie de lot dans laquelle $users est une liste d’utilisateurs que vous spécifiez.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="related-topics"></a>Rubriques connexes

- [Aperçu de Teams PowerShell](teams-powershell-overview.md)