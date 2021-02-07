---
description: 'Más información acerca de: 1009-ActivityScheduled'
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 80ee250955a03927fb9db2b1242d420be77a6df8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755556"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="5d83f-103">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="5d83f-103">1009 - ActivityScheduled</span></span>

## <a name="properties"></a><span data-ttu-id="5d83f-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5d83f-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d83f-105">Id.</span><span class="sxs-lookup"><span data-stu-id="5d83f-105">ID</span></span>|<span data-ttu-id="5d83f-106">1009</span><span class="sxs-lookup"><span data-stu-id="5d83f-106">1009</span></span>|  
|<span data-ttu-id="5d83f-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d83f-107">Keywords</span></span>|<span data-ttu-id="5d83f-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5d83f-108">WFRuntime</span></span>|  
|<span data-ttu-id="5d83f-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="5d83f-109">Level</span></span>|<span data-ttu-id="5d83f-110">Información</span><span class="sxs-lookup"><span data-stu-id="5d83f-110">Information</span></span>|  
|<span data-ttu-id="5d83f-111">Canal</span><span class="sxs-lookup"><span data-stu-id="5d83f-111">Channel</span></span>|<span data-ttu-id="5d83f-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5d83f-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5d83f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d83f-113">Description</span></span>  

 <span data-ttu-id="5d83f-114">Indica que una actividad se está programando para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="5d83f-114">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5d83f-115">Message</span><span class="sxs-lookup"><span data-stu-id="5d83f-115">Message</span></span>  

 <span data-ttu-id="5d83f-116">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="5d83f-116">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5d83f-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="5d83f-117">Details</span></span>  
  
|<span data-ttu-id="5d83f-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5d83f-118">Data Item Name</span></span>|<span data-ttu-id="5d83f-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5d83f-119">Data Item Type</span></span>|<span data-ttu-id="5d83f-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d83f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5d83f-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="5d83f-121">ParentActivity</span></span>|<span data-ttu-id="5d83f-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d83f-122">xs:string</span></span>|<span data-ttu-id="5d83f-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="5d83f-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="5d83f-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="5d83f-124">ParentDisplayName</span></span>|<span data-ttu-id="5d83f-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d83f-125">xs:string</span></span>|<span data-ttu-id="5d83f-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="5d83f-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="5d83f-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="5d83f-127">ParentInstanceId</span></span>|<span data-ttu-id="5d83f-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d83f-128">xs:string</span></span>|<span data-ttu-id="5d83f-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="5d83f-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="5d83f-130">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="5d83f-130">ChildActivity</span></span>|<span data-ttu-id="5d83f-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d83f-131">xs:string</span></span>|<span data-ttu-id="5d83f-132">Nombre del tipo de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="5d83f-132">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="5d83f-133">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="5d83f-133">ChildDisplayName</span></span>|<span data-ttu-id="5d83f-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d83f-134">xs:string</span></span>|<span data-ttu-id="5d83f-135">El nombre para mostrar de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="5d83f-135">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="5d83f-136">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="5d83f-136">ChildInstanceId</span></span>|<span data-ttu-id="5d83f-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d83f-137">xs:string</span></span>|<span data-ttu-id="5d83f-138">Identificador de instancia de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="5d83f-138">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="5d83f-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5d83f-139">AppDomain</span></span>|<span data-ttu-id="5d83f-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d83f-140">xs:string</span></span>|<span data-ttu-id="5d83f-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5d83f-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
