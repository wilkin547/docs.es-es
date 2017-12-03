---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5455472a5b9ebdba7aea7d0384ce9cd4a9a2849d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="6d53b-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="6d53b-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="6d53b-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6d53b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d53b-104">Id.</span><span class="sxs-lookup"><span data-stu-id="6d53b-104">ID</span></span>|<span data-ttu-id="6d53b-105">3552</span><span class="sxs-lookup"><span data-stu-id="6d53b-105">3552</span></span>|  
|<span data-ttu-id="6d53b-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6d53b-106">Keywords</span></span>|<span data-ttu-id="6d53b-107">Cuota, WFServices</span><span class="sxs-lookup"><span data-stu-id="6d53b-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="6d53b-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="6d53b-108">Level</span></span>|<span data-ttu-id="6d53b-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="6d53b-109">Warning</span></span>|  
|<span data-ttu-id="6d53b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="6d53b-110">Channel</span></span>|<span data-ttu-id="6d53b-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6d53b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6d53b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d53b-112">Description</span></span>  
 <span data-ttu-id="6d53b-113">Indica que se alcanzó la limitación de 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="6d53b-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6d53b-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="6d53b-114">Message</span></span>  
 <span data-ttu-id="6d53b-115">Se alcanzó el límite de ' maxpendingmessagesperchannel ' de '%1'.</span><span class="sxs-lookup"><span data-stu-id="6d53b-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="6d53b-116">Para aumentar este límite, ajuste la propiedad MaxPendingMessagesPerChannel en BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="6d53b-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6d53b-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="6d53b-117">Details</span></span>  
  
|<span data-ttu-id="6d53b-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6d53b-118">Data Item Name</span></span>|<span data-ttu-id="6d53b-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6d53b-119">Data Item Type</span></span>|<span data-ttu-id="6d53b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d53b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6d53b-121">Limit</span><span class="sxs-lookup"><span data-stu-id="6d53b-121">Limit</span></span>|<span data-ttu-id="6d53b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d53b-122">xs:string</span></span>|<span data-ttu-id="6d53b-123">Se alcanzó la limitación de MaxPendingMessagesPerChannel.</span><span class="sxs-lookup"><span data-stu-id="6d53b-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="6d53b-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6d53b-124">AppDomain</span></span>|<span data-ttu-id="6d53b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d53b-125">xs:string</span></span>|<span data-ttu-id="6d53b-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6d53b-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
