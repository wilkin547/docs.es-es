---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 52034f7cc7c6f6749fbbbf06db9267ecb6279ee1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281864"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="bffd5-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="bffd5-102">1030 - StartFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="bffd5-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bffd5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bffd5-104">ID</span><span class="sxs-lookup"><span data-stu-id="bffd5-104">ID</span></span>|<span data-ttu-id="bffd5-105">1030</span><span class="sxs-lookup"><span data-stu-id="bffd5-105">1030</span></span>|  
|<span data-ttu-id="bffd5-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="bffd5-106">Keywords</span></span>|<span data-ttu-id="bffd5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bffd5-107">WFRuntime</span></span>|  
|<span data-ttu-id="bffd5-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="bffd5-108">Level</span></span>|<span data-ttu-id="bffd5-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="bffd5-109">Verbose</span></span>|  
|<span data-ttu-id="bffd5-110">Canal</span><span class="sxs-lookup"><span data-stu-id="bffd5-110">Channel</span></span>|<span data-ttu-id="bffd5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bffd5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bffd5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bffd5-112">Description</span></span>  

 <span data-ttu-id="bffd5-113">Indica que un FaultWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="bffd5-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bffd5-114">Message</span><span class="sxs-lookup"><span data-stu-id="bffd5-114">Message</span></span>  

 <span data-ttu-id="bffd5-115">Iniciando la ejecución de un FaultWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="bffd5-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="bffd5-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="bffd5-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bffd5-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="bffd5-117">Details</span></span>  
  
|<span data-ttu-id="bffd5-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="bffd5-118">Data Item Name</span></span>|<span data-ttu-id="bffd5-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="bffd5-119">Data Item Type</span></span>|<span data-ttu-id="bffd5-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="bffd5-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bffd5-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="bffd5-121">FaultActivity</span></span>|<span data-ttu-id="bffd5-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="bffd5-122">xs:string</span></span>|<span data-ttu-id="bffd5-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="bffd5-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="bffd5-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="bffd5-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="bffd5-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="bffd5-125">xs:string</span></span>|<span data-ttu-id="bffd5-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="bffd5-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="bffd5-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="bffd5-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="bffd5-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="bffd5-128">xs:string</span></span>|<span data-ttu-id="bffd5-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="bffd5-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="bffd5-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="bffd5-130">ExceptionActivity</span></span>|<span data-ttu-id="bffd5-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="bffd5-131">xs:string</span></span>|<span data-ttu-id="bffd5-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="bffd5-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="bffd5-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="bffd5-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="bffd5-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="bffd5-134">xs:string</span></span>|<span data-ttu-id="bffd5-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="bffd5-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="bffd5-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="bffd5-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="bffd5-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="bffd5-137">xs:string</span></span>|<span data-ttu-id="bffd5-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="bffd5-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="bffd5-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="bffd5-139">Exception</span></span>|<span data-ttu-id="bffd5-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="bffd5-140">xs:string</span></span>|<span data-ttu-id="bffd5-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="bffd5-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="bffd5-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bffd5-142">AppDomain</span></span>|<span data-ttu-id="bffd5-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="bffd5-143">xs:string</span></span>|<span data-ttu-id="bffd5-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bffd5-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
