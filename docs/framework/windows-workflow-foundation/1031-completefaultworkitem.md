---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: cdcbe516fc8ba7440b3d109a5e5cadc105ecee9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008803"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="e1e23-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="e1e23-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="e1e23-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e1e23-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1e23-104">ID</span><span class="sxs-lookup"><span data-stu-id="e1e23-104">ID</span></span>|<span data-ttu-id="e1e23-105">1031</span><span class="sxs-lookup"><span data-stu-id="e1e23-105">1031</span></span>|  
|<span data-ttu-id="e1e23-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e1e23-106">Keywords</span></span>|<span data-ttu-id="e1e23-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e1e23-107">WFRuntime</span></span>|  
|<span data-ttu-id="e1e23-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="e1e23-108">Level</span></span>|<span data-ttu-id="e1e23-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="e1e23-109">Verbose</span></span>|  
|<span data-ttu-id="e1e23-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e1e23-110">Channel</span></span>|<span data-ttu-id="e1e23-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e1e23-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e1e23-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1e23-112">Description</span></span>  
 <span data-ttu-id="e1e23-113">Indica que se ha completado un FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="e1e23-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e1e23-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="e1e23-114">Message</span></span>  
 <span data-ttu-id="e1e23-115">Un FaultWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="e1e23-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="e1e23-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="e1e23-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e1e23-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="e1e23-117">Details</span></span>  
  
|<span data-ttu-id="e1e23-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e1e23-118">Data Item Name</span></span>|<span data-ttu-id="e1e23-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e1e23-119">Data Item Type</span></span>|<span data-ttu-id="e1e23-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1e23-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e1e23-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="e1e23-121">FaultActivity</span></span>|<span data-ttu-id="e1e23-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1e23-122">xs:string</span></span>|<span data-ttu-id="e1e23-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="e1e23-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="e1e23-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="e1e23-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="e1e23-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1e23-125">xs:string</span></span>|<span data-ttu-id="e1e23-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="e1e23-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="e1e23-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="e1e23-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="e1e23-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1e23-128">xs:string</span></span>|<span data-ttu-id="e1e23-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="e1e23-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="e1e23-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="e1e23-130">ExceptionActivity</span></span>|<span data-ttu-id="e1e23-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1e23-131">xs:string</span></span>|<span data-ttu-id="e1e23-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="e1e23-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e1e23-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="e1e23-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="e1e23-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1e23-134">xs:string</span></span>|<span data-ttu-id="e1e23-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="e1e23-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e1e23-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="e1e23-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="e1e23-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1e23-137">xs:string</span></span>|<span data-ttu-id="e1e23-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="e1e23-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e1e23-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="e1e23-139">Exception</span></span>|<span data-ttu-id="e1e23-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1e23-140">xs:string</span></span>|<span data-ttu-id="e1e23-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="e1e23-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="e1e23-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e1e23-142">AppDomain</span></span>|<span data-ttu-id="e1e23-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1e23-143">xs:string</span></span>|<span data-ttu-id="e1e23-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e1e23-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
