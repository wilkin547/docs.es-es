---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 7fd93683851c5a8c4ab253272c3f2129b3f0bb49
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275562"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="457df-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="457df-102">1014 - ScheduleCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="457df-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="457df-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="457df-104">ID</span><span class="sxs-lookup"><span data-stu-id="457df-104">ID</span></span>|<span data-ttu-id="457df-105">1014</span><span class="sxs-lookup"><span data-stu-id="457df-105">1014</span></span>|  
|<span data-ttu-id="457df-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="457df-106">Keywords</span></span>|<span data-ttu-id="457df-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="457df-107">WFRuntime</span></span>|  
|<span data-ttu-id="457df-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="457df-108">Level</span></span>|<span data-ttu-id="457df-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="457df-109">Verbose</span></span>|  
|<span data-ttu-id="457df-110">Canal</span><span class="sxs-lookup"><span data-stu-id="457df-110">Channel</span></span>|<span data-ttu-id="457df-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="457df-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="457df-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="457df-112">Description</span></span>  

 <span data-ttu-id="457df-113">Indica que se ha programado un CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="457df-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="457df-114">Message</span><span class="sxs-lookup"><span data-stu-id="457df-114">Message</span></span>  

 <span data-ttu-id="457df-115">Se ha programado un CompletionWorkItem para la actividad primaria ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="457df-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="457df-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="457df-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="457df-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="457df-117">Details</span></span>  
  
|<span data-ttu-id="457df-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="457df-118">Data Item Name</span></span>|<span data-ttu-id="457df-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="457df-119">Data Item Type</span></span>|<span data-ttu-id="457df-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="457df-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="457df-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="457df-121">ParentActivity</span></span>|<span data-ttu-id="457df-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="457df-122">xs:string</span></span>|<span data-ttu-id="457df-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="457df-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="457df-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="457df-124">ParentDisplayName</span></span>|<span data-ttu-id="457df-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="457df-125">xs:string</span></span>|<span data-ttu-id="457df-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="457df-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="457df-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="457df-127">ParentInstanceId</span></span>|<span data-ttu-id="457df-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="457df-128">xs:string</span></span>|<span data-ttu-id="457df-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="457df-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="457df-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="457df-130">CompletedActivity</span></span>|<span data-ttu-id="457df-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="457df-131">xs:string</span></span>|<span data-ttu-id="457df-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="457df-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="457df-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="457df-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="457df-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="457df-134">xs:string</span></span>|<span data-ttu-id="457df-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="457df-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="457df-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="457df-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="457df-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="457df-137">xs:string</span></span>|<span data-ttu-id="457df-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="457df-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="457df-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="457df-139">AppDomain</span></span>|<span data-ttu-id="457df-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="457df-140">xs:string</span></span>|<span data-ttu-id="457df-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="457df-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
