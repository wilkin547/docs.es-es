---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a87ecb0a50437d83dd3c80d213553c8ac2143968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="6589d-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="6589d-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="6589d-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6589d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6589d-104">Id.</span><span class="sxs-lookup"><span data-stu-id="6589d-104">ID</span></span>|<span data-ttu-id="6589d-105">1031</span><span class="sxs-lookup"><span data-stu-id="6589d-105">1031</span></span>|  
|<span data-ttu-id="6589d-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6589d-106">Keywords</span></span>|<span data-ttu-id="6589d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6589d-107">WFRuntime</span></span>|  
|<span data-ttu-id="6589d-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="6589d-108">Level</span></span>|<span data-ttu-id="6589d-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="6589d-109">Verbose</span></span>|  
|<span data-ttu-id="6589d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="6589d-110">Channel</span></span>|<span data-ttu-id="6589d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6589d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6589d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6589d-112">Description</span></span>  
 <span data-ttu-id="6589d-113">Indica que se ha completado un FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="6589d-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6589d-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="6589d-114">Message</span></span>  
 <span data-ttu-id="6589d-115">Un FaultWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="6589d-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="6589d-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="6589d-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6589d-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="6589d-117">Details</span></span>  
  
|<span data-ttu-id="6589d-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6589d-118">Data Item Name</span></span>|<span data-ttu-id="6589d-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6589d-119">Data Item Type</span></span>|<span data-ttu-id="6589d-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6589d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6589d-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="6589d-121">FaultActivity</span></span>|<span data-ttu-id="6589d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6589d-122">xs:string</span></span>|<span data-ttu-id="6589d-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="6589d-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="6589d-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="6589d-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="6589d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6589d-125">xs:string</span></span>|<span data-ttu-id="6589d-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="6589d-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="6589d-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="6589d-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="6589d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="6589d-128">xs:string</span></span>|<span data-ttu-id="6589d-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="6589d-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="6589d-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="6589d-130">ExceptionActivity</span></span>|<span data-ttu-id="6589d-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="6589d-131">xs:string</span></span>|<span data-ttu-id="6589d-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="6589d-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="6589d-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="6589d-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="6589d-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="6589d-134">xs:string</span></span>|<span data-ttu-id="6589d-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="6589d-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="6589d-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="6589d-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="6589d-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="6589d-137">xs:string</span></span>|<span data-ttu-id="6589d-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="6589d-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="6589d-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="6589d-139">Exception</span></span>|<span data-ttu-id="6589d-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="6589d-140">xs:string</span></span>|<span data-ttu-id="6589d-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="6589d-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="6589d-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6589d-142">AppDomain</span></span>|<span data-ttu-id="6589d-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="6589d-143">xs:string</span></span>|<span data-ttu-id="6589d-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6589d-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
