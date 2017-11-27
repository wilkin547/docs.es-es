---
title: 116 - WorkflowInstanceSuspendedRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38232c03-6139-4494-a020-79bc83eb9dce
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6dc875721c323a48f5cc0b49e4ef0e7c167622b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="116---workflowinstancesuspendedrecordwithid"></a><span data-ttu-id="97e0d-102">116 - WorkflowInstanceSuspendedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="97e0d-102">116 - WorkflowInstanceSuspendedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="97e0d-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="97e0d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="97e0d-104">Id.</span><span class="sxs-lookup"><span data-stu-id="97e0d-104">ID</span></span>|<span data-ttu-id="97e0d-105">116</span><span class="sxs-lookup"><span data-stu-id="97e0d-105">116</span></span>|  
|<span data-ttu-id="97e0d-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="97e0d-106">Keywords</span></span>|<span data-ttu-id="97e0d-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="97e0d-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="97e0d-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="97e0d-108">Level</span></span>|<span data-ttu-id="97e0d-109">Información</span><span class="sxs-lookup"><span data-stu-id="97e0d-109">Information</span></span>|  
|<span data-ttu-id="97e0d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="97e0d-110">Channel</span></span>|<span data-ttu-id="97e0d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="97e0d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="97e0d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="97e0d-112">Description</span></span>  
 <span data-ttu-id="97e0d-113">El participante de seguimiento de ETW emite este evento cuando una instancia de flujo de trabajo emite WorkflowInstanceSuspended Record.</span><span class="sxs-lookup"><span data-stu-id="97e0d-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceSuspended Record.</span></span>  
  
## <a name="message"></a><span data-ttu-id="97e0d-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="97e0d-114">Message</span></span>  
 <span data-ttu-id="97e0d-115">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="97e0d-115">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="97e0d-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="97e0d-116">Details</span></span>  
  
|<span data-ttu-id="97e0d-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="97e0d-117">Data Item Name</span></span>|<span data-ttu-id="97e0d-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="97e0d-118">Data Item Type</span></span>|<span data-ttu-id="97e0d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="97e0d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="97e0d-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="97e0d-120">InstanceId</span></span>|<span data-ttu-id="97e0d-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="97e0d-121">xs:GUID</span></span>|<span data-ttu-id="97e0d-122">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97e0d-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="97e0d-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="97e0d-123">RecordNumber</span></span>|<span data-ttu-id="97e0d-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="97e0d-124">xs:long</span></span>|<span data-ttu-id="97e0d-125">El número de secuencia del registro emitido.</span><span class="sxs-lookup"><span data-stu-id="97e0d-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="97e0d-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="97e0d-126">EventTime</span></span>|<span data-ttu-id="97e0d-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="97e0d-127">xs:dateTime</span></span>|<span data-ttu-id="97e0d-128">La hora en UTC cuando se emitió el evento.</span><span class="sxs-lookup"><span data-stu-id="97e0d-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="97e0d-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="97e0d-129">ActivityDefinitionId</span></span>|<span data-ttu-id="97e0d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="97e0d-130">xs:string</span></span>|<span data-ttu-id="97e0d-131">El nombre de la actividad raíz del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97e0d-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="97e0d-132">Estado</span><span class="sxs-lookup"><span data-stu-id="97e0d-132">State</span></span>|<span data-ttu-id="97e0d-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="97e0d-133">xs:string</span></span>|<span data-ttu-id="97e0d-134">El estado actual del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97e0d-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="97e0d-135">Anotaciones</span><span class="sxs-lookup"><span data-stu-id="97e0d-135">Annotations</span></span>|<span data-ttu-id="97e0d-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="97e0d-136">xs:string</span></span>|<span data-ttu-id="97e0d-137">Las anotaciones que se agregaron a este evento.</span><span class="sxs-lookup"><span data-stu-id="97e0d-137">The annotations that were added to this event.</span></span> <span data-ttu-id="97e0d-138">Los valores se almacenan en un elemento xml con el formato \<elementos >\< nombre de elemento = "annotationName" Type = "> annotationValue\</artículo > \< /artículos >.</span><span class="sxs-lookup"><span data-stu-id="97e0d-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="97e0d-139">Si se especifica ninguna anotación, a continuación, la cadena contiene \<elementos / >.</span><span class="sxs-lookup"><span data-stu-id="97e0d-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="97e0d-140">El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW.</span><span class="sxs-lookup"><span data-stu-id="97e0d-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="97e0d-141">Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación con \<elementos >...  \< /artículos >.</span><span class="sxs-lookup"><span data-stu-id="97e0d-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="97e0d-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="97e0d-142">ProfileName</span></span>|<span data-ttu-id="97e0d-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="97e0d-143">xs:string</span></span>|<span data-ttu-id="97e0d-144">El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.</span><span class="sxs-lookup"><span data-stu-id="97e0d-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="97e0d-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="97e0d-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="97e0d-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="97e0d-146">xs:string</span></span>|<span data-ttu-id="97e0d-147">Id. de definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97e0d-147">The workflow definition id</span></span>|  
|<span data-ttu-id="97e0d-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="97e0d-148">AppDomain</span></span>|<span data-ttu-id="97e0d-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="97e0d-149">xs:string</span></span>|<span data-ttu-id="97e0d-150">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="97e0d-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
