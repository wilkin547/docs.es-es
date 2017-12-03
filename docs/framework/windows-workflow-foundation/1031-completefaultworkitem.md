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
ms.openlocfilehash: 5173e61b2479d02dc35c5fcf9ae55634cc8dc7ba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="43e70-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="43e70-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="43e70-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43e70-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="43e70-104">Id.</span><span class="sxs-lookup"><span data-stu-id="43e70-104">ID</span></span>|<span data-ttu-id="43e70-105">1031</span><span class="sxs-lookup"><span data-stu-id="43e70-105">1031</span></span>|  
|<span data-ttu-id="43e70-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="43e70-106">Keywords</span></span>|<span data-ttu-id="43e70-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="43e70-107">WFRuntime</span></span>|  
|<span data-ttu-id="43e70-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="43e70-108">Level</span></span>|<span data-ttu-id="43e70-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="43e70-109">Verbose</span></span>|  
|<span data-ttu-id="43e70-110">Canal</span><span class="sxs-lookup"><span data-stu-id="43e70-110">Channel</span></span>|<span data-ttu-id="43e70-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="43e70-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="43e70-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="43e70-112">Description</span></span>  
 <span data-ttu-id="43e70-113">Indica que se ha completado un FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="43e70-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="43e70-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="43e70-114">Message</span></span>  
 <span data-ttu-id="43e70-115">Un FaultWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="43e70-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="43e70-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="43e70-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="43e70-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="43e70-117">Details</span></span>  
  
|<span data-ttu-id="43e70-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="43e70-118">Data Item Name</span></span>|<span data-ttu-id="43e70-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="43e70-119">Data Item Type</span></span>|<span data-ttu-id="43e70-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="43e70-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="43e70-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="43e70-121">FaultActivity</span></span>|<span data-ttu-id="43e70-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="43e70-122">xs:string</span></span>|<span data-ttu-id="43e70-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="43e70-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="43e70-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="43e70-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="43e70-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="43e70-125">xs:string</span></span>|<span data-ttu-id="43e70-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="43e70-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="43e70-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="43e70-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="43e70-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="43e70-128">xs:string</span></span>|<span data-ttu-id="43e70-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="43e70-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="43e70-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="43e70-130">ExceptionActivity</span></span>|<span data-ttu-id="43e70-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="43e70-131">xs:string</span></span>|<span data-ttu-id="43e70-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="43e70-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="43e70-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="43e70-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="43e70-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="43e70-134">xs:string</span></span>|<span data-ttu-id="43e70-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="43e70-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="43e70-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="43e70-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="43e70-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="43e70-137">xs:string</span></span>|<span data-ttu-id="43e70-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="43e70-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="43e70-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="43e70-139">Exception</span></span>|<span data-ttu-id="43e70-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="43e70-140">xs:string</span></span>|<span data-ttu-id="43e70-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="43e70-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="43e70-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="43e70-142">AppDomain</span></span>|<span data-ttu-id="43e70-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="43e70-143">xs:string</span></span>|<span data-ttu-id="43e70-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="43e70-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
