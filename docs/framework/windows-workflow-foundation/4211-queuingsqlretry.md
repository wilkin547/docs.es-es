---
description: 'Más información acerca de: 4211-QueuingSqlRetry'
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: 674914ee105bb0a48f8c32efbd573c685d22d9f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742711"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="c3fd8-103">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="c3fd8-103">4211 - QueuingSqlRetry</span></span>

## <a name="properties"></a><span data-ttu-id="c3fd8-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c3fd8-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3fd8-105">Id.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-105">ID</span></span>|<span data-ttu-id="c3fd8-106">4211</span><span class="sxs-lookup"><span data-stu-id="c3fd8-106">4211</span></span>|  
|<span data-ttu-id="c3fd8-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c3fd8-107">Keywords</span></span>|<span data-ttu-id="c3fd8-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c3fd8-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="c3fd8-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="c3fd8-109">Level</span></span>|<span data-ttu-id="c3fd8-110">Advertencia</span><span class="sxs-lookup"><span data-stu-id="c3fd8-110">Warning</span></span>|  
|<span data-ttu-id="c3fd8-111">Canal</span><span class="sxs-lookup"><span data-stu-id="c3fd8-111">Channel</span></span>|<span data-ttu-id="c3fd8-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c3fd8-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c3fd8-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3fd8-113">Description</span></span>  

 <span data-ttu-id="c3fd8-114">Indica poner en cola el intento de SQL.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-114">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c3fd8-115">Message</span><span class="sxs-lookup"><span data-stu-id="c3fd8-115">Message</span></span>  

 <span data-ttu-id="c3fd8-116">Poniendo en cola el reintento SQL con %1 milisegundos de retraso.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-116">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c3fd8-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="c3fd8-117">Details</span></span>  
  
|<span data-ttu-id="c3fd8-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c3fd8-118">Data Item Name</span></span>|<span data-ttu-id="c3fd8-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c3fd8-119">Data Item Type</span></span>|<span data-ttu-id="c3fd8-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3fd8-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c3fd8-121">Delay</span><span class="sxs-lookup"><span data-stu-id="c3fd8-121">Delay</span></span>|<span data-ttu-id="c3fd8-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3fd8-122">xs:string</span></span>|<span data-ttu-id="c3fd8-123">El retraso entre los reintentos.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-123">The delay between retries.</span></span>|  
|<span data-ttu-id="c3fd8-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c3fd8-124">AppDomain</span></span>|<span data-ttu-id="c3fd8-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3fd8-125">xs:string</span></span>|<span data-ttu-id="c3fd8-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
