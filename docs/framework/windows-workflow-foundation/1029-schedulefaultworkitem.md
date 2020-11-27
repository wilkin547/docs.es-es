---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: 5c109607b2d353d3d4a5a693f29ab66bb76c8398
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275094"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="c7b79-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="c7b79-102">1029 - ScheduleFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="c7b79-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c7b79-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7b79-104">ID</span><span class="sxs-lookup"><span data-stu-id="c7b79-104">ID</span></span>|<span data-ttu-id="c7b79-105">1029</span><span class="sxs-lookup"><span data-stu-id="c7b79-105">1029</span></span>|  
|<span data-ttu-id="c7b79-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c7b79-106">Keywords</span></span>|<span data-ttu-id="c7b79-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c7b79-107">WFRuntime</span></span>|  
|<span data-ttu-id="c7b79-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="c7b79-108">Level</span></span>|<span data-ttu-id="c7b79-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="c7b79-109">Verbose</span></span>|  
|<span data-ttu-id="c7b79-110">Canal</span><span class="sxs-lookup"><span data-stu-id="c7b79-110">Channel</span></span>|<span data-ttu-id="c7b79-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c7b79-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c7b79-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7b79-112">Description</span></span>  

 <span data-ttu-id="c7b79-113">Indica que se ha programado un FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="c7b79-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c7b79-114">Message</span><span class="sxs-lookup"><span data-stu-id="c7b79-114">Message</span></span>  

 <span data-ttu-id="c7b79-115">Se ha programado un FaultWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="c7b79-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c7b79-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="c7b79-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c7b79-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="c7b79-117">Details</span></span>  
  
|<span data-ttu-id="c7b79-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c7b79-118">Data Item Name</span></span>|<span data-ttu-id="c7b79-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c7b79-119">Data Item Type</span></span>|<span data-ttu-id="c7b79-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7b79-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c7b79-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="c7b79-121">FaultActivity</span></span>|<span data-ttu-id="c7b79-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7b79-122">xs:string</span></span>|<span data-ttu-id="c7b79-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="c7b79-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="c7b79-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c7b79-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="c7b79-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7b79-125">xs:string</span></span>|<span data-ttu-id="c7b79-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="c7b79-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="c7b79-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c7b79-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="c7b79-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7b79-128">xs:string</span></span>|<span data-ttu-id="c7b79-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="c7b79-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="c7b79-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="c7b79-130">ExceptionActivity</span></span>|<span data-ttu-id="c7b79-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7b79-131">xs:string</span></span>|<span data-ttu-id="c7b79-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="c7b79-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c7b79-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c7b79-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="c7b79-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7b79-134">xs:string</span></span>|<span data-ttu-id="c7b79-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="c7b79-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c7b79-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c7b79-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="c7b79-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7b79-137">xs:string</span></span>|<span data-ttu-id="c7b79-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="c7b79-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c7b79-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="c7b79-139">Exception</span></span>|<span data-ttu-id="c7b79-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7b79-140">xs:string</span></span>|<span data-ttu-id="c7b79-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="c7b79-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="c7b79-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c7b79-142">AppDomain</span></span>|<span data-ttu-id="c7b79-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7b79-143">xs:string</span></span>|<span data-ttu-id="c7b79-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c7b79-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
