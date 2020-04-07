---
title: Authentification dans les salles de Microsoft teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Découvrir comment configurer l’authentification moderne pour les salles Microsoft teams
ms.openlocfilehash: bef547ab0b9ade2edc433ec64bb1ef61eee4c040
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160111"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Authentification dans les salles de Microsoft teams

La gestion des comptes pour les appareils Microsoft teams est gérée au niveau de l’application. L’application se connecte à Microsoft Teams, à Skype entreprise et à Exchange pour obtenir des ressources pour le compte de la salle afin d’activer les appels et les expériences de réunion. Le compte est maintenu de manière indépendante pour permettre des fonctionnalités toujours disponibles, des scénarios d’appel (pour les appareils configurés avec un plan d’appels) et des mécanismes de verrouillage personnalisés implémentés sur ces appareils. Cela signifie que l’authentification de ces périphériques se produit de manière différente de celle des appareils utilisateurs finaux.  

L’authentification moderne est recommandée pour tous les clients utilisant des appareils Microsoft teams salles avec Office 365. Si vous avez un déploiement local d’Exchange Server ou de Skype entreprise Server, configurez [l’authentification moderne hybride](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) avec Azure Active Directory (Azure AD) pour permettre l’utilisation de l’authentification moderne.

L’authentification moderne est prise en charge dans Microsoft Teams (version 4.4.25.0 et versions ultérieures).

## <a name="modern-authentication"></a>Authentification moderne

