---
title: 114 - WorkflowInstanceRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bd8b4a1-b210-4c07-8156-f19392318c08
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c7f6324d6d563ca19b16a76cff809649ad90e3dd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="114---workflowinstancerecordwithid"></a><span data-ttu-id="e3560-102">114 - WorkflowInstanceRecordWithId</span><span class="sxs-lookup"><span data-stu-id="e3560-102">114 - WorkflowInstanceRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="e3560-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e3560-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3560-104">Id.</span><span class="sxs-lookup"><span data-stu-id="e3560-104">ID</span></span>|<span data-ttu-id="e3560-105">114</span><span class="sxs-lookup"><span data-stu-id="e3560-105">114</span></span>|  
|<span data-ttu-id="e3560-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e3560-106">Keywords</span></span>|<span data-ttu-id="e3560-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="e3560-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="e3560-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="e3560-108">Level</span></span>|<span data-ttu-id="e3560-109">Información</span><span class="sxs-lookup"><span data-stu-id="e3560-109">Information</span></span>|  
|<span data-ttu-id="e3560-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e3560-110">Channel</span></span>|<span data-ttu-id="e3560-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e3560-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e3560-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3560-112">Description</span></span>  
 <span data-ttu-id="e3560-113">El participante de seguimiento de ETW emite este evento cuando una instancia de flujo de trabajo emite WorkflowInstanceRecord para los estados del flujo de trabajo: iniciado, reanudado, conservado, inactivo, eliminado, completado, cancelado, descargado y no suspendido.</span><span class="sxs-lookup"><span data-stu-id="e3560-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceRecord for workflow states : Started, Resumed, Persisted, Idle, Deleted, Completed, Canceled, Unloaded, Unsuspended.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e3560-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="e3560-114">Message</span></span>  
 <span data-ttu-id="e3560-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="e3560-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="e3560-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="e3560-116">Details</span></span>  
  
|<span data-ttu-id="e3560-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e3560-117">Data Item Name</span></span>|<span data-ttu-id="e3560-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e3560-118">Data Item Type</span></span>|<span data-ttu-id="e3560-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3560-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e3560-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e3560-120">InstanceId</span></span>|<span data-ttu-id="e3560-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="e3560-121">xs:GUID</span></span>|<span data-ttu-id="e3560-122">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e3560-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="e3560-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="e3560-123">RecordNumber</span></span>|<span data-ttu-id="e3560-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="e3560-124">xs:long</span></span>|<span data-ttu-id="e3560-125">El número de secuencia del registro emitido.</span><span class="sxs-lookup"><span data-stu-id="e3560-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="e3560-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="e3560-126">EventTime</span></span>|<span data-ttu-id="e3560-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="e3560-127">xs:dateTime</span></span>|<span data-ttu-id="e3560-128">La hora en UTC cuando se emitió el evento.</span><span class="sxs-lookup"><span data-stu-id="e3560-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="e3560-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="e3560-129">ActivityDefinitionId</span></span>|<span data-ttu-id="e3560-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3560-130">xs:string</span></span>|<span data-ttu-id="e3560-131">El nombre de la actividad raíz del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e3560-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="e3560-132">Estado</span><span class="sxs-lookup"><span data-stu-id="e3560-132">State</span></span>|<span data-ttu-id="e3560-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3560-133">xs:string</span></span>|<span data-ttu-id="e3560-134">El estado actual del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e3560-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="e3560-135">Anotaciones</span><span class="sxs-lookup"><span data-stu-id="e3560-135">Annotations</span></span>|<span data-ttu-id="e3560-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3560-136">xs:string</span></span>|<span data-ttu-id="e3560-137">Las anotaciones que se agregaron a este evento.</span><span class="sxs-lookup"><span data-stu-id="e3560-137">The annotations that were added to this event.</span></span> <span data-ttu-id="e3560-138">Los valores se almacenan en un elemento xml con el formato \<elementos >\< nombre de elemento = "annotationName" Type = "> annotationValue\</artículo > \< /artículos >.</span><span class="sxs-lookup"><span data-stu-id="e3560-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="e3560-139">Si se especifica ninguna anotación, a continuación, la cadena contiene \<elementos / >.</span><span class="sxs-lookup"><span data-stu-id="e3560-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="e3560-140">El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW.</span><span class="sxs-lookup"><span data-stu-id="e3560-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="e3560-141">Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación con \<elementos >...  \< /artículos >.</span><span class="sxs-lookup"><span data-stu-id="e3560-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="e3560-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="e3560-142">ProfileName</span></span>|<span data-ttu-id="e3560-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3560-143">xs:string</span></span>|<span data-ttu-id="e3560-144">El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.</span><span class="sxs-lookup"><span data-stu-id="e3560-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="e3560-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="e3560-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="e3560-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3560-146">xs:string</span></span>|<span data-ttu-id="e3560-147">Id. de definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e3560-147">The workflow definition id</span></span>|  
|<span data-ttu-id="e3560-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e3560-148">AppDomain</span></span>|<span data-ttu-id="e3560-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3560-149">xs:string</span></span>|<span data-ttu-id="e3560-150">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e3560-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
