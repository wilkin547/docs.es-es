---
description: 'Más información acerca de: 1031-CompleteFaultWorkItem'
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: dc5cb4988df2aab9710fd7ec875d9b4004bfa7af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668076"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="f4ad5-103">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="f4ad5-103">1031 - CompleteFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="f4ad5-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f4ad5-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4ad5-105">Id.</span><span class="sxs-lookup"><span data-stu-id="f4ad5-105">ID</span></span>|<span data-ttu-id="f4ad5-106">1031</span><span class="sxs-lookup"><span data-stu-id="f4ad5-106">1031</span></span>|  
|<span data-ttu-id="f4ad5-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f4ad5-107">Keywords</span></span>|<span data-ttu-id="f4ad5-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f4ad5-108">WFRuntime</span></span>|  
|<span data-ttu-id="f4ad5-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="f4ad5-109">Level</span></span>|<span data-ttu-id="f4ad5-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="f4ad5-110">Verbose</span></span>|  
|<span data-ttu-id="f4ad5-111">Canal</span><span class="sxs-lookup"><span data-stu-id="f4ad5-111">Channel</span></span>|<span data-ttu-id="f4ad5-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f4ad5-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f4ad5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4ad5-113">Description</span></span>  

 <span data-ttu-id="f4ad5-114">Indica que se ha completado un FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="f4ad5-114">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f4ad5-115">Message</span><span class="sxs-lookup"><span data-stu-id="f4ad5-115">Message</span></span>  

 <span data-ttu-id="f4ad5-116">Un FaultWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="f4ad5-116">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="f4ad5-117">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="f4ad5-117">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f4ad5-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="f4ad5-118">Details</span></span>  
  
|<span data-ttu-id="f4ad5-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f4ad5-119">Data Item Name</span></span>|<span data-ttu-id="f4ad5-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f4ad5-120">Data Item Type</span></span>|<span data-ttu-id="f4ad5-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4ad5-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f4ad5-122">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="f4ad5-122">FaultActivity</span></span>|<span data-ttu-id="f4ad5-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4ad5-123">xs:string</span></span>|<span data-ttu-id="f4ad5-124">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="f4ad5-124">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="f4ad5-125">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f4ad5-125">FaultActivityDisplayName</span></span>|<span data-ttu-id="f4ad5-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4ad5-126">xs:string</span></span>|<span data-ttu-id="f4ad5-127">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="f4ad5-127">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="f4ad5-128">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f4ad5-128">FaultActivityInstanceId</span></span>|<span data-ttu-id="f4ad5-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4ad5-129">xs:string</span></span>|<span data-ttu-id="f4ad5-130">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="f4ad5-130">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="f4ad5-131">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="f4ad5-131">ExceptionActivity</span></span>|<span data-ttu-id="f4ad5-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4ad5-132">xs:string</span></span>|<span data-ttu-id="f4ad5-133">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="f4ad5-133">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f4ad5-134">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f4ad5-134">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="f4ad5-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4ad5-135">xs:string</span></span>|<span data-ttu-id="f4ad5-136">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="f4ad5-136">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f4ad5-137">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f4ad5-137">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="f4ad5-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4ad5-138">xs:string</span></span>|<span data-ttu-id="f4ad5-139">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="f4ad5-139">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f4ad5-140">Excepción</span><span class="sxs-lookup"><span data-stu-id="f4ad5-140">Exception</span></span>|<span data-ttu-id="f4ad5-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4ad5-141">xs:string</span></span>|<span data-ttu-id="f4ad5-142">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="f4ad5-142">The exception details for the exception</span></span>|  
|<span data-ttu-id="f4ad5-143">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f4ad5-143">AppDomain</span></span>|<span data-ttu-id="f4ad5-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4ad5-144">xs:string</span></span>|<span data-ttu-id="f4ad5-145">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f4ad5-145">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
