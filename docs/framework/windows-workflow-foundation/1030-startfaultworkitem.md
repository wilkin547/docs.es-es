---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509685"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="f7572-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="f7572-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f7572-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f7572-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f7572-104">Id.</span><span class="sxs-lookup"><span data-stu-id="f7572-104">ID</span></span>|<span data-ttu-id="f7572-105">1030</span><span class="sxs-lookup"><span data-stu-id="f7572-105">1030</span></span>|  
|<span data-ttu-id="f7572-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f7572-106">Keywords</span></span>|<span data-ttu-id="f7572-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f7572-107">WFRuntime</span></span>|  
|<span data-ttu-id="f7572-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f7572-108">Level</span></span>|<span data-ttu-id="f7572-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="f7572-109">Verbose</span></span>|  
|<span data-ttu-id="f7572-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f7572-110">Channel</span></span>|<span data-ttu-id="f7572-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f7572-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f7572-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7572-112">Description</span></span>  
 <span data-ttu-id="f7572-113">Indica que un FaultWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="f7572-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f7572-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="f7572-114">Message</span></span>  
 <span data-ttu-id="f7572-115">Iniciando la ejecución de un FaultWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="f7572-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="f7572-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="f7572-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f7572-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="f7572-117">Details</span></span>  
  
|<span data-ttu-id="f7572-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f7572-118">Data Item Name</span></span>|<span data-ttu-id="f7572-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f7572-119">Data Item Type</span></span>|<span data-ttu-id="f7572-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7572-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f7572-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="f7572-121">FaultActivity</span></span>|<span data-ttu-id="f7572-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7572-122">xs:string</span></span>|<span data-ttu-id="f7572-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="f7572-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="f7572-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f7572-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="f7572-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7572-125">xs:string</span></span>|<span data-ttu-id="f7572-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="f7572-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="f7572-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f7572-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="f7572-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7572-128">xs:string</span></span>|<span data-ttu-id="f7572-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="f7572-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="f7572-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="f7572-130">ExceptionActivity</span></span>|<span data-ttu-id="f7572-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7572-131">xs:string</span></span>|<span data-ttu-id="f7572-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="f7572-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f7572-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f7572-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="f7572-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7572-134">xs:string</span></span>|<span data-ttu-id="f7572-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="f7572-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f7572-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f7572-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="f7572-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7572-137">xs:string</span></span>|<span data-ttu-id="f7572-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="f7572-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f7572-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="f7572-139">Exception</span></span>|<span data-ttu-id="f7572-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7572-140">xs:string</span></span>|<span data-ttu-id="f7572-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="f7572-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="f7572-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f7572-142">AppDomain</span></span>|<span data-ttu-id="f7572-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7572-143">xs:string</span></span>|<span data-ttu-id="f7572-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f7572-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
