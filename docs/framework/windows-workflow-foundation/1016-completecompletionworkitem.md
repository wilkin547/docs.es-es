---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: a192ffe19777ca3e2e9784f6506a0c2929ced000
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275536"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="133da-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="133da-102">1016 - CompleteCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="133da-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="133da-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="133da-104">ID</span><span class="sxs-lookup"><span data-stu-id="133da-104">ID</span></span>|<span data-ttu-id="133da-105">1016</span><span class="sxs-lookup"><span data-stu-id="133da-105">1016</span></span>|  
|<span data-ttu-id="133da-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="133da-106">Keywords</span></span>|<span data-ttu-id="133da-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="133da-107">WFRuntime</span></span>|  
|<span data-ttu-id="133da-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="133da-108">Level</span></span>|<span data-ttu-id="133da-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="133da-109">Verbose</span></span>|  
|<span data-ttu-id="133da-110">Canal</span><span class="sxs-lookup"><span data-stu-id="133da-110">Channel</span></span>|<span data-ttu-id="133da-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="133da-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="133da-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="133da-112">Description</span></span>  

 <span data-ttu-id="133da-113">Indica que se ha completado un CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="133da-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="133da-114">Message</span><span class="sxs-lookup"><span data-stu-id="133da-114">Message</span></span>  

 <span data-ttu-id="133da-115">Un CompletionWorkItem se ha completado para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="133da-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="133da-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="133da-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="133da-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="133da-117">Details</span></span>  
  
|<span data-ttu-id="133da-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="133da-118">Data Item Name</span></span>|<span data-ttu-id="133da-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="133da-119">Data Item Type</span></span>|<span data-ttu-id="133da-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="133da-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="133da-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="133da-121">ParentActivity</span></span>|<span data-ttu-id="133da-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="133da-122">xs:string</span></span>|<span data-ttu-id="133da-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="133da-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="133da-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="133da-124">ParentDisplayName</span></span>|<span data-ttu-id="133da-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="133da-125">xs:string</span></span>|<span data-ttu-id="133da-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="133da-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="133da-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="133da-127">ParentInstanceId</span></span>|<span data-ttu-id="133da-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="133da-128">xs:string</span></span>|<span data-ttu-id="133da-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="133da-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="133da-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="133da-130">CompletedActivity</span></span>|<span data-ttu-id="133da-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="133da-131">xs:string</span></span>|<span data-ttu-id="133da-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="133da-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="133da-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="133da-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="133da-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="133da-134">xs:string</span></span>|<span data-ttu-id="133da-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="133da-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="133da-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="133da-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="133da-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="133da-137">xs:string</span></span>|<span data-ttu-id="133da-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="133da-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="133da-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="133da-139">AppDomain</span></span>|<span data-ttu-id="133da-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="133da-140">xs:string</span></span>|<span data-ttu-id="133da-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="133da-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
