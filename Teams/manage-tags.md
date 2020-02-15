---
title: Gérer les balises dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Apprenez à gérer l’utilisation des indicateurs au sein de votre organisation dans Microsoft Teams.
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034499"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gérer les balises dans Microsoft teams

> [!NOTE]
> Cette fonctionnalité n’est pas encore affichée dans le centre d’administration Microsoft teams ? Ce service est actuellement déployé et n’est peut-être pas encore disponible dans votre organisation. Pour rester au courant des nouvelles fonctionnalités de teams, consultez la [documentation Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

Dans Microsoft Teams, les indicateurs permettent aux utilisateurs de communiquer avec un sous-ensemble de personnes d’une équipe. Les balises peuvent être ajoutées à un ou plusieurs membres de l’équipe pour se connecter facilement au sous-ensemble de personnes approprié. Les propriétaires d’équipe et les membres (si la fonctionnalité est activée pour eux) peuvent ajouter un ou plusieurs indicateurs à une personne. Vous pouvez ensuite utiliser les balises dans @mentions par tout membre de l’équipe dans un billet de canal pour communiquer uniquement aux personnes auxquelles cette balise est affectée.

> [!NOTE]
> Les balises ne sont pas encore prises en charge dans les canaux privés.

## <a name="how-tags-work"></a>Fonctionnement des indicateurs

Vous pouvez ajouter un indicateur à une personne d’une équipe spécifique. Dès lors que vous ajoutez une balise, celle-ci peut être utilisée dans @mentions de n’importe quel canal standard de l’équipe. Voici quelques exemples de la manière dont les indicateurs peuvent être utilisés dans teams :

- Un responsable du Windows Store veut publier une annonce dans un canal et en informer tous les caissiers.
- Un responsable de produit de groupe veut avertir tous les responsables de produits dans un canal.
- Un administrateur de l’hôpital veut envoyer un message à tous les Radiologists dans un canal.

Pour en savoir plus, voir [utilisation de balises dans teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

## <a name="manage-tags-for-your-organization"></a>Gérer les indicateurs de votre organisation

En tant qu’administrateur, vous pouvez contrôler qui peut ajouter des balises et comment les balises sont utilisées au sein de votre organisation dans le centre d’administration Microsoft Teams.

![Capture d’écran des paramètres de marquage dans le centre d’administration Microsoft teams](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a>Définir qui peut ajouter des indicateurs

Par défaut, les propriétaires d’équipe peuvent ajouter des balises. Vous pouvez modifier ce paramètre pour autoriser les propriétaires d’équipe et les membres de l’équipe à ajouter des indicateurs ou à désactiver les indicateurs de votre organisation.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur > **paramètres des équipes**des **paramètres à l’échelle**de l’organisation.
2. Sous **marquage**, en regard de l’option **étiquetage est activée pour**, sélectionnez l’une des options suivantes :

    - **Propriétaires et membres**d’une équipe : autoriser les propriétaires et les membres de l’équipe à ajouter des indicateurs.
    - **Propriétaires d’équipe**: autoriser les propriétaires d’équipe à ajouter des indicateurs.
    - **Désactivé**: désactiver les balises.

### <a name="configure-tags-settings"></a>Configurer les paramètres des indicateurs

Vous pouvez configurer les paramètres de balises suivants pour contrôler l’utilisation des balises au sein de votre organisation.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur > **paramètres des équipes**des **paramètres à l’échelle**de l’organisation.
2. Sous **marquage**, définissez les éléments suivants selon les besoins de votre organisation.

    - Le propriétaire d’une **équipe peut remplacer les personnes qui peuvent appliquer des indicateurs**: lorsque cette fonction est activée, les propriétaires d’équipe peuvent autoriser ou interdire les membres à ajouter des indicateurs dans les paramètres d’équipe.
    - **Les membres peuvent ajouter des indicateurs supplémentaires**: Si vous autorisez les membres de l’équipe à ajouter des indicateurs, activez cette option pour permettre aux membres de l’équipe d’ajouter des balises autres que les balises par défaut suggérées. Si cette option est désactivée, les membres de l’équipe peuvent uniquement utiliser les balises par défaut.
    - **Balises par défaut suggérées**: utilisez cet indicateur pour ajouter un ensemble de balises par défaut. Vous pouvez ajouter jusqu’à 25 indicateurs et chaque balise peut contenir un maximum de 25 caractères. Les propriétaires d’équipe et les membres (si la fonctionnalité est activée pour eux) peuvent utiliser ces suggestions, y ajouter ou créer un ensemble de balises.

## <a name="manage-tags-settings-for-a-team"></a>Gérer les paramètres des indicateurs pour une équipe

Si vous avez activé la case à coadresse le propriétaire de l' **équipe peut remplacer les utilisateurs qui peuvent appliquer des indicateurs** dans le centre d’administration Microsoft Teams, les propriétaires d’équipe peuvent définir si les membres peuvent ajouter des balises au niveau de l’équipe. Pour ce faire, dans l’onglet **paramètres** d’une équipe, accédez à **balises**, puis sélectionnez qui peut ajouter des indicateurs.

![Capture d’écran du paramètre balises au niveau de l’équipe](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a>Ajouter des balises dans teams

Dans Microsoft Teams, l’onglet **membres** de la page gérer l’équipe d’une équipe comprend une colonne **balises** . Les propriétaires d’équipe et les membres (si la fonctionnalité est activée pour eux), vous pouvez cliquer sur **gérer les indicateurs** en regard d’un membre pour afficher la liste des balises suggérées pour ce membre et ajouter des indicateurs à la liste.

![Capture d’écran de l’application de balises dans le client teams ](media/manage-tags-teams.png) 