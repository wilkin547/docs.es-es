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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 260647b56d945600afea5609f06d36385fa66014
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="501fb-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="501fb-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="501fb-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="501fb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="501fb-104">Id.</span><span class="sxs-lookup"><span data-stu-id="501fb-104">ID</span></span>|<span data-ttu-id="501fb-105">1031</span><span class="sxs-lookup"><span data-stu-id="501fb-105">1031</span></span>|  
|<span data-ttu-id="501fb-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="501fb-106">Keywords</span></span>|<span data-ttu-id="501fb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="501fb-107">WFRuntime</span></span>|  
|<span data-ttu-id="501fb-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="501fb-108">Level</span></span>|<span data-ttu-id="501fb-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="501fb-109">Verbose</span></span>|  
|<span data-ttu-id="501fb-110">Canal</span><span class="sxs-lookup"><span data-stu-id="501fb-110">Channel</span></span>|<span data-ttu-id="501fb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="501fb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="501fb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="501fb-112">Description</span></span>  
 <span data-ttu-id="501fb-113">Indica que se ha completado un FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="501fb-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="501fb-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="501fb-114">Message</span></span>  
 <span data-ttu-id="501fb-115">Un FaultWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="501fb-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="501fb-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="501fb-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="501fb-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="501fb-117">Details</span></span>  
  
|<span data-ttu-id="501fb-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="501fb-118">Data Item Name</span></span>|<span data-ttu-id="501fb-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="501fb-119">Data Item Type</span></span>|<span data-ttu-id="501fb-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="501fb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="501fb-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="501fb-121">FaultActivity</span></span>|<span data-ttu-id="501fb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="501fb-122">xs:string</span></span>|<span data-ttu-id="501fb-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="501fb-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="501fb-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="501fb-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="501fb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="501fb-125">xs:string</span></span>|<span data-ttu-id="501fb-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="501fb-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="501fb-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="501fb-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="501fb-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="501fb-128">xs:string</span></span>|<span data-ttu-id="501fb-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="501fb-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="501fb-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="501fb-130">ExceptionActivity</span></span>|<span data-ttu-id="501fb-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="501fb-131">xs:string</span></span>|<span data-ttu-id="501fb-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="501fb-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="501fb-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="501fb-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="501fb-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="501fb-134">xs:string</span></span>|<span data-ttu-id="501fb-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="501fb-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="501fb-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="501fb-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="501fb-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="501fb-137">xs:string</span></span>|<span data-ttu-id="501fb-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="501fb-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="501fb-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="501fb-139">Exception</span></span>|<span data-ttu-id="501fb-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="501fb-140">xs:string</span></span>|<span data-ttu-id="501fb-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="501fb-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="501fb-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="501fb-142">AppDomain</span></span>|<span data-ttu-id="501fb-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="501fb-143">xs:string</span></span>|<span data-ttu-id="501fb-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="501fb-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
