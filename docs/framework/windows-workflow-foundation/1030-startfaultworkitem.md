---
title: 1030 - StartFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 436a0323fcf4498a1d707f7af9bd8204885fd645
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="fd4dc-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="fd4dc-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fd4dc-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fd4dc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd4dc-104">Id.</span><span class="sxs-lookup"><span data-stu-id="fd4dc-104">ID</span></span>|<span data-ttu-id="fd4dc-105">1030</span><span class="sxs-lookup"><span data-stu-id="fd4dc-105">1030</span></span>|  
|<span data-ttu-id="fd4dc-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="fd4dc-106">Keywords</span></span>|<span data-ttu-id="fd4dc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fd4dc-107">WFRuntime</span></span>|  
|<span data-ttu-id="fd4dc-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="fd4dc-108">Level</span></span>|<span data-ttu-id="fd4dc-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="fd4dc-109">Verbose</span></span>|  
|<span data-ttu-id="fd4dc-110">Canal</span><span class="sxs-lookup"><span data-stu-id="fd4dc-110">Channel</span></span>|<span data-ttu-id="fd4dc-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fd4dc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fd4dc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd4dc-112">Description</span></span>  
 <span data-ttu-id="fd4dc-113">Indica que un FaultWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="fd4dc-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fd4dc-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="fd4dc-114">Message</span></span>  
 <span data-ttu-id="fd4dc-115">Iniciando la ejecución de un FaultWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="fd4dc-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="fd4dc-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="fd4dc-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fd4dc-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="fd4dc-117">Details</span></span>  
  
|<span data-ttu-id="fd4dc-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fd4dc-118">Data Item Name</span></span>|<span data-ttu-id="fd4dc-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fd4dc-119">Data Item Type</span></span>|<span data-ttu-id="fd4dc-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd4dc-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fd4dc-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="fd4dc-121">FaultActivity</span></span>|<span data-ttu-id="fd4dc-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd4dc-122">xs:string</span></span>|<span data-ttu-id="fd4dc-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="fd4dc-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="fd4dc-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="fd4dc-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="fd4dc-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd4dc-125">xs:string</span></span>|<span data-ttu-id="fd4dc-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="fd4dc-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="fd4dc-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="fd4dc-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="fd4dc-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd4dc-128">xs:string</span></span>|<span data-ttu-id="fd4dc-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="fd4dc-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="fd4dc-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="fd4dc-130">ExceptionActivity</span></span>|<span data-ttu-id="fd4dc-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd4dc-131">xs:string</span></span>|<span data-ttu-id="fd4dc-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="fd4dc-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="fd4dc-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="fd4dc-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="fd4dc-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd4dc-134">xs:string</span></span>|<span data-ttu-id="fd4dc-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="fd4dc-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="fd4dc-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="fd4dc-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="fd4dc-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd4dc-137">xs:string</span></span>|<span data-ttu-id="fd4dc-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="fd4dc-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="fd4dc-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="fd4dc-139">Exception</span></span>|<span data-ttu-id="fd4dc-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd4dc-140">xs:string</span></span>|<span data-ttu-id="fd4dc-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="fd4dc-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="fd4dc-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fd4dc-142">AppDomain</span></span>|<span data-ttu-id="fd4dc-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd4dc-143">xs:string</span></span>|<span data-ttu-id="fd4dc-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fd4dc-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
