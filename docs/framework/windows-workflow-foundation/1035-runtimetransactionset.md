---
title: 1035 - RuntimeTransactionSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a64a8a4ab6212a5e83b59fd7523df9cd875e7b87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="84704-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="84704-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="84704-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="84704-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="84704-104">Id.</span><span class="sxs-lookup"><span data-stu-id="84704-104">ID</span></span>|<span data-ttu-id="84704-105">1035</span><span class="sxs-lookup"><span data-stu-id="84704-105">1035</span></span>|  
|<span data-ttu-id="84704-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84704-106">Keywords</span></span>|<span data-ttu-id="84704-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="84704-107">WFRuntime</span></span>|  
|<span data-ttu-id="84704-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="84704-108">Level</span></span>|<span data-ttu-id="84704-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="84704-109">Verbose</span></span>|  
|<span data-ttu-id="84704-110">Canal</span><span class="sxs-lookup"><span data-stu-id="84704-110">Channel</span></span>|<span data-ttu-id="84704-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="84704-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="84704-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="84704-112">Description</span></span>  
 <span data-ttu-id="84704-113">Indica que una actividad ha establecido la transacción en tiempo ejecución.</span><span class="sxs-lookup"><span data-stu-id="84704-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="84704-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="84704-114">Message</span></span>  
 <span data-ttu-id="84704-115">Se ha establecido la transacción en tiempo de ejecución por la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="84704-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="84704-116">Ejecución aislada a la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="84704-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="84704-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="84704-117">Details</span></span>  
  
|<span data-ttu-id="84704-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="84704-118">Data Item Name</span></span>|<span data-ttu-id="84704-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="84704-119">Data Item Type</span></span>|<span data-ttu-id="84704-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="84704-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="84704-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="84704-121">Activity</span></span>|<span data-ttu-id="84704-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="84704-122">xs:string</span></span>|<span data-ttu-id="84704-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="84704-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="84704-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="84704-124">DisplayName</span></span>|<span data-ttu-id="84704-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="84704-125">xs:string</span></span>|<span data-ttu-id="84704-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="84704-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="84704-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="84704-127">InstanceId</span></span>|<span data-ttu-id="84704-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="84704-128">xs:string</span></span>|<span data-ttu-id="84704-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="84704-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="84704-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="84704-130">IsolatedActivity</span></span>|<span data-ttu-id="84704-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="84704-131">xs:string</span></span>|<span data-ttu-id="84704-132">El nombre de tipo para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="84704-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="84704-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="84704-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="84704-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="84704-134">xs:string</span></span>|<span data-ttu-id="84704-135">El nombre para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="84704-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="84704-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="84704-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="84704-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="84704-137">xs:string</span></span>|<span data-ttu-id="84704-138">El identificador de la instancia de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="84704-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="84704-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="84704-139">AppDomain</span></span>|<span data-ttu-id="84704-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="84704-140">xs:string</span></span>|<span data-ttu-id="84704-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="84704-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
