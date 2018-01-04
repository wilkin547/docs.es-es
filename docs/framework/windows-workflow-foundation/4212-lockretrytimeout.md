---
title: 4212 - LockRetryTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f47b383547da5145c5307670fee2eda10fcab402
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="5791d-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="5791d-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="5791d-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5791d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5791d-104">Id.</span><span class="sxs-lookup"><span data-stu-id="5791d-104">ID</span></span>|<span data-ttu-id="5791d-105">4212</span><span class="sxs-lookup"><span data-stu-id="5791d-105">4212</span></span>|  
|<span data-ttu-id="5791d-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5791d-106">Keywords</span></span>|<span data-ttu-id="5791d-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="5791d-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="5791d-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="5791d-108">Level</span></span>|<span data-ttu-id="5791d-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="5791d-109">Warning</span></span>|  
|<span data-ttu-id="5791d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="5791d-110">Channel</span></span>|<span data-ttu-id="5791d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5791d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5791d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5791d-112">Description</span></span>  
 <span data-ttu-id="5791d-113">El proveedor de SQL detectó que se agotó el tiempo de espera al intentar adquirir el bloqueo de instancia.</span><span class="sxs-lookup"><span data-stu-id="5791d-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5791d-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="5791d-114">Message</span></span>  
 <span data-ttu-id="5791d-115">Intenta adquirir el bloqueo de la instancia de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="5791d-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="5791d-116">La operación no se completó dentro del tiempo de espera asignado de %1.</span><span class="sxs-lookup"><span data-stu-id="5791d-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="5791d-117">El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.</span><span class="sxs-lookup"><span data-stu-id="5791d-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5791d-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="5791d-118">Details</span></span>  
  
|<span data-ttu-id="5791d-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5791d-119">Data Item Name</span></span>|<span data-ttu-id="5791d-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5791d-120">Data Item Type</span></span>|<span data-ttu-id="5791d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="5791d-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5791d-122">Delay</span><span class="sxs-lookup"><span data-stu-id="5791d-122">Delay</span></span>|<span data-ttu-id="5791d-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="5791d-123">xs:string</span></span>|<span data-ttu-id="5791d-124">Retraso entre los intentos.</span><span class="sxs-lookup"><span data-stu-id="5791d-124">The delay between retries.</span></span>|  
|<span data-ttu-id="5791d-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5791d-125">AppDomain</span></span>|<span data-ttu-id="5791d-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="5791d-126">xs:string</span></span>|<span data-ttu-id="5791d-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5791d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
