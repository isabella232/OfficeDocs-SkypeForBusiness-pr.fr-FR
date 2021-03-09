---
title: Configurer Microsoft Teams dans votre petite entreprise
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Configurez Teams dans votre petite entreprise pour permettre à vos utilisateurs de collaborer à l’aide de la conversation et du partage de fichiers, configurer à des réunions de petite et grande taille, puis d’y participer, et discuter par vidéo et voix.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bbadcd18050d098d9c602f7ba56da40ecafd89b4
ms.sourcegitcommit: 6785d7f1ef5d2010ab334ec8cc46884327a53662
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2021
ms.locfileid: "50395416"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a><span data-ttu-id="c9195-103">Configurer Microsoft Teams dans votre petite entreprise</span><span class="sxs-lookup"><span data-stu-id="c9195-103">Set up Microsoft Teams in your small business</span></span>

<span data-ttu-id="c9195-104">Il existe de nombreuses façons de personnaliser Teams.</span><span class="sxs-lookup"><span data-stu-id="c9195-104">There are lots of ways you can customize Teams.</span></span> <span data-ttu-id="c9195-105">Les sections suivantes vous montrent comment configurer chaque charge de travail Teams : **conversations, équipes et canaux** ; **réunions et conférences** ; et **voix cloud**.</span><span class="sxs-lookup"><span data-stu-id="c9195-105">The following sections show you how to set up each Teams workload: **chats, teams and channels**; **meetings and conferencing**; and **cloud voice**.</span></span> <span data-ttu-id="c9195-106">Vous devez définir l’ordre de configuration de chaque charge de travail.</span><span class="sxs-lookup"><span data-stu-id="c9195-106">The order in which you set up each workload is up to you.</span></span> <span data-ttu-id="c9195-107">Nous vous recommandons de commencer par définir d’abord les conversations, les équipes et les canaux de charge de travail. Cependant, vous pouvez commencer par des réunions et des conférences, voire la voix cloud.</span><span class="sxs-lookup"><span data-stu-id="c9195-107">While we recommend setting up the chats, teams, and channels workload first, you can start with meetings and conferencing or even cloud voice.</span></span> <span data-ttu-id="c9195-108">Le choix vous appartient.</span><span class="sxs-lookup"><span data-stu-id="c9195-108">The choice is yours.</span></span>

