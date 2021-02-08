---
description: 'Más información acerca de: 1014-ScheduleCompletionWorkItem'
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 85bbd9b749c1dd34d026d90d708ea7f880665fbb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792939"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="030f7-103">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="030f7-103">1014 - ScheduleCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="030f7-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="030f7-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="030f7-105">Id.</span><span class="sxs-lookup"><span data-stu-id="030f7-105">ID</span></span>|<span data-ttu-id="030f7-106">1014</span><span class="sxs-lookup"><span data-stu-id="030f7-106">1014</span></span>|  
|<span data-ttu-id="030f7-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="030f7-107">Keywords</span></span>|<span data-ttu-id="030f7-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="030f7-108">WFRuntime</span></span>|  
|<span data-ttu-id="030f7-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="030f7-109">Level</span></span>|<span data-ttu-id="030f7-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="030f7-110">Verbose</span></span>|  
|<span data-ttu-id="030f7-111">Canal</span><span class="sxs-lookup"><span data-stu-id="030f7-111">Channel</span></span>|<span data-ttu-id="030f7-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="030f7-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="030f7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="030f7-113">Description</span></span>  

 <span data-ttu-id="030f7-114">Indica que se ha programado un CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="030f7-114">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="030f7-115">Message</span><span class="sxs-lookup"><span data-stu-id="030f7-115">Message</span></span>  

 <span data-ttu-id="030f7-116">Se ha programado un CompletionWorkItem para la actividad primaria ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="030f7-116">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="030f7-117">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="030f7-117">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="030f7-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="030f7-118">Details</span></span>  
  
|<span data-ttu-id="030f7-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="030f7-119">Data Item Name</span></span>|<span data-ttu-id="030f7-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="030f7-120">Data Item Type</span></span>|<span data-ttu-id="030f7-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="030f7-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="030f7-122">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="030f7-122">ParentActivity</span></span>|<span data-ttu-id="030f7-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="030f7-123">xs:string</span></span>|<span data-ttu-id="030f7-124">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="030f7-124">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="030f7-125">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="030f7-125">ParentDisplayName</span></span>|<span data-ttu-id="030f7-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="030f7-126">xs:string</span></span>|<span data-ttu-id="030f7-127">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="030f7-127">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="030f7-128">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="030f7-128">ParentInstanceId</span></span>|<span data-ttu-id="030f7-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="030f7-129">xs:string</span></span>|<span data-ttu-id="030f7-130">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="030f7-130">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="030f7-131">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="030f7-131">CompletedActivity</span></span>|<span data-ttu-id="030f7-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="030f7-132">xs:string</span></span>|<span data-ttu-id="030f7-133">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="030f7-133">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="030f7-134">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="030f7-134">CompletedActivityDisplayName</span></span>|<span data-ttu-id="030f7-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="030f7-135">xs:string</span></span>|<span data-ttu-id="030f7-136">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="030f7-136">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="030f7-137">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="030f7-137">CompletedActivityInstanceId</span></span>|<span data-ttu-id="030f7-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="030f7-138">xs:string</span></span>|<span data-ttu-id="030f7-139">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="030f7-139">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="030f7-140">AppDomain</span><span class="sxs-lookup"><span data-stu-id="030f7-140">AppDomain</span></span>|<span data-ttu-id="030f7-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="030f7-141">xs:string</span></span>|<span data-ttu-id="030f7-142">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="030f7-142">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
