---
title: 4211 - QueuingSqlRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 349a91f5b4708d829aee8d7f055871ac7dcc8914
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="d95ff-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="d95ff-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="d95ff-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d95ff-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d95ff-104">Id.</span><span class="sxs-lookup"><span data-stu-id="d95ff-104">ID</span></span>|<span data-ttu-id="d95ff-105">4211</span><span class="sxs-lookup"><span data-stu-id="d95ff-105">4211</span></span>|  
|<span data-ttu-id="d95ff-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d95ff-106">Keywords</span></span>|<span data-ttu-id="d95ff-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="d95ff-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="d95ff-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d95ff-108">Level</span></span>|<span data-ttu-id="d95ff-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="d95ff-109">Warning</span></span>|  
|<span data-ttu-id="d95ff-110">Canal</span><span class="sxs-lookup"><span data-stu-id="d95ff-110">Channel</span></span>|<span data-ttu-id="d95ff-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d95ff-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d95ff-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d95ff-112">Description</span></span>  
 <span data-ttu-id="d95ff-113">Indica poner en cola el intento de SQL.</span><span class="sxs-lookup"><span data-stu-id="d95ff-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d95ff-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="d95ff-114">Message</span></span>  
 <span data-ttu-id="d95ff-115">Poniendo en cola el reintento SQL con %1 milisegundos de retraso.</span><span class="sxs-lookup"><span data-stu-id="d95ff-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d95ff-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="d95ff-116">Details</span></span>  
  
|<span data-ttu-id="d95ff-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d95ff-117">Data Item Name</span></span>|<span data-ttu-id="d95ff-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d95ff-118">Data Item Type</span></span>|<span data-ttu-id="d95ff-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d95ff-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d95ff-120">Delay</span><span class="sxs-lookup"><span data-stu-id="d95ff-120">Delay</span></span>|<span data-ttu-id="d95ff-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d95ff-121">xs:string</span></span>|<span data-ttu-id="d95ff-122">Retraso entre los intentos.</span><span class="sxs-lookup"><span data-stu-id="d95ff-122">The delay between retries.</span></span>|  
|<span data-ttu-id="d95ff-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d95ff-123">AppDomain</span></span>|<span data-ttu-id="d95ff-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d95ff-124">xs:string</span></span>|<span data-ttu-id="d95ff-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d95ff-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
