---
title: 1016 - CompleteCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b01706f6e84987ea20f52c131139e243e8184c51
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="4c7d9-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="4c7d9-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="4c7d9-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4c7d9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4c7d9-104">Id.</span><span class="sxs-lookup"><span data-stu-id="4c7d9-104">ID</span></span>|<span data-ttu-id="4c7d9-105">1016</span><span class="sxs-lookup"><span data-stu-id="4c7d9-105">1016</span></span>|  
|<span data-ttu-id="4c7d9-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c7d9-106">Keywords</span></span>|<span data-ttu-id="4c7d9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4c7d9-107">WFRuntime</span></span>|  
|<span data-ttu-id="4c7d9-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="4c7d9-108">Level</span></span>|<span data-ttu-id="4c7d9-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="4c7d9-109">Verbose</span></span>|  
|<span data-ttu-id="4c7d9-110">Canal</span><span class="sxs-lookup"><span data-stu-id="4c7d9-110">Channel</span></span>|<span data-ttu-id="4c7d9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4c7d9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4c7d9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c7d9-112">Description</span></span>  
 <span data-ttu-id="4c7d9-113">Indica que se ha completado un CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="4c7d9-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4c7d9-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4c7d9-114">Message</span></span>  
 <span data-ttu-id="4c7d9-115">Un CompletionWorkItem se ha completado para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="4c7d9-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="4c7d9-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="4c7d9-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4c7d9-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="4c7d9-117">Details</span></span>  
  
|<span data-ttu-id="4c7d9-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4c7d9-118">Data Item Name</span></span>|<span data-ttu-id="4c7d9-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4c7d9-119">Data Item Type</span></span>|<span data-ttu-id="4c7d9-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c7d9-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4c7d9-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="4c7d9-121">ParentActivity</span></span>|<span data-ttu-id="4c7d9-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c7d9-122">xs:string</span></span>|<span data-ttu-id="4c7d9-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="4c7d9-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="4c7d9-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="4c7d9-124">ParentDisplayName</span></span>|<span data-ttu-id="4c7d9-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c7d9-125">xs:string</span></span>|<span data-ttu-id="4c7d9-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="4c7d9-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="4c7d9-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="4c7d9-127">ParentInstanceId</span></span>|<span data-ttu-id="4c7d9-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c7d9-128">xs:string</span></span>|<span data-ttu-id="4c7d9-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="4c7d9-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="4c7d9-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="4c7d9-130">CompletedActivity</span></span>|<span data-ttu-id="4c7d9-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c7d9-131">xs:string</span></span>|<span data-ttu-id="4c7d9-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="4c7d9-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="4c7d9-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="4c7d9-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="4c7d9-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c7d9-134">xs:string</span></span>|<span data-ttu-id="4c7d9-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="4c7d9-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="4c7d9-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="4c7d9-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="4c7d9-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c7d9-137">xs:string</span></span>|<span data-ttu-id="4c7d9-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="4c7d9-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="4c7d9-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4c7d9-139">AppDomain</span></span>|<span data-ttu-id="4c7d9-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c7d9-140">xs:string</span></span>|<span data-ttu-id="4c7d9-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4c7d9-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
