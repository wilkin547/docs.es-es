---
title: 1014 - ScheduleCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a80406ce56000703555f7834714222e03d2b65f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="951ea-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="951ea-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="951ea-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="951ea-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="951ea-104">Id.</span><span class="sxs-lookup"><span data-stu-id="951ea-104">ID</span></span>|<span data-ttu-id="951ea-105">1014</span><span class="sxs-lookup"><span data-stu-id="951ea-105">1014</span></span>|  
|<span data-ttu-id="951ea-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="951ea-106">Keywords</span></span>|<span data-ttu-id="951ea-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="951ea-107">WFRuntime</span></span>|  
|<span data-ttu-id="951ea-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="951ea-108">Level</span></span>|<span data-ttu-id="951ea-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="951ea-109">Verbose</span></span>|  
|<span data-ttu-id="951ea-110">Canal</span><span class="sxs-lookup"><span data-stu-id="951ea-110">Channel</span></span>|<span data-ttu-id="951ea-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="951ea-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="951ea-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="951ea-112">Description</span></span>  
 <span data-ttu-id="951ea-113">Indica que se ha programado un CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="951ea-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="951ea-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="951ea-114">Message</span></span>  
 <span data-ttu-id="951ea-115">Se ha programado un CompletionWorkItem para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="951ea-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="951ea-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="951ea-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="951ea-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="951ea-117">Details</span></span>  
  
|<span data-ttu-id="951ea-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="951ea-118">Data Item Name</span></span>|<span data-ttu-id="951ea-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="951ea-119">Data Item Type</span></span>|<span data-ttu-id="951ea-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="951ea-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="951ea-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="951ea-121">ParentActivity</span></span>|<span data-ttu-id="951ea-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="951ea-122">xs:string</span></span>|<span data-ttu-id="951ea-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="951ea-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="951ea-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="951ea-124">ParentDisplayName</span></span>|<span data-ttu-id="951ea-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="951ea-125">xs:string</span></span>|<span data-ttu-id="951ea-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="951ea-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="951ea-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="951ea-127">ParentInstanceId</span></span>|<span data-ttu-id="951ea-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="951ea-128">xs:string</span></span>|<span data-ttu-id="951ea-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="951ea-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="951ea-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="951ea-130">CompletedActivity</span></span>|<span data-ttu-id="951ea-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="951ea-131">xs:string</span></span>|<span data-ttu-id="951ea-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="951ea-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="951ea-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="951ea-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="951ea-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="951ea-134">xs:string</span></span>|<span data-ttu-id="951ea-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="951ea-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="951ea-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="951ea-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="951ea-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="951ea-137">xs:string</span></span>|<span data-ttu-id="951ea-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="951ea-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="951ea-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="951ea-139">AppDomain</span></span>|<span data-ttu-id="951ea-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="951ea-140">xs:string</span></span>|<span data-ttu-id="951ea-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="951ea-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
