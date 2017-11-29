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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c318ee6509ce8b96a1e7e78a13f4aeb7c76dde6a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="01f40-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="01f40-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="01f40-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="01f40-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01f40-104">Id.</span><span class="sxs-lookup"><span data-stu-id="01f40-104">ID</span></span>|<span data-ttu-id="01f40-105">4211</span><span class="sxs-lookup"><span data-stu-id="01f40-105">4211</span></span>|  
|<span data-ttu-id="01f40-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="01f40-106">Keywords</span></span>|<span data-ttu-id="01f40-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="01f40-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="01f40-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="01f40-108">Level</span></span>|<span data-ttu-id="01f40-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="01f40-109">Warning</span></span>|  
|<span data-ttu-id="01f40-110">Canal</span><span class="sxs-lookup"><span data-stu-id="01f40-110">Channel</span></span>|<span data-ttu-id="01f40-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="01f40-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="01f40-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="01f40-112">Description</span></span>  
 <span data-ttu-id="01f40-113">Indica poner en cola el intento de SQL.</span><span class="sxs-lookup"><span data-stu-id="01f40-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="01f40-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="01f40-114">Message</span></span>  
 <span data-ttu-id="01f40-115">Poniendo en cola el reintento SQL con %1 milisegundos de retraso.</span><span class="sxs-lookup"><span data-stu-id="01f40-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="01f40-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="01f40-116">Details</span></span>  
  
|<span data-ttu-id="01f40-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="01f40-117">Data Item Name</span></span>|<span data-ttu-id="01f40-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="01f40-118">Data Item Type</span></span>|<span data-ttu-id="01f40-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="01f40-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="01f40-120">Delay</span><span class="sxs-lookup"><span data-stu-id="01f40-120">Delay</span></span>|<span data-ttu-id="01f40-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="01f40-121">xs:string</span></span>|<span data-ttu-id="01f40-122">Retraso entre los intentos.</span><span class="sxs-lookup"><span data-stu-id="01f40-122">The delay between retries.</span></span>|  
|<span data-ttu-id="01f40-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="01f40-123">AppDomain</span></span>|<span data-ttu-id="01f40-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="01f40-124">xs:string</span></span>|<span data-ttu-id="01f40-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="01f40-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
