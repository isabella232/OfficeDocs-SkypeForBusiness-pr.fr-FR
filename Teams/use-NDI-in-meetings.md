---
title: Utiliser NDI dans Microsoft teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser NDI dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 86c0908b04b2eece835a747d9f57625878c15a99
ms.sourcegitcommit: 95989f1a93524a2025feeb50b8635da332961ea3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588288"
---
# <a name="use-ndi-in-microsoft-teams"></a>Utiliser NDI dans Microsoft teams

[!INCLUDE [template](includes/preview-feature.md)]

Network Device Interface (NDI) est une solution moderne de connexion des appareils multimédias (caméra et mixeur Studio, par exemple). Au lieu d’utiliser les connexions physiques, NDI autorise la connectivité via un intranet local, y compris sur un ordinateur local.

NewTek NDI® est devenu une solution standard pour la production de contenus en direct pour les flux et a gagné en connaissance et en adoption dans le monde de la diffusion professionnelle.

Skype a auparavant ajouté des fonctionnalités NDIes à Skype en fin de 2018. Microsoft teams tire parti de cette fonctionnalité pour améliorer l’utilisation de la réunion.

NDI est limité à un réseau local et ne doit être considéré qu’une partie du flux de travail de production, et non d’une solution de diffusion.

## <a name="turn-on-ndi"></a>Activation de NDI

L’activation de NDI nécessite deux étapes.

1. L’administrateur client doit activer la propriété « AllowNDIStreaming » dans CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Une fois cette modification remplie, l’utilisateur final doit activer NDI pour son client spécifique dans les **Settings**  >  **autorisations**de paramètres.

Lorsqu’un utilisateur rejoint une réunion, un message s’affiche indiquant que la réunion est en cours de diffusion. Si les utilisateurs ne veulent pas être inclus dans la diffusion, ils devront les supprimer de la réunion.

L’image ci-après illustre le message d’une bannière qu’un utilisateur voit dans une réunion Teams.

![Image de la bannière NDI qui s’affiche dans une réunion Teams.](media/NDI-disclosure.png)

La bannière comporte un lien vers la [politique de confidentialité Microsoft](https://aka.ms/teamsprivacy).

## <a name="supported-locales-and-user-types"></a>Paramètres régionaux et types d’utilisateurs pris en charge

NDI est pris en charge dans tous les pays/régions. Les utilisateurs suivants sont pris en charge dans une réunion NDI :

- In-client-support complet, fourni en fonction de sonnerie/IDClient/Id_utilisateur (géré par la stratégie de réunion)
- Federated-non (même lorsqu’ils ont NDI)<sup>1</sup>
- Freemium-non (valeur par défaut)
- Anonymat-non (valeur par défaut)
- Guest-non (valeur par défaut)

<sup>1</sup> les appareils ont un paramètre NDI qui est activé par défaut. Si un participant à une réunion utilise un appareil sur lequel NDI est désactivé, il doit activer NDI.