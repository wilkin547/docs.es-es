---
description: 'Más información acerca de: 3552-MaxPendingMessagesPerChannelExceeded'
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: 5fb2d27f7d68716cebf2cfaafd21851226a456e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631442"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="c8c3a-103">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="c8c3a-103">3552 - MaxPendingMessagesPerChannelExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="c8c3a-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c8c3a-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c8c3a-105">Id.</span><span class="sxs-lookup"><span data-stu-id="c8c3a-105">ID</span></span>|<span data-ttu-id="c8c3a-106">3552</span><span class="sxs-lookup"><span data-stu-id="c8c3a-106">3552</span></span>|  
|<span data-ttu-id="c8c3a-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c8c3a-107">Keywords</span></span>|<span data-ttu-id="c8c3a-108">Cuota, WFServices</span><span class="sxs-lookup"><span data-stu-id="c8c3a-108">Quota, WFServices</span></span>|  
|<span data-ttu-id="c8c3a-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="c8c3a-109">Level</span></span>|<span data-ttu-id="c8c3a-110">Advertencia</span><span class="sxs-lookup"><span data-stu-id="c8c3a-110">Warning</span></span>|  
|<span data-ttu-id="c8c3a-111">Canal</span><span class="sxs-lookup"><span data-stu-id="c8c3a-111">Channel</span></span>|<span data-ttu-id="c8c3a-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c8c3a-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c8c3a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8c3a-113">Description</span></span>  

 <span data-ttu-id="c8c3a-114">Indica que se alcanzó la limitación de 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="c8c3a-114">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c8c3a-115">Message</span><span class="sxs-lookup"><span data-stu-id="c8c3a-115">Message</span></span>  

 <span data-ttu-id="c8c3a-116">Se alcanzó la limitación de 'MaxPendingMessagesPerChannel' de '%1'.</span><span class="sxs-lookup"><span data-stu-id="c8c3a-116">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="c8c3a-117">Para aumentar este límite, ajuste la propiedad MaxPendingMessagesPerChannel en BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="c8c3a-117">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c8c3a-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="c8c3a-118">Details</span></span>  
  
|<span data-ttu-id="c8c3a-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c8c3a-119">Data Item Name</span></span>|<span data-ttu-id="c8c3a-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c8c3a-120">Data Item Type</span></span>|<span data-ttu-id="c8c3a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8c3a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c8c3a-122">Límite</span><span class="sxs-lookup"><span data-stu-id="c8c3a-122">Limit</span></span>|<span data-ttu-id="c8c3a-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c8c3a-123">xs:string</span></span>|<span data-ttu-id="c8c3a-124">Se alcanzó la limitación de MaxPendingMessagesPerChannel.</span><span class="sxs-lookup"><span data-stu-id="c8c3a-124">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="c8c3a-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c8c3a-125">AppDomain</span></span>|<span data-ttu-id="c8c3a-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="c8c3a-126">xs:string</span></span>|<span data-ttu-id="c8c3a-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c8c3a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