Lorsque vous utilisez l’authentification moderne avec l’application Microsoft teams Resources, la bibliothèque d’authentification Active Directory (ADAL) est utilisée pour se connecter à Microsoft Teams, Exchange et Skype entreprise. Un appareil de salle Microsoft teams est un appareil partagé et effectue un redémarrage nocturne pour garantir un fonctionnement fluide et obtenir des mises à jour de systèmes d’exploitation, de microprogrammes ou de microprogrammes importants. Le mécanisme d’authentification moderne utilise le type d’autorisation d’accès au [mot de passe du propriétaire de ressources](https://tools.ietf.org/html/rfc6749#section-1.3.3) dans OAuth 2,0, qui ne nécessite aucune intervention de l’utilisateur. Il s’agit de l’une des principales différences entre le fonctionnement de l’authentification moderne pour les comptes d’utilisateurs et les comptes de ressources qui sont utilisés par l’application Microsoft Teams. Pour cette raison, les comptes de ressources de Microsoft Teams ne doivent pas être configurés de manière à utiliser l’authentification multifacteur (MFA), l’authentification par carte à puce ou l’authentification par certificat client (qui sont disponibles pour les utilisateurs finaux).

La différence principale entre le fonctionnement de l’authentification moderne sur les appareils Microsoft teams et les appareils utilisateurs finaux réside dans le fait que vous ne pouvez pas utiliser un compte de ressources pour appliquer des stratégies d’accès conditionnel au niveau de l’appareil, telles que « nécessiter l’inscription d’un appareil en tant que plainte » ou « nécessiter un appareil Azure AD hybride », et ainsi de suite. En effet, les concepts de niveau périphérique ne s’appliquent pas à l’authentification moderne lorsqu’elle est utilisée au niveau de l’application. Au lieu de cela, vous pouvez inscrire un appareil dans Microsoft Intune et appliquer des stratégies de conformité à l’aide de [ces instructions.](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess)

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Activer l’authentification moderne sur un appareil Microsoft teams

Pour que Microsoft teams se réutilise l’authentification moderne dans Skype entreprise et Exchange, activez le paramètre côté client pour l’authentification moderne sur le périphérique Microsoft Teams. Pour cela, vous pouvez utiliser les paramètres de l’appareil ou le fichier de configuration XML.

> [!NOTE]
> Avant d’activer le paramètre côté client pour l’authentification moderne, assurez-vous que votre environnement est correctement configuré pour utiliser l’authentification moderne.

### <a name="using-device-settings"></a>Utiliser les paramètres de l’appareil

1. Sur l’appareil Microsoft Teams, accédez à **plus** (**...**).
    
2. Sélectionnez **paramètres**, puis entrez le nom d’utilisateur et le mot de passe de l’administrateur de l’appareil.
3. Accédez à l’onglet **compte** , activez **l’authentification moderne**, puis sélectionnez **enregistrer et quitter**.

### <a name="using-the-xml-config-file"></a>Utilisation du fichier de configuration XML

Dans votre fichier SkypeSettings. xml, définissez l’élément XML d’authentification moderne sur **true**, comme suit.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Pour appliquer le paramètre, voir [gérer les paramètres de la console Microsoft teams à distance à l’aide d’un fichier de configuration XML](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Préparer votre environnement pour l’authentification moderne

Avant de commencer, assurez-vous de bien comprendre les modèles d’identité à utiliser avec Office 365 et Azure AD. Vous pouvez en savoir plus sur les [modèles d’identité d’office 365 et sur Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) et à l' [identité hybride et à la synchronisation d’annuaires pour Office 365](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-office-365"></a>Activer l’authentification moderne dans Office 365

Pour activer l’authentification moderne pour Exchange Online, voir [activer l’authentification moderne dans Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online). Si vous utilisez Skype entreprise Online, vous devez également vérifier que l’authentification moderne est activée pour Skype entreprise online. Pour en savoir plus, reportez-vous à [la rubrique Skype entreprise Online : activer votre client pour l’authentification moderne](https://aka.ms/SkypeModernAuth).

Nous vous conseillons de ne pas supprimer les stratégies d’authentification de base pour Exchange Online ou de désactiver l’authentification de base pour votre client avant que vous n’ayez pu valider que le paramètre d’authentification moderne puisse se connecter à Exchange Online et teams ou à Skype entreprise Online lorsque le paramètre d’authentification moderne est activé et qu’aucun appareil n’est encore configuré pour utiliser l’authentification de base.

Pour plus d’informations sur la désactivation de l’authentification de base dans Exchange Online, voir [désactiver l’authentification de base dans Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Authentification moderne hybride

Pour garantir une authentification réussie de votre serveur Exchange local et/ou de Skype entreprise Server, vous devez vous assurer que le compte de ressources utilisé avec les salles de Microsoft teams est configuré pour obtenir l’autorisation d’Azure AD. Pour en savoir plus sur l’identité hybride et les méthodes qui conviennent à votre organisation, consultez les rubriques suivantes : 

- [Qu’est-ce que la synchronisation du hachage du mot de passe ?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-phs)
- [Qu’est-ce que l’authentification par relais ?](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta)
- [Qu’est-ce que la Fédération ?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-fed)

### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Éléments requis spécifiques aux salles de Microsoft teams

La configuration requise pour activer l’authentification moderne dans votre topologie hybride est abordée dans la [vue d’ensemble de l’authentification moderne hybride et les prérequis pour une utilisation avec des serveurs Skype entreprise et Exchange locaux](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview). Tous les éléments requis mentionnés dans l’article s’appliquent.

Toutefois, étant donné que Microsoft teams se sert de l’autorisation [d’identification du mot de passe de propriétaire de ressources](https://tools.ietf.org/html/rfc6749#section-1.3.3) et des API REST sous-jacentes pour l’authentification moderne, il existe des différences importantes qui sont spécifiques aux salles d’équipe Microsoft.

- Vous devez disposer d’Exchange Server 2016 CU8 ou version ultérieure, ou d’Exchange Server 2019 CU1 ou version ultérieure.
- Vous devez disposer de Skype entreprise Server 2015 CU5 ou version ultérieure, ou de Skype entreprise Server 2019 ou version ultérieure.
- L’authentification multifacteur n’est pas prise en charge, quelle que soit la topologie que vous utilisez.
- Si vous utilisez un fournisseur d’authentification tiers pris en charge par Azure AD, il doit prendre en charge OAuth et utiliser l’autorisation d’identification du mot de passe de propriétaire de ressources.
- N’utilisez pas de stratégies d’accès conditionnel au niveau de l’appareil pour un compte de ressources configuré avec l’application. Cela entraînera des échecs de connexion. Au lieu de cela, inscrivez un appareil dans Microsoft Intune et appliquez les stratégies de conformité à l’aide de l’aide publiée [ici](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).

### <a name="configure-exchange-server"></a>Configurer Exchange Server

Pour activer l’authentification moderne hybride dans Exchange Server, reportez-vous [à la rubrique Configuration d’Exchange Server local pour utiliser l’authentification moderne hybride](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Configurer Skype entreprise Server

Pour activer l’authentification moderne hybride avec Skype entreprise Server, reportez-vous [à la configuration de Skype entreprise sur site pour utiliser l’authentification moderne hybride](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Suppression ou désactivation de Skype entreprise et Exchange

Si votre configuration n’autorise pas l’authentification moderne hybride ou si vous devez supprimer ou désactiver l’authentification moderne hybride pour Exchange ou Skype entreprise, reportez-vous à la rubrique [retrait ou désactivation de l’authentification moderne hybride de Skype entreprise et Exchange](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Accès conditionnel Azure AD

Vous pouvez configurer un compte de ressources utilisé avec les salles de Microsoft teams pour l’accès par adresse IP/par emplacement. Pour en savoir plus, voir [accès conditionnel : bloquer l’accès par emplacement](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Aucune autre stratégie d’accès conditionnel n’est prise en charge. Pour plus d’informations sur la compatibilité des appareils, voir les conseils [ici](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).  