> [!NOTE]
> <span data-ttu-id="c9195-109">Si vous ne l’avez pas déjà fait, nous vous recommandons vivement de commencer votre déploiement Teams par un pilote.</span><span class="sxs-lookup"><span data-stu-id="c9195-109">If you haven't done so already, we strongly suggest that you begin your Teams deployment with a pilot.</span></span> <span data-ttu-id="c9195-110">Un pilote vous permettra, ainsi qu'à quelques utilisateurs précoces, de vous familiariser avec Teams et ses fonctionnalités avant votre planification et votre déploiement éventuel. Si vous souhaitez en savoir plus sur le démarrage de votre pilote, veuillez consulter la page [Prise en main de Microsoft Teams](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="c9195-110">A pilot will allow you and a few early adopters to get familiar with Teams and its features before your planning and eventual roll out. For more information about how to start your pilot, check out [Get started with Microsoft Teams](get-started-with-teams-quick-start.md).</span></span>

<span data-ttu-id="c9195-111">Avant de déployer Teams à grande échelle, pour vérifier que votre organisation est prête, veuillez consulter la section [Vérifiez que vous êtes prêt](get-started-with-teams-quick-start.md#make-sure-youre-ready).</span><span class="sxs-lookup"><span data-stu-id="c9195-111">Before you roll out Teams broadly, make sure your organization is ready by reviewing the items in [Make sure you're ready](get-started-with-teams-quick-start.md#make-sure-youre-ready).</span></span>

<span data-ttu-id="c9195-112">Passez à la section qui vous intéresse :</span><span class="sxs-lookup"><span data-stu-id="c9195-112">Jump to the section you're interested in:</span></span>

- [<span data-ttu-id="c9195-113">Charges de travail</span><span class="sxs-lookup"><span data-stu-id="c9195-113">Workloads</span></span>](#workloads)
  - [<span data-ttu-id="c9195-114">Conversation, équipes et canaux</span><span class="sxs-lookup"><span data-stu-id="c9195-114">Chat, teams, and channels</span></span>](#chat-teams-and-channels)
  - [<span data-ttu-id="c9195-115">Réunions et conférences</span><span class="sxs-lookup"><span data-stu-id="c9195-115">Meetings and conferencing</span></span>](#meetings-and-conferencing)
  - [<span data-ttu-id="c9195-116">Business Voice</span><span class="sxs-lookup"><span data-stu-id="c9195-116">Business Voice</span></span>](#business-voice)
- [<span data-ttu-id="c9195-117">Déploiement des clients</span><span class="sxs-lookup"><span data-stu-id="c9195-117">Deploy clients</span></span>](#deploy-clients)
- [<span data-ttu-id="c9195-118">Formation</span><span class="sxs-lookup"><span data-stu-id="c9195-118">Training</span></span>](#training)

## <a name="workloads"></a><span data-ttu-id="c9195-119">Charges de travail</span><span class="sxs-lookup"><span data-stu-id="c9195-119">Workloads</span></span>
### <a name="chat-teams-and-channels"></a><span data-ttu-id="c9195-120">Conversation, équipes et canaux</span><span class="sxs-lookup"><span data-stu-id="c9195-120">Chat, teams, and channels</span></span>

<span data-ttu-id="c9195-121">La conversation, les équipes et les canaux sont la clé de l’utilisation de Teams.</span><span class="sxs-lookup"><span data-stu-id="c9195-121">Chat, teams, and channels, are the cornerstone of Teams.</span></span> <span data-ttu-id="c9195-122">La **conversation** permet à un ou plusieurs utilisateurs de discuter, de partager des fichiers, puis de se réunir en privé.</span><span class="sxs-lookup"><span data-stu-id="c9195-122">**Chat** lets one or more users talk to each other, share files, and meet privately.</span></span> <span data-ttu-id="c9195-123">Les **équipes**, visibles par tous les membres de votre organisation ou seulement par les membres de l’équipe, permettent aux bonnes personnes collaborer quelle que soit la tâche ou l’occasion, qu’il s’agisse d’un projet de longue durée ou d’une fête d’anniversaire.</span><span class="sxs-lookup"><span data-stu-id="c9195-123">**Teams**, which can be visible to everyone in your organization or only to those in the team, let the right people collaborate whatever the task or occasion, whether it's a long-running project or planning for a birthday party.</span></span> <span data-ttu-id="c9195-124">Les **canaux** au sein des équipes peuvent segmenter des sujets, des projets, des services ou toute autre chose qui a du sens pour votre équipe.</span><span class="sxs-lookup"><span data-stu-id="c9195-124">**Channels** within teams can segment topics, projects, departments, or anything else make sense for your team.</span></span> <span data-ttu-id="c9195-125">Si vous souhaitez en savoir plus sur les conversations, les équipes et les canaux, veuillez consulter la rubrique [Vue d’ensemble des équipes et canaux](teams-channels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c9195-125">For details about chat, teams, and channels, check out [Overview of teams and channels](teams-channels-overview.md).</span></span>

> [!TIP]
> <span data-ttu-id="c9195-126">Découvrez comment gérer les rôles d’équipe, l’accès et les stratégies de messagerie en complétant le module [Gérer Microsoft Teams](https://docs.microsoft.com/learn/modules/m365-teams-collab-manage-teams/) dans Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="c9195-126">See how you can manage team roles, access, and messaging policies by completing the [Manage Microsoft Teams](https://docs.microsoft.com/learn/modules/m365-teams-collab-manage-teams/) module on Microsoft Learn.</span></span>

<span data-ttu-id="c9195-127">Lorsque vous pensez à déployer des équipes et des canaux, vous devez décider qui doit pouvoir les créer, si des invités extérieurs à votre organisation peuvent y accéder, et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="c9195-127">As you think about rolling out teams and channels, you need to decide who should be able to create them, whether guests from outside your organization can access them, and so on.</span></span> <span data-ttu-id="c9195-128">L’article [Conversation, équipes, canaux et applications dans Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) propose de nombreuses informations sur la planification des conversations, des équipes et des canaux. Toutefois, voici quelques éléments clés de cet article à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="c9195-128">The article [Chat, teams, channels, & apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) has lots of information about planning for chat, teams, and channels, however, here are some key things from that article you should think about.</span></span> <span data-ttu-id="c9195-129">Cliquez sur une décision si vous souhaitez en savoir plus à son sujet.</span><span class="sxs-lookup"><span data-stu-id="c9195-129">Click on a decision if you want more information about it.</span></span>

| <span data-ttu-id="c9195-130">Decision</span><span class="sxs-lookup"><span data-stu-id="c9195-130">Decision</span></span> | <span data-ttu-id="c9195-131">Description</span><span class="sxs-lookup"><span data-stu-id="c9195-131">Description</span></span> |
|--|--|
| [<span data-ttu-id="c9195-132">Qui doit être administrateur Teams ?</span><span class="sxs-lookup"><span data-stu-id="c9195-132">Who should be Teams administrators?</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | <span data-ttu-id="c9195-133">Les rôles d'administrateur vous permettent d’accorder des autorisations spécifiques aux personnes qui doivent, selon vous, administrer Teams.</span><span class="sxs-lookup"><span data-stu-id="c9195-133">Admin roles can be used to grant specific permissions to people who you want to administer Teams.</span></span> <span data-ttu-id="c9195-134">Les petites entreprises n’ont pas besoin de ces rôles supplémentaires, car la même personne peut être responsable de tous les aspects de Teams.</span><span class="sxs-lookup"><span data-stu-id="c9195-134">Small businesses may not need these extra roles because the same person may be responsible for all aspects of Teams.</span></span> <span data-ttu-id="c9195-135">Vous pouvez toujours ajouter ou supprimer des administrateurs ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="c9195-135">You can always add or remove administrators later on.</span></span><br><br>[<span data-ttu-id="c9195-136">Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams</span><span class="sxs-lookup"><span data-stu-id="c9195-136">Use Microsoft Teams administrator roles to manage Teams</span></span>](using-admin-roles.md) |
| [<span data-ttu-id="c9195-137">Qui doit être propriétaire et membre d’une équipe ?</span><span class="sxs-lookup"><span data-stu-id="c9195-137">Who should be Team owners and members?</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | <span data-ttu-id="c9195-138">Les propriétaires d’équipe contrôlent qui peut accéder à une équipe et à ses canaux.</span><span class="sxs-lookup"><span data-stu-id="c9195-138">Team owners control who can access a team and its channels.</span></span> <span data-ttu-id="c9195-139">Ils peuvent décider si une équipe ou un canal est public (pour l’organisation) ou privé, puis définir des stratégies telles que la modération d’un canal.</span><span class="sxs-lookup"><span data-stu-id="c9195-139">They can decide whether a team or channel is public (to the organization) or private and can set up policies like whether a channel should be moderated.</span></span> <span data-ttu-id="c9195-140">Les membres peuvent accéder à l’équipe et à ses canaux (sauf si un canal est donné comme privé et qu’ils ne sont pas membres de ce canal) et peuvent être désignés comme modérateurs.</span><span class="sxs-lookup"><span data-stu-id="c9195-140">Members can access the team and its channels (unless a channel is set to private and they're not a member of that channel) and can be designated as moderators.</span></span><br><br>[<span data-ttu-id="c9195-141">Affecter des propriétaires d’équipe et des membres dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9195-141">Assign team owners and members in Microsoft Teams</span></span>](assign-roles-permissions.md) |
| [<span data-ttu-id="c9195-142">Dois-je activer l’accès invité ?</span><span class="sxs-lookup"><span data-stu-id="c9195-142">Should guest access be enabled?</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |<span data-ttu-id="c9195-143">L’accès invité permet aux contacts de votre organisation d’inviter des contacts externes à votre organisation à accéder à vos équipes et canaux.</span><span class="sxs-lookup"><span data-stu-id="c9195-143">Guest access lets people in your organization invite people outside your organization access your teams and channels.</span></span> <span data-ttu-id="c9195-144">L’accès invité sert souvent à collaborer avec des contacts extérieurs à votre organisation qui n’ont pas de relation officielle avec la vôtre.</span><span class="sxs-lookup"><span data-stu-id="c9195-144">Guest access is often used to collaborate with people outside your organization who don't have a formal relationship with yours.</span></span> <span data-ttu-id="c9195-145">Par exemple, vous pouvez inviter un planificateur de projet à travailler temporairement sur un projet.</span><span class="sxs-lookup"><span data-stu-id="c9195-145">For example, you might invite a project planner to work on a project temporarily.</span></span><br><span data-ttu-id="c9195-146">L’accès invité est différent de l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="c9195-146">Guest access is different than external access.</span></span> <span data-ttu-id="c9195-147">L'accès invité permet d’inviter des personnes spécifiques à interagir avec les contacts de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c9195-147">Guest access invites specific individuals access to interact with people in your organization.</span></span>  <br><span data-ttu-id="c9195-148">L’accès invité est **désactivé** par défaut.</span><span class="sxs-lookup"><span data-stu-id="c9195-148">Guest access is turned **Off** by default.</span></span> <br><br>[<span data-ttu-id="c9195-149">Activer ou désactiver l'accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9195-149">Turn on or turn off guest access to Microsoft Teams</span></span>](set-up-guests.md)  |

<span data-ttu-id="c9195-150">Vous n’avez rien d’autre à faire pour que vos utilisateurs commencent à utiliser la conversation, les équipes et les canaux.</span><span class="sxs-lookup"><span data-stu-id="c9195-150">You don't need to do anything else for your users to start using chat, teams, and channels.</span></span> <span data-ttu-id="c9195-151">Toutefois, de nombreuses options vous permettent de contrôler l’utilisation de Teams.</span><span class="sxs-lookup"><span data-stu-id="c9195-151">However, there are lots of options for controlling how Teams is used.</span></span> <span data-ttu-id="c9195-152">Vous pouvez apporter des modifications maintenant ou attendre de voir comment les personnes utilisent Teams.</span><span class="sxs-lookup"><span data-stu-id="c9195-152">You can changes now, or wait until you can see how people are using Teams.</span></span> <span data-ttu-id="c9195-153">Si vous souhaitez en savoir plus veuillez, consulter les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="c9195-153">For more information, check out the following articles:</span></span>

- [<span data-ttu-id="c9195-154">Gérer les stratégies de messagerie dans Teams</span><span class="sxs-lookup"><span data-stu-id="c9195-154">Manage messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
- [<span data-ttu-id="c9195-155">Paramètres de Teams</span><span class="sxs-lookup"><span data-stu-id="c9195-155">Teams settings</span></span>](enable-features-office-365#teams-settings)

### <a name="meetings-and-conferencing"></a><span data-ttu-id="c9195-156">Réunions et conférences</span><span class="sxs-lookup"><span data-stu-id="c9195-156">Meetings and conferencing</span></span>

<span data-ttu-id="c9195-157">Les réunions et les conférences permettent aux contacts de votre organisation de se réunir, puis de rencontrer les personnes extérieures à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c9195-157">Meetings and conferencing lets people in your organization meet with each other and those outside your organization.</span></span> <span data-ttu-id="c9195-158">Toute personne possédant un client Teams ou Skype Entreprise peut participer aux **réunions** auxquelles elle a été invitée.</span><span class="sxs-lookup"><span data-stu-id="c9195-158">Anyone with a Teams or Skype for Business client can join **meetings** to which they've been invited.</span></span> <span data-ttu-id="c9195-159">L’utilisation du microphone, de la caméra et de l’écran de leur appareil permet aux participants de rejoindre la conversation sans avoir besoin d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="c9195-159">Using the microphone, camera, and screen of their device lets participants join in the conversation without the need for a phone.</span></span> <span data-ttu-id="c9195-160">Les participants peuvent converser, passer des appels vocaux et partager des vidéos et applications avec d’autres participants à l’aide d’un PC ou d’un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="c9195-160">Participants can chat, make voice calls, and share video and apps with other participants using a PC or mobile device.</span></span>

<span data-ttu-id="c9195-161">Le **système d’audioconférence** permet aux participants de rejoindre les réunions par téléphone normal en appelant un numéro de téléphone de conférence, puis en entrant un ID de réunion.</span><span class="sxs-lookup"><span data-stu-id="c9195-161">**Audio conferencing** lets participants join to meetings via a regular phone by calling a conference phone number and entering a meeting ID.</span></span> <span data-ttu-id="c9195-162">L’audioconférence est utile lorsqu’un participant n’a pas une bonne connexion Internet, que la réunion est à voix seule ou qu’une autre circonstance ne lui permet pas de rejoindre la réunion via le client Teams.</span><span class="sxs-lookup"><span data-stu-id="c9195-162">Audio conferencing is useful when a participant doesn't have a good Internet connection, the meeting is voice-only, or some other circumstance doesn't allow them to join via the Teams client.</span></span>

> [!TIP]
> <span data-ttu-id="c9195-163">Familiarisez-vous avec les réunions et événements en exécutant le module [Gérer les réunions, les conférences et les événements avec Microsoft Teams](https://docs.microsoft.com/learn/modules/m365-teams-collab-manage-meetings) sur Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="c9195-163">Get more familiar with meetings and events by completing the [Manage meetings, conferences, and events with Microsoft Teams](https://docs.microsoft.com/learn/modules/m365-teams-collab-manage-meetings) module on Microsoft Learn.</span></span>

<span data-ttu-id="c9195-164">Les réunions sont activées par défaut dans Teams. Toutefois, vous pouvez contrôler l’expérience des organisateurs et des participants en matière de réunions.</span><span class="sxs-lookup"><span data-stu-id="c9195-164">Meetings are enabled by default in Teams, however, you can control the meeting experience for organizers and participants.</span></span> <span data-ttu-id="c9195-165">Vous pouvez également définir des stratégies sur ce que les personnes peuvent et ne peuvent pas faire avant et pendant les réunions.</span><span class="sxs-lookup"><span data-stu-id="c9195-165">You can also set policies for what people are, and aren't, allowed to do before and during meetings.</span></span> <span data-ttu-id="c9195-166">Si vous souhaitez en savoir plus veuillez, consulter les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="c9195-166">For more information, check out the following articles:</span></span>

- [<span data-ttu-id="c9195-167">Démarrage rapide pour les administrateurs : réunions et événements en direct dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9195-167">Admin quick start - Meetings and live events in Microsoft Teams</span></span>](quick-start-meetings-live-events.md)
- [<span data-ttu-id="c9195-168">Configurer l’audioconférence pour les petites et moyennes entreprises</span><span class="sxs-lookup"><span data-stu-id="c9195-168">Set up Audio Conferencing for small and medium businesses</span></span>](audio-conferencing-smb.md)

### <a name="business-voice"></a><span data-ttu-id="c9195-169">Business Voice</span><span class="sxs-lookup"><span data-stu-id="c9195-169">Business Voice</span></span>

<span data-ttu-id="c9195-170">[Microsoft 365 Business Voice](business-voice/whats-business-voice.md) est une solution idéale pour les entreprises de moins de 300 utilisateurs. Elle offre toutes les fonctionnalités d’un système de téléphonie de bureau.</span><span class="sxs-lookup"><span data-stu-id="c9195-170">[Microsoft 365 Business Voice](business-voice/whats-business-voice.md) is a great solution for businesses with fewer than 300 users that gives you all the features of an office phone system.</span></span> <span data-ttu-id="c9195-171">Business Voice inclut la messagerie vocale, l’identification de l'appelant, des menus de système téléphonique, des numéros gratuits, et bien plus encore, sans devoir gérer un système téléphonique local complexe et coûteux.</span><span class="sxs-lookup"><span data-stu-id="c9195-171">Business Voice includes voicemail, caller ID, phone system menus, toll-free numbers, and more, without the need to manage a complex and costly on-premises phone system.</span></span>

<span data-ttu-id="c9195-172">Basé sur le Système téléphonique Microsoft 365, Business Voice simplifie l’ajout de voix à votre organisation en regroupant les fonctionnalités et les modules supplémentaires du système téléphonique, puis en fournissant un assistant facile à suivre pour vous aider à configurer votre système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="c9195-172">Based on Microsoft 365 Phone System, Business Voice simplifies adding voice to your organization by bundling Phone System features and add-ons, and providing an easy-to-follow wizard to help you set up your phone system.</span></span> <span data-ttu-id="c9195-173">Si votre organisation se trouve dans un pays ou une région [qui prend en charge Business Voice](business-voice/country-region-availability.md), vous pouvez transférer vos numéros de téléphone vers Microsoft 365 et nous laisser gérer votre système téléphonique à votre place.</span><span class="sxs-lookup"><span data-stu-id="c9195-173">If your organization is located in a [country or region that supports Business Voice](business-voice/country-region-availability.md), you can transfer your phone numbers to Microsoft 365 and let us manage your phone system for you.</span></span>

<span data-ttu-id="c9195-174">Avec Microsoft 365 comme système téléphonique, vous pouvez transformer n’importe quel appareil en téléphone en y installant le client Teams.</span><span class="sxs-lookup"><span data-stu-id="c9195-174">With Microsoft 365 as your phone system, you can turn any device into a phone by installing the Teams client on it.</span></span> <span data-ttu-id="c9195-175">Sinon, si vous préférez un téléphone classique de bureau ou de conférence, vous pouvez le choisir parmi un grand nombre d’appareils certifiés Teams.</span><span class="sxs-lookup"><span data-stu-id="c9195-175">Or, if you'd rather have a traditional desk phone or conference phone, there are many Teams-certified devices to choose from.</span></span> <span data-ttu-id="c9195-176">Dans les deux cas, les appels parviennent toujours à l’endroit où vous vous trouvez, et votre numéro de téléphone de bureau s’affiche toujours lorsque vous passez des appels.</span><span class="sxs-lookup"><span data-stu-id="c9195-176">Either way, calls are always routed to where you are, and calls you make always have your office phone number.</span></span>

<span data-ttu-id="c9195-177">Si vous souhaitez essayer Business Voice, veuillez consulter la rubrique [Que dois-je me procurer pour utiliser Microsoft 365 Business Voice ?](business-voice/what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="c9195-177">If you're interested in trying out Business Voice, check out [What do I need to buy to use Microsoft 365 Business Voice?](business-voice/what-to-buy.md).</span></span>

## <a name="deploy-clients"></a><span data-ttu-id="c9195-178">Déployer les clients</span><span class="sxs-lookup"><span data-stu-id="c9195-178">Deploy clients</span></span>

<span data-ttu-id="c9195-179">Lorsque vous êtes prêt à aider vos utilisateurs à utiliser Teams, ils peuvent installer le client Teams sur leurs PC Windows, Mac ou Linux, ou sur leurs appareils Android ou iOS.</span><span class="sxs-lookup"><span data-stu-id="c9195-179">When you're ready for your users to start using Teams, they can install the Teams client on their Windows, Mac, or Linux PC, or on their Android or iOS device.</span></span> <span data-ttu-id="c9195-180">Les utilisateurs peuvent télécharger le client Teams directement depuis <https://teams.microsoft.com/downloads>.</span><span class="sxs-lookup"><span data-stu-id="c9195-180">Users can download the Teams client directly from <https://teams.microsoft.com/downloads>.</span></span>

<span data-ttu-id="c9195-181">Vérifiez que toutes les personnes qui utiliseront Teams ont une licence Teams.</span><span class="sxs-lookup"><span data-stu-id="c9195-181">Make sure everyone who will be using Teams has a Teams license.</span></span> <span data-ttu-id="c9195-182">Si vous souhaitez en savoir plus sur l’attribution d’une licence Teams, veuillez consulter la rubrique [Gérer l’accès des utilisateurs à Teams](user-access.md#using-the-microsoft-365-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c9195-182">For more information about assigning a Teams license, see [Manage user access to Teams](user-access.md#using-the-microsoft-365-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="c9195-183">Obtenez des recommandations sur la façon de planifier le déploiement de votre client Teams en complétant le module [Déployer les clients Microsoft Teams](https://docs.microsoft.com/learn/modules/m365-teams-collab-deploy-clients/) sur Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="c9195-183">Get recommendations on how to plan your Teams client deployment by completing the [Deploy Microsoft Teams clients](https://docs.microsoft.com/learn/modules/m365-teams-collab-deploy-clients/) module on Microsoft Learn.</span></span>

<span data-ttu-id="c9195-184">Si votre organisation utilise Microsoft Endpoint Configuration Manager, une stratégie de groupe ou un mécanisme de distribution tiers, pour déployer des logiciels sur les ordinateurs de vos utilisateurs, veuillez consulter la rubrique [Installer Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="c9195-184">If your organization uses Microsoft Endpoint Configuration Manager, Group Policy, or a third-party distribution mechanism, to deploy software to your user's computers, see [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md).</span></span>

<span data-ttu-id="c9195-185">Si vous souhaitez en savoir plus sur le déploiement des clients Teams, veuillez consulter la rubrique [Obtenir les clients pour Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="c9195-185">If you want detailed information about deploying Teams clients, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="training"></a><span data-ttu-id="c9195-186">Formation</span><span class="sxs-lookup"><span data-stu-id="c9195-186">Training</span></span>

<span data-ttu-id="c9195-187">Si vous souhaitez en savoir plus sur la formation de vos utilisateurs et administrateurs à l’utilisation de Teams, veuillez consulter la rubrique [Formation Microsoft Teams](training-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="c9195-187">For information on how to train your users to use Teams, see [Microsoft Teams training](training-microsoft-teams-landing-page.md).</span></span>