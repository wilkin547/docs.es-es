---
description: 'Más información acerca de: 1029-ScheduleFaultWorkItem'
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: e5f0463626882d6c8c48412326582fafa7be4670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755452"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="612ca-103">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="612ca-103">1029 - ScheduleFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="612ca-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="612ca-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="612ca-105">Id.</span><span class="sxs-lookup"><span data-stu-id="612ca-105">ID</span></span>|<span data-ttu-id="612ca-106">1029</span><span class="sxs-lookup"><span data-stu-id="612ca-106">1029</span></span>|  
|<span data-ttu-id="612ca-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="612ca-107">Keywords</span></span>|<span data-ttu-id="612ca-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="612ca-108">WFRuntime</span></span>|  
|<span data-ttu-id="612ca-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="612ca-109">Level</span></span>|<span data-ttu-id="612ca-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="612ca-110">Verbose</span></span>|  
|<span data-ttu-id="612ca-111">Canal</span><span class="sxs-lookup"><span data-stu-id="612ca-111">Channel</span></span>|<span data-ttu-id="612ca-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="612ca-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="612ca-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="612ca-113">Description</span></span>  

 <span data-ttu-id="612ca-114">Indica que se ha programado un FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="612ca-114">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="612ca-115">Message</span><span class="sxs-lookup"><span data-stu-id="612ca-115">Message</span></span>  

 <span data-ttu-id="612ca-116">Se ha programado un FaultWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="612ca-116">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="612ca-117">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="612ca-117">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="612ca-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="612ca-118">Details</span></span>  
  
|<span data-ttu-id="612ca-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="612ca-119">Data Item Name</span></span>|<span data-ttu-id="612ca-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="612ca-120">Data Item Type</span></span>|<span data-ttu-id="612ca-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="612ca-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="612ca-122">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="612ca-122">FaultActivity</span></span>|<span data-ttu-id="612ca-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="612ca-123">xs:string</span></span>|<span data-ttu-id="612ca-124">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="612ca-124">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="612ca-125">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="612ca-125">FaultActivityDisplayName</span></span>|<span data-ttu-id="612ca-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="612ca-126">xs:string</span></span>|<span data-ttu-id="612ca-127">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="612ca-127">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="612ca-128">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="612ca-128">FaultActivityInstanceId</span></span>|<span data-ttu-id="612ca-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="612ca-129">xs:string</span></span>|<span data-ttu-id="612ca-130">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="612ca-130">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="612ca-131">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="612ca-131">ExceptionActivity</span></span>|<span data-ttu-id="612ca-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="612ca-132">xs:string</span></span>|<span data-ttu-id="612ca-133">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="612ca-133">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="612ca-134">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="612ca-134">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="612ca-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="612ca-135">xs:string</span></span>|<span data-ttu-id="612ca-136">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="612ca-136">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="612ca-137">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="612ca-137">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="612ca-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="612ca-138">xs:string</span></span>|<span data-ttu-id="612ca-139">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="612ca-139">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="612ca-140">Excepción</span><span class="sxs-lookup"><span data-stu-id="612ca-140">Exception</span></span>|<span data-ttu-id="612ca-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="612ca-141">xs:string</span></span>|<span data-ttu-id="612ca-142">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="612ca-142">The exception details for the exception</span></span>|  
|<span data-ttu-id="612ca-143">AppDomain</span><span class="sxs-lookup"><span data-stu-id="612ca-143">AppDomain</span></span>|<span data-ttu-id="612ca-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="612ca-144">xs:string</span></span>|<span data-ttu-id="612ca-145">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="612ca-145">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
