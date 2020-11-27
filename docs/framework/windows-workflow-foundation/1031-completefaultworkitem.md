---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: 557155fab35a37bdbaa45efb26d6bc025ad825c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281838"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="35505-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="35505-102">1031 - CompleteFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="35505-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="35505-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35505-104">ID</span><span class="sxs-lookup"><span data-stu-id="35505-104">ID</span></span>|<span data-ttu-id="35505-105">1031</span><span class="sxs-lookup"><span data-stu-id="35505-105">1031</span></span>|  
|<span data-ttu-id="35505-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="35505-106">Keywords</span></span>|<span data-ttu-id="35505-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="35505-107">WFRuntime</span></span>|  
|<span data-ttu-id="35505-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="35505-108">Level</span></span>|<span data-ttu-id="35505-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="35505-109">Verbose</span></span>|  
|<span data-ttu-id="35505-110">Canal</span><span class="sxs-lookup"><span data-stu-id="35505-110">Channel</span></span>|<span data-ttu-id="35505-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="35505-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="35505-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="35505-112">Description</span></span>  

 <span data-ttu-id="35505-113">Indica que se ha completado un FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="35505-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="35505-114">Message</span><span class="sxs-lookup"><span data-stu-id="35505-114">Message</span></span>  

 <span data-ttu-id="35505-115">Un FaultWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="35505-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="35505-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="35505-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="35505-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="35505-117">Details</span></span>  
  
|<span data-ttu-id="35505-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="35505-118">Data Item Name</span></span>|<span data-ttu-id="35505-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="35505-119">Data Item Type</span></span>|<span data-ttu-id="35505-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="35505-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="35505-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="35505-121">FaultActivity</span></span>|<span data-ttu-id="35505-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="35505-122">xs:string</span></span>|<span data-ttu-id="35505-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="35505-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="35505-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="35505-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="35505-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="35505-125">xs:string</span></span>|<span data-ttu-id="35505-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="35505-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="35505-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="35505-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="35505-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="35505-128">xs:string</span></span>|<span data-ttu-id="35505-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="35505-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="35505-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="35505-130">ExceptionActivity</span></span>|<span data-ttu-id="35505-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="35505-131">xs:string</span></span>|<span data-ttu-id="35505-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="35505-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="35505-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="35505-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="35505-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="35505-134">xs:string</span></span>|<span data-ttu-id="35505-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="35505-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="35505-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="35505-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="35505-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="35505-137">xs:string</span></span>|<span data-ttu-id="35505-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="35505-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="35505-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="35505-139">Exception</span></span>|<span data-ttu-id="35505-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="35505-140">xs:string</span></span>|<span data-ttu-id="35505-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="35505-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="35505-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="35505-142">AppDomain</span></span>|<span data-ttu-id="35505-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="35505-143">xs:string</span></span>|<span data-ttu-id="35505-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="35505-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
