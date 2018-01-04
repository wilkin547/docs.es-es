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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfa9553c25f607ec25fd968c2e8c6db061fb49dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="11a54-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="11a54-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="11a54-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="11a54-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11a54-104">Id.</span><span class="sxs-lookup"><span data-stu-id="11a54-104">ID</span></span>|<span data-ttu-id="11a54-105">1029</span><span class="sxs-lookup"><span data-stu-id="11a54-105">1029</span></span>|  
|<span data-ttu-id="11a54-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="11a54-106">Keywords</span></span>|<span data-ttu-id="11a54-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="11a54-107">WFRuntime</span></span>|  
|<span data-ttu-id="11a54-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="11a54-108">Level</span></span>|<span data-ttu-id="11a54-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="11a54-109">Verbose</span></span>|  
|<span data-ttu-id="11a54-110">Canal</span><span class="sxs-lookup"><span data-stu-id="11a54-110">Channel</span></span>|<span data-ttu-id="11a54-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="11a54-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="11a54-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="11a54-112">Description</span></span>  
 <span data-ttu-id="11a54-113">Indica que se ha programado un FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="11a54-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="11a54-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="11a54-114">Message</span></span>  
 <span data-ttu-id="11a54-115">Un FaultWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="11a54-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="11a54-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="11a54-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="11a54-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="11a54-117">Details</span></span>  
  
|<span data-ttu-id="11a54-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="11a54-118">Data Item Name</span></span>|<span data-ttu-id="11a54-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="11a54-119">Data Item Type</span></span>|<span data-ttu-id="11a54-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="11a54-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="11a54-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="11a54-121">FaultActivity</span></span>|<span data-ttu-id="11a54-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="11a54-122">xs:string</span></span>|<span data-ttu-id="11a54-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="11a54-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="11a54-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="11a54-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="11a54-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="11a54-125">xs:string</span></span>|<span data-ttu-id="11a54-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="11a54-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="11a54-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="11a54-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="11a54-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="11a54-128">xs:string</span></span>|<span data-ttu-id="11a54-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="11a54-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="11a54-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="11a54-130">ExceptionActivity</span></span>|<span data-ttu-id="11a54-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="11a54-131">xs:string</span></span>|<span data-ttu-id="11a54-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="11a54-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="11a54-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="11a54-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="11a54-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="11a54-134">xs:string</span></span>|<span data-ttu-id="11a54-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="11a54-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="11a54-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="11a54-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="11a54-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="11a54-137">xs:string</span></span>|<span data-ttu-id="11a54-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="11a54-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="11a54-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="11a54-139">Exception</span></span>|<span data-ttu-id="11a54-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="11a54-140">xs:string</span></span>|<span data-ttu-id="11a54-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="11a54-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="11a54-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="11a54-142">AppDomain</span></span>|<span data-ttu-id="11a54-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="11a54-143">xs:string</span></span>|<span data-ttu-id="11a54-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="11a54-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
