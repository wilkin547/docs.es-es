---
description: 'Más información acerca de: 1030-StartFaultWorkItem'
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 2d148277b2d593cfcf75e17662626f1f486e7c1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668102"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="2a339-103">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="2a339-103">1030 - StartFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="2a339-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2a339-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a339-105">Id.</span><span class="sxs-lookup"><span data-stu-id="2a339-105">ID</span></span>|<span data-ttu-id="2a339-106">1030</span><span class="sxs-lookup"><span data-stu-id="2a339-106">1030</span></span>|  
|<span data-ttu-id="2a339-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2a339-107">Keywords</span></span>|<span data-ttu-id="2a339-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2a339-108">WFRuntime</span></span>|  
|<span data-ttu-id="2a339-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a339-109">Level</span></span>|<span data-ttu-id="2a339-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="2a339-110">Verbose</span></span>|  
|<span data-ttu-id="2a339-111">Canal</span><span class="sxs-lookup"><span data-stu-id="2a339-111">Channel</span></span>|<span data-ttu-id="2a339-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2a339-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2a339-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a339-113">Description</span></span>  

 <span data-ttu-id="2a339-114">Indica que un FaultWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="2a339-114">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2a339-115">Message</span><span class="sxs-lookup"><span data-stu-id="2a339-115">Message</span></span>  

 <span data-ttu-id="2a339-116">Iniciando la ejecución de un FaultWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="2a339-116">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2a339-117">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="2a339-117">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2a339-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="2a339-118">Details</span></span>  
  
|<span data-ttu-id="2a339-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2a339-119">Data Item Name</span></span>|<span data-ttu-id="2a339-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2a339-120">Data Item Type</span></span>|<span data-ttu-id="2a339-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a339-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2a339-122">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="2a339-122">FaultActivity</span></span>|<span data-ttu-id="2a339-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a339-123">xs:string</span></span>|<span data-ttu-id="2a339-124">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="2a339-124">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="2a339-125">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2a339-125">FaultActivityDisplayName</span></span>|<span data-ttu-id="2a339-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a339-126">xs:string</span></span>|<span data-ttu-id="2a339-127">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="2a339-127">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="2a339-128">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2a339-128">FaultActivityInstanceId</span></span>|<span data-ttu-id="2a339-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a339-129">xs:string</span></span>|<span data-ttu-id="2a339-130">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="2a339-130">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="2a339-131">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="2a339-131">ExceptionActivity</span></span>|<span data-ttu-id="2a339-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a339-132">xs:string</span></span>|<span data-ttu-id="2a339-133">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="2a339-133">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2a339-134">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2a339-134">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="2a339-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a339-135">xs:string</span></span>|<span data-ttu-id="2a339-136">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="2a339-136">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2a339-137">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2a339-137">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="2a339-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a339-138">xs:string</span></span>|<span data-ttu-id="2a339-139">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="2a339-139">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2a339-140">Excepción</span><span class="sxs-lookup"><span data-stu-id="2a339-140">Exception</span></span>|<span data-ttu-id="2a339-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a339-141">xs:string</span></span>|<span data-ttu-id="2a339-142">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="2a339-142">The exception details for the exception</span></span>|  
|<span data-ttu-id="2a339-143">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2a339-143">AppDomain</span></span>|<span data-ttu-id="2a339-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a339-144">xs:string</span></span>|<span data-ttu-id="2a339-145">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2a339-145">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
