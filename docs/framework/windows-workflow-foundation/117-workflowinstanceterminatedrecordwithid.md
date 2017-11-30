---
title: 117 - WorkflowInstanceTerminatedRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e68539d0-5338-468a-9f75-7e5b09d39a3c
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c8b2bc6325ec6f5cf1c3af8b7748a45ad21809cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="117---workflowinstanceterminatedrecordwithid"></a><span data-ttu-id="8babf-102">117 - WorkflowInstanceTerminatedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="8babf-102">117 - WorkflowInstanceTerminatedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="8babf-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8babf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8babf-104">Id.</span><span class="sxs-lookup"><span data-stu-id="8babf-104">ID</span></span>|<span data-ttu-id="8babf-105">117</span><span class="sxs-lookup"><span data-stu-id="8babf-105">117</span></span>|  
|<span data-ttu-id="8babf-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8babf-106">Keywords</span></span>|<span data-ttu-id="8babf-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="8babf-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="8babf-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="8babf-108">Level</span></span>|<span data-ttu-id="8babf-109">Error</span><span class="sxs-lookup"><span data-stu-id="8babf-109">Error</span></span>|  
|<span data-ttu-id="8babf-110">Canal</span><span class="sxs-lookup"><span data-stu-id="8babf-110">Channel</span></span>|<span data-ttu-id="8babf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="8babf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8babf-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8babf-112">Description</span></span>  
 <span data-ttu-id="8babf-113">El participante de seguimiento de ETW emite este evento cuando una instancia de flujo de trabajo emite   una clase WorkflowInstanceTerminatedRecord.</span><span class="sxs-lookup"><span data-stu-id="8babf-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceTerminatedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8babf-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="8babf-114">Message</span></span>  
 <span data-ttu-id="8babf-115">TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, razón = %5, anotaciones = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="8babf-115">TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="8babf-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="8babf-116">Details</span></span>  
  
|<span data-ttu-id="8babf-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8babf-117">Data Item Name</span></span>|<span data-ttu-id="8babf-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8babf-118">Data Item Type</span></span>|<span data-ttu-id="8babf-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="8babf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8babf-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8babf-120">InstanceId</span></span>|<span data-ttu-id="8babf-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="8babf-121">xs:GUID</span></span>|<span data-ttu-id="8babf-122">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8babf-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="8babf-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="8babf-123">RecordNumber</span></span>|<span data-ttu-id="8babf-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="8babf-124">xs:long</span></span>|<span data-ttu-id="8babf-125">El número de secuencia del registro emitido.</span><span class="sxs-lookup"><span data-stu-id="8babf-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="8babf-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="8babf-126">EventTime</span></span>|<span data-ttu-id="8babf-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="8babf-127">xs:dateTime</span></span>|<span data-ttu-id="8babf-128">La hora en UTC cuando se emitió el evento.</span><span class="sxs-lookup"><span data-stu-id="8babf-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="8babf-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="8babf-129">ActivityDefinitionId</span></span>|<span data-ttu-id="8babf-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8babf-130">xs:string</span></span>|<span data-ttu-id="8babf-131">El nombre de la actividad raíz del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8babf-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="8babf-132">Estado</span><span class="sxs-lookup"><span data-stu-id="8babf-132">State</span></span>|<span data-ttu-id="8babf-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="8babf-133">xs:string</span></span>|<span data-ttu-id="8babf-134">El estado actual del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8babf-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="8babf-135">Anotaciones</span><span class="sxs-lookup"><span data-stu-id="8babf-135">Annotations</span></span>|<span data-ttu-id="8babf-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="8babf-136">xs:string</span></span>|<span data-ttu-id="8babf-137">Las anotaciones que se agregaron a este evento.</span><span class="sxs-lookup"><span data-stu-id="8babf-137">The annotations that were added to this event.</span></span> <span data-ttu-id="8babf-138">Los valores se almacenan en un elemento xml con el formato \<elementos >\< nombre de elemento = "annotationName" Type = "> annotationValue\</artículo > \< /artículos >.</span><span class="sxs-lookup"><span data-stu-id="8babf-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="8babf-139">Si se especifica ninguna anotación, a continuación, la cadena contiene \<elementos / >.</span><span class="sxs-lookup"><span data-stu-id="8babf-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="8babf-140">El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW.</span><span class="sxs-lookup"><span data-stu-id="8babf-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="8babf-141">Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación con \<elementos >...  \< /artículos >.</span><span class="sxs-lookup"><span data-stu-id="8babf-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="8babf-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="8babf-142">ProfileName</span></span>|<span data-ttu-id="8babf-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="8babf-143">xs:string</span></span>|<span data-ttu-id="8babf-144">El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.</span><span class="sxs-lookup"><span data-stu-id="8babf-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="8babf-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="8babf-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="8babf-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="8babf-146">xs:string</span></span>|<span data-ttu-id="8babf-147">Id. de definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8babf-147">The workflow definition id</span></span>|  
|<span data-ttu-id="8babf-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8babf-148">AppDomain</span></span>|<span data-ttu-id="8babf-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="8babf-149">xs:string</span></span>|<span data-ttu-id="8babf-150">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8babf-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
