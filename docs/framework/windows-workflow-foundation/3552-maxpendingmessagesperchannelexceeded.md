---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: bd3e7539922e6c430c4ffe5bd96ef1ac7dbd098f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261168"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="79bbc-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="79bbc-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="79bbc-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="79bbc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79bbc-104">ID</span><span class="sxs-lookup"><span data-stu-id="79bbc-104">ID</span></span>|<span data-ttu-id="79bbc-105">3552</span><span class="sxs-lookup"><span data-stu-id="79bbc-105">3552</span></span>|  
|<span data-ttu-id="79bbc-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79bbc-106">Keywords</span></span>|<span data-ttu-id="79bbc-107">Cuota, WFServices</span><span class="sxs-lookup"><span data-stu-id="79bbc-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="79bbc-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="79bbc-108">Level</span></span>|<span data-ttu-id="79bbc-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="79bbc-109">Warning</span></span>|  
|<span data-ttu-id="79bbc-110">Canal</span><span class="sxs-lookup"><span data-stu-id="79bbc-110">Channel</span></span>|<span data-ttu-id="79bbc-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="79bbc-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="79bbc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="79bbc-112">Description</span></span>  

 <span data-ttu-id="79bbc-113">Indica que se alcanzó la limitación de 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="79bbc-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="79bbc-114">Message</span><span class="sxs-lookup"><span data-stu-id="79bbc-114">Message</span></span>  

 <span data-ttu-id="79bbc-115">Se alcanzó la limitación de 'MaxPendingMessagesPerChannel' de '%1'.</span><span class="sxs-lookup"><span data-stu-id="79bbc-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="79bbc-116">Para aumentar este límite, ajuste la propiedad MaxPendingMessagesPerChannel en BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="79bbc-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="79bbc-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="79bbc-117">Details</span></span>  
  
|<span data-ttu-id="79bbc-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="79bbc-118">Data Item Name</span></span>|<span data-ttu-id="79bbc-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="79bbc-119">Data Item Type</span></span>|<span data-ttu-id="79bbc-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="79bbc-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="79bbc-121">Límite</span><span class="sxs-lookup"><span data-stu-id="79bbc-121">Limit</span></span>|<span data-ttu-id="79bbc-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="79bbc-122">xs:string</span></span>|<span data-ttu-id="79bbc-123">Se alcanzó la limitación de MaxPendingMessagesPerChannel.</span><span class="sxs-lookup"><span data-stu-id="79bbc-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="79bbc-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="79bbc-124">AppDomain</span></span>|<span data-ttu-id="79bbc-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="79bbc-125">xs:string</span></span>|<span data-ttu-id="79bbc-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="79bbc-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
