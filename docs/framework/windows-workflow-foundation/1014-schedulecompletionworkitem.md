---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 50b00a49ea73dcbe09e8f4c4195cbce8c1cbf615
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510372"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="2f67c-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="2f67c-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="2f67c-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2f67c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f67c-104">Id.</span><span class="sxs-lookup"><span data-stu-id="2f67c-104">ID</span></span>|<span data-ttu-id="2f67c-105">1014</span><span class="sxs-lookup"><span data-stu-id="2f67c-105">1014</span></span>|  
|<span data-ttu-id="2f67c-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2f67c-106">Keywords</span></span>|<span data-ttu-id="2f67c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2f67c-107">WFRuntime</span></span>|  
|<span data-ttu-id="2f67c-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="2f67c-108">Level</span></span>|<span data-ttu-id="2f67c-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="2f67c-109">Verbose</span></span>|  
|<span data-ttu-id="2f67c-110">Canal</span><span class="sxs-lookup"><span data-stu-id="2f67c-110">Channel</span></span>|<span data-ttu-id="2f67c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2f67c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2f67c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f67c-112">Description</span></span>  
 <span data-ttu-id="2f67c-113">Indica que se ha programado un CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="2f67c-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2f67c-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2f67c-114">Message</span></span>  
 <span data-ttu-id="2f67c-115">Se ha programado un CompletionWorkItem para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="2f67c-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2f67c-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="2f67c-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2f67c-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="2f67c-117">Details</span></span>  
  
|<span data-ttu-id="2f67c-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2f67c-118">Data Item Name</span></span>|<span data-ttu-id="2f67c-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2f67c-119">Data Item Type</span></span>|<span data-ttu-id="2f67c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f67c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2f67c-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="2f67c-121">ParentActivity</span></span>|<span data-ttu-id="2f67c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f67c-122">xs:string</span></span>|<span data-ttu-id="2f67c-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="2f67c-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="2f67c-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="2f67c-124">ParentDisplayName</span></span>|<span data-ttu-id="2f67c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f67c-125">xs:string</span></span>|<span data-ttu-id="2f67c-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="2f67c-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="2f67c-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="2f67c-127">ParentInstanceId</span></span>|<span data-ttu-id="2f67c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f67c-128">xs:string</span></span>|<span data-ttu-id="2f67c-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="2f67c-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="2f67c-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="2f67c-130">CompletedActivity</span></span>|<span data-ttu-id="2f67c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f67c-131">xs:string</span></span>|<span data-ttu-id="2f67c-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="2f67c-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="2f67c-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2f67c-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="2f67c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f67c-134">xs:string</span></span>|<span data-ttu-id="2f67c-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="2f67c-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="2f67c-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2f67c-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="2f67c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f67c-137">xs:string</span></span>|<span data-ttu-id="2f67c-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="2f67c-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="2f67c-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2f67c-139">AppDomain</span></span>|<span data-ttu-id="2f67c-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f67c-140">xs:string</span></span>|<span data-ttu-id="2f67c-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2f67c-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
