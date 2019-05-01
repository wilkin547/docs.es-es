---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945943"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="3b6ba-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="3b6ba-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="3b6ba-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3b6ba-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b6ba-104">ID</span><span class="sxs-lookup"><span data-stu-id="3b6ba-104">ID</span></span>|<span data-ttu-id="3b6ba-105">3552</span><span class="sxs-lookup"><span data-stu-id="3b6ba-105">3552</span></span>|  
|<span data-ttu-id="3b6ba-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3b6ba-106">Keywords</span></span>|<span data-ttu-id="3b6ba-107">Cuota, WFServices</span><span class="sxs-lookup"><span data-stu-id="3b6ba-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="3b6ba-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="3b6ba-108">Level</span></span>|<span data-ttu-id="3b6ba-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="3b6ba-109">Warning</span></span>|  
|<span data-ttu-id="3b6ba-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3b6ba-110">Channel</span></span>|<span data-ttu-id="3b6ba-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="3b6ba-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3b6ba-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b6ba-112">Description</span></span>  
 <span data-ttu-id="3b6ba-113">Indica que se alcanzó la limitación de 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="3b6ba-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3b6ba-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="3b6ba-114">Message</span></span>  
 <span data-ttu-id="3b6ba-115">Se alcanzó el límite de ' maxpendingmessagesperchannel ' de '%1'.</span><span class="sxs-lookup"><span data-stu-id="3b6ba-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="3b6ba-116">Para aumentar este límite, ajuste la propiedad MaxPendingMessagesPerChannel en BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="3b6ba-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3b6ba-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="3b6ba-117">Details</span></span>  
  
|<span data-ttu-id="3b6ba-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3b6ba-118">Data Item Name</span></span>|<span data-ttu-id="3b6ba-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3b6ba-119">Data Item Type</span></span>|<span data-ttu-id="3b6ba-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b6ba-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3b6ba-121">Limit</span><span class="sxs-lookup"><span data-stu-id="3b6ba-121">Limit</span></span>|<span data-ttu-id="3b6ba-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b6ba-122">xs:string</span></span>|<span data-ttu-id="3b6ba-123">Se alcanzó la limitación de MaxPendingMessagesPerChannel.</span><span class="sxs-lookup"><span data-stu-id="3b6ba-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="3b6ba-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3b6ba-124">AppDomain</span></span>|<span data-ttu-id="3b6ba-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b6ba-125">xs:string</span></span>|<span data-ttu-id="3b6ba-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3b6ba-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
