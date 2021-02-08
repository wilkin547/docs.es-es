---
description: 'Más información acerca de: 1016-CompleteCompletionWorkItem'
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 849e192d63b5db19e5beea31befcdc38d4340c6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792913"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="35e70-103">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="35e70-103">1016 - CompleteCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="35e70-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="35e70-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35e70-105">Id.</span><span class="sxs-lookup"><span data-stu-id="35e70-105">ID</span></span>|<span data-ttu-id="35e70-106">1016</span><span class="sxs-lookup"><span data-stu-id="35e70-106">1016</span></span>|  
|<span data-ttu-id="35e70-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="35e70-107">Keywords</span></span>|<span data-ttu-id="35e70-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="35e70-108">WFRuntime</span></span>|  
|<span data-ttu-id="35e70-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="35e70-109">Level</span></span>|<span data-ttu-id="35e70-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="35e70-110">Verbose</span></span>|  
|<span data-ttu-id="35e70-111">Canal</span><span class="sxs-lookup"><span data-stu-id="35e70-111">Channel</span></span>|<span data-ttu-id="35e70-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="35e70-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="35e70-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="35e70-113">Description</span></span>  

 <span data-ttu-id="35e70-114">Indica que se ha completado un CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="35e70-114">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="35e70-115">Message</span><span class="sxs-lookup"><span data-stu-id="35e70-115">Message</span></span>  

 <span data-ttu-id="35e70-116">Un CompletionWorkItem se ha completado para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="35e70-116">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="35e70-117">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="35e70-117">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="35e70-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="35e70-118">Details</span></span>  
  
|<span data-ttu-id="35e70-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="35e70-119">Data Item Name</span></span>|<span data-ttu-id="35e70-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="35e70-120">Data Item Type</span></span>|<span data-ttu-id="35e70-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="35e70-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="35e70-122">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="35e70-122">ParentActivity</span></span>|<span data-ttu-id="35e70-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="35e70-123">xs:string</span></span>|<span data-ttu-id="35e70-124">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="35e70-124">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="35e70-125">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="35e70-125">ParentDisplayName</span></span>|<span data-ttu-id="35e70-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="35e70-126">xs:string</span></span>|<span data-ttu-id="35e70-127">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="35e70-127">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="35e70-128">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="35e70-128">ParentInstanceId</span></span>|<span data-ttu-id="35e70-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="35e70-129">xs:string</span></span>|<span data-ttu-id="35e70-130">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="35e70-130">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="35e70-131">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="35e70-131">CompletedActivity</span></span>|<span data-ttu-id="35e70-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="35e70-132">xs:string</span></span>|<span data-ttu-id="35e70-133">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="35e70-133">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="35e70-134">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="35e70-134">CompletedActivityDisplayName</span></span>|<span data-ttu-id="35e70-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="35e70-135">xs:string</span></span>|<span data-ttu-id="35e70-136">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="35e70-136">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="35e70-137">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="35e70-137">CompletedActivityInstanceId</span></span>|<span data-ttu-id="35e70-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="35e70-138">xs:string</span></span>|<span data-ttu-id="35e70-139">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="35e70-139">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="35e70-140">AppDomain</span><span class="sxs-lookup"><span data-stu-id="35e70-140">AppDomain</span></span>|<span data-ttu-id="35e70-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="35e70-141">xs:string</span></span>|<span data-ttu-id="35e70-142">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="35e70-142">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
