---
title: 1009 - ActivityScheduled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdaa8ca4efeffb3895e0056303721b13cdc1ae27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="e1555-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="e1555-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="e1555-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e1555-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1555-104">Id.</span><span class="sxs-lookup"><span data-stu-id="e1555-104">ID</span></span>|<span data-ttu-id="e1555-105">1009</span><span class="sxs-lookup"><span data-stu-id="e1555-105">1009</span></span>|  
|<span data-ttu-id="e1555-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e1555-106">Keywords</span></span>|<span data-ttu-id="e1555-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e1555-107">WFRuntime</span></span>|  
|<span data-ttu-id="e1555-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="e1555-108">Level</span></span>|<span data-ttu-id="e1555-109">Información</span><span class="sxs-lookup"><span data-stu-id="e1555-109">Information</span></span>|  
|<span data-ttu-id="e1555-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e1555-110">Channel</span></span>|<span data-ttu-id="e1555-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e1555-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e1555-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1555-112">Description</span></span>  
 <span data-ttu-id="e1555-113">Indica que una actividad se está programando para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e1555-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e1555-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="e1555-114">Message</span></span>  
 <span data-ttu-id="e1555-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="e1555-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e1555-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="e1555-116">Details</span></span>  
  
|<span data-ttu-id="e1555-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e1555-117">Data Item Name</span></span>|<span data-ttu-id="e1555-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e1555-118">Data Item Type</span></span>|<span data-ttu-id="e1555-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1555-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e1555-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="e1555-120">ParentActivity</span></span>|<span data-ttu-id="e1555-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1555-121">xs:string</span></span>|<span data-ttu-id="e1555-122">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="e1555-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="e1555-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="e1555-123">ParentDisplayName</span></span>|<span data-ttu-id="e1555-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1555-124">xs:string</span></span>|<span data-ttu-id="e1555-125">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="e1555-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="e1555-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="e1555-126">ParentInstanceId</span></span>|<span data-ttu-id="e1555-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1555-127">xs:string</span></span>|<span data-ttu-id="e1555-128">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="e1555-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="e1555-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="e1555-129">ChildActivity</span></span>|<span data-ttu-id="e1555-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1555-130">xs:string</span></span>|<span data-ttu-id="e1555-131">Nombre del tipo de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="e1555-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="e1555-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="e1555-132">ChildDisplayName</span></span>|<span data-ttu-id="e1555-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1555-133">xs:string</span></span>|<span data-ttu-id="e1555-134">El nombre para mostrar de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="e1555-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="e1555-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="e1555-135">ChildInstanceId</span></span>|<span data-ttu-id="e1555-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1555-136">xs:string</span></span>|<span data-ttu-id="e1555-137">Identificador de instancia de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="e1555-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="e1555-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e1555-138">AppDomain</span></span>|<span data-ttu-id="e1555-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1555-139">xs:string</span></span>|<span data-ttu-id="e1555-140">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e1555-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
