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
ms.openlocfilehash: c639de96bd72670b2641707e7283be2642801dbe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="9db9c-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="9db9c-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9db9c-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9db9c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9db9c-104">Id.</span><span class="sxs-lookup"><span data-stu-id="9db9c-104">ID</span></span>|<span data-ttu-id="9db9c-105">1030</span><span class="sxs-lookup"><span data-stu-id="9db9c-105">1030</span></span>|  
|<span data-ttu-id="9db9c-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9db9c-106">Keywords</span></span>|<span data-ttu-id="9db9c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9db9c-107">WFRuntime</span></span>|  
|<span data-ttu-id="9db9c-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="9db9c-108">Level</span></span>|<span data-ttu-id="9db9c-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="9db9c-109">Verbose</span></span>|  
|<span data-ttu-id="9db9c-110">Canal</span><span class="sxs-lookup"><span data-stu-id="9db9c-110">Channel</span></span>|<span data-ttu-id="9db9c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9db9c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9db9c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9db9c-112">Description</span></span>  
 <span data-ttu-id="9db9c-113">Indica que un FaultWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="9db9c-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9db9c-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="9db9c-114">Message</span></span>  
 <span data-ttu-id="9db9c-115">Iniciando la ejecución de un FaultWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="9db9c-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="9db9c-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="9db9c-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9db9c-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="9db9c-117">Details</span></span>  
  
|<span data-ttu-id="9db9c-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9db9c-118">Data Item Name</span></span>|<span data-ttu-id="9db9c-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9db9c-119">Data Item Type</span></span>|<span data-ttu-id="9db9c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="9db9c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9db9c-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="9db9c-121">FaultActivity</span></span>|<span data-ttu-id="9db9c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="9db9c-122">xs:string</span></span>|<span data-ttu-id="9db9c-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="9db9c-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="9db9c-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="9db9c-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="9db9c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="9db9c-125">xs:string</span></span>|<span data-ttu-id="9db9c-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="9db9c-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="9db9c-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="9db9c-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="9db9c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="9db9c-128">xs:string</span></span>|<span data-ttu-id="9db9c-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="9db9c-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="9db9c-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="9db9c-130">ExceptionActivity</span></span>|<span data-ttu-id="9db9c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="9db9c-131">xs:string</span></span>|<span data-ttu-id="9db9c-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="9db9c-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="9db9c-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="9db9c-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="9db9c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="9db9c-134">xs:string</span></span>|<span data-ttu-id="9db9c-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="9db9c-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="9db9c-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="9db9c-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="9db9c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="9db9c-137">xs:string</span></span>|<span data-ttu-id="9db9c-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="9db9c-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="9db9c-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="9db9c-139">Exception</span></span>|<span data-ttu-id="9db9c-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="9db9c-140">xs:string</span></span>|<span data-ttu-id="9db9c-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="9db9c-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="9db9c-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9db9c-142">AppDomain</span></span>|<span data-ttu-id="9db9c-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="9db9c-143">xs:string</span></span>|<span data-ttu-id="9db9c-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9db9c-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
