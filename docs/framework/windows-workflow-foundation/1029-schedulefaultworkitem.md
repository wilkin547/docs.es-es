---
title: 1029 - ScheduleFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1ba1ae69caff2e08da58e824d35341d3781ea8ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="8f821-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="8f821-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8f821-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8f821-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f821-104">Id.</span><span class="sxs-lookup"><span data-stu-id="8f821-104">ID</span></span>|<span data-ttu-id="8f821-105">1029</span><span class="sxs-lookup"><span data-stu-id="8f821-105">1029</span></span>|  
|<span data-ttu-id="8f821-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8f821-106">Keywords</span></span>|<span data-ttu-id="8f821-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8f821-107">WFRuntime</span></span>|  
|<span data-ttu-id="8f821-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="8f821-108">Level</span></span>|<span data-ttu-id="8f821-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="8f821-109">Verbose</span></span>|  
|<span data-ttu-id="8f821-110">Canal</span><span class="sxs-lookup"><span data-stu-id="8f821-110">Channel</span></span>|<span data-ttu-id="8f821-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8f821-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8f821-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f821-112">Description</span></span>  
 <span data-ttu-id="8f821-113">Indica que se ha programado un FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="8f821-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8f821-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="8f821-114">Message</span></span>  
 <span data-ttu-id="8f821-115">Un FaultWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="8f821-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="8f821-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="8f821-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8f821-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="8f821-117">Details</span></span>  
  
|<span data-ttu-id="8f821-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8f821-118">Data Item Name</span></span>|<span data-ttu-id="8f821-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8f821-119">Data Item Type</span></span>|<span data-ttu-id="8f821-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f821-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8f821-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="8f821-121">FaultActivity</span></span>|<span data-ttu-id="8f821-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f821-122">xs:string</span></span>|<span data-ttu-id="8f821-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="8f821-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="8f821-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="8f821-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="8f821-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f821-125">xs:string</span></span>|<span data-ttu-id="8f821-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="8f821-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="8f821-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="8f821-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="8f821-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f821-128">xs:string</span></span>|<span data-ttu-id="8f821-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="8f821-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="8f821-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="8f821-130">ExceptionActivity</span></span>|<span data-ttu-id="8f821-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f821-131">xs:string</span></span>|<span data-ttu-id="8f821-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="8f821-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="8f821-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="8f821-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="8f821-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f821-134">xs:string</span></span>|<span data-ttu-id="8f821-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="8f821-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="8f821-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="8f821-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="8f821-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f821-137">xs:string</span></span>|<span data-ttu-id="8f821-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="8f821-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="8f821-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="8f821-139">Exception</span></span>|<span data-ttu-id="8f821-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f821-140">xs:string</span></span>|<span data-ttu-id="8f821-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="8f821-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="8f821-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8f821-142">AppDomain</span></span>|<span data-ttu-id="8f821-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f821-143">xs:string</span></span>|<span data-ttu-id="8f821-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8f821-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
