---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 50b00a49ea73dcbe09e8f4c4195cbce8c1cbf615
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982272"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="09d0d-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="09d0d-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="09d0d-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="09d0d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="09d0d-104">ID</span><span class="sxs-lookup"><span data-stu-id="09d0d-104">ID</span></span>|<span data-ttu-id="09d0d-105">1014</span><span class="sxs-lookup"><span data-stu-id="09d0d-105">1014</span></span>|  
|<span data-ttu-id="09d0d-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="09d0d-106">Keywords</span></span>|<span data-ttu-id="09d0d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="09d0d-107">WFRuntime</span></span>|  
|<span data-ttu-id="09d0d-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="09d0d-108">Level</span></span>|<span data-ttu-id="09d0d-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="09d0d-109">Verbose</span></span>|  
|<span data-ttu-id="09d0d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="09d0d-110">Channel</span></span>|<span data-ttu-id="09d0d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="09d0d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="09d0d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="09d0d-112">Description</span></span>  
 <span data-ttu-id="09d0d-113">Indica que se ha programado un CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="09d0d-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="09d0d-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="09d0d-114">Message</span></span>  
 <span data-ttu-id="09d0d-115">Se ha programado un CompletionWorkItem para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="09d0d-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="09d0d-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="09d0d-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="09d0d-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="09d0d-117">Details</span></span>  
  
|<span data-ttu-id="09d0d-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="09d0d-118">Data Item Name</span></span>|<span data-ttu-id="09d0d-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="09d0d-119">Data Item Type</span></span>|<span data-ttu-id="09d0d-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="09d0d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="09d0d-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="09d0d-121">ParentActivity</span></span>|<span data-ttu-id="09d0d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="09d0d-122">xs:string</span></span>|<span data-ttu-id="09d0d-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="09d0d-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="09d0d-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="09d0d-124">ParentDisplayName</span></span>|<span data-ttu-id="09d0d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="09d0d-125">xs:string</span></span>|<span data-ttu-id="09d0d-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="09d0d-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="09d0d-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="09d0d-127">ParentInstanceId</span></span>|<span data-ttu-id="09d0d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="09d0d-128">xs:string</span></span>|<span data-ttu-id="09d0d-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="09d0d-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="09d0d-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="09d0d-130">CompletedActivity</span></span>|<span data-ttu-id="09d0d-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="09d0d-131">xs:string</span></span>|<span data-ttu-id="09d0d-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="09d0d-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="09d0d-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="09d0d-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="09d0d-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="09d0d-134">xs:string</span></span>|<span data-ttu-id="09d0d-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="09d0d-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="09d0d-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="09d0d-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="09d0d-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="09d0d-137">xs:string</span></span>|<span data-ttu-id="09d0d-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="09d0d-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="09d0d-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="09d0d-139">AppDomain</span></span>|<span data-ttu-id="09d0d-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="09d0d-140">xs:string</span></span>|<span data-ttu-id="09d0d-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="09d0d-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
