---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: f5beab91f7dd39a3f8ed3b76d6c0a1ddd9bd77c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509735"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="0ac1c-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="0ac1c-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0ac1c-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0ac1c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ac1c-104">Id.</span><span class="sxs-lookup"><span data-stu-id="0ac1c-104">ID</span></span>|<span data-ttu-id="0ac1c-105">1029</span><span class="sxs-lookup"><span data-stu-id="0ac1c-105">1029</span></span>|  
|<span data-ttu-id="0ac1c-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0ac1c-106">Keywords</span></span>|<span data-ttu-id="0ac1c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0ac1c-107">WFRuntime</span></span>|  
|<span data-ttu-id="0ac1c-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="0ac1c-108">Level</span></span>|<span data-ttu-id="0ac1c-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="0ac1c-109">Verbose</span></span>|  
|<span data-ttu-id="0ac1c-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0ac1c-110">Channel</span></span>|<span data-ttu-id="0ac1c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0ac1c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0ac1c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ac1c-112">Description</span></span>  
 <span data-ttu-id="0ac1c-113">Indica que se ha programado un FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="0ac1c-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0ac1c-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0ac1c-114">Message</span></span>  
 <span data-ttu-id="0ac1c-115">Un FaultWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="0ac1c-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="0ac1c-116">La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="0ac1c-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0ac1c-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="0ac1c-117">Details</span></span>  
  
|<span data-ttu-id="0ac1c-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0ac1c-118">Data Item Name</span></span>|<span data-ttu-id="0ac1c-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0ac1c-119">Data Item Type</span></span>|<span data-ttu-id="0ac1c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ac1c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0ac1c-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="0ac1c-121">FaultActivity</span></span>|<span data-ttu-id="0ac1c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ac1c-122">xs:string</span></span>|<span data-ttu-id="0ac1c-123">Nombre de tipo de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="0ac1c-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="0ac1c-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0ac1c-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="0ac1c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ac1c-125">xs:string</span></span>|<span data-ttu-id="0ac1c-126">Nombre para mostrar de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="0ac1c-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="0ac1c-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0ac1c-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="0ac1c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ac1c-128">xs:string</span></span>|<span data-ttu-id="0ac1c-129">Identificador de la actividad que generó el error.</span><span class="sxs-lookup"><span data-stu-id="0ac1c-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="0ac1c-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="0ac1c-130">ExceptionActivity</span></span>|<span data-ttu-id="0ac1c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ac1c-131">xs:string</span></span>|<span data-ttu-id="0ac1c-132">El nombre de tipo para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="0ac1c-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="0ac1c-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0ac1c-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="0ac1c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ac1c-134">xs:string</span></span>|<span data-ttu-id="0ac1c-135">El nombre para mostrar de la actividad que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="0ac1c-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="0ac1c-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0ac1c-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="0ac1c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ac1c-137">xs:string</span></span>|<span data-ttu-id="0ac1c-138">Identificador de instancia de la actividad que generó la excepción.</span><span class="sxs-lookup"><span data-stu-id="0ac1c-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="0ac1c-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="0ac1c-139">Exception</span></span>|<span data-ttu-id="0ac1c-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ac1c-140">xs:string</span></span>|<span data-ttu-id="0ac1c-141">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="0ac1c-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="0ac1c-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0ac1c-142">AppDomain</span></span>|<span data-ttu-id="0ac1c-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ac1c-143">xs:string</span></span>|<span data-ttu-id="0ac1c-144">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0ac1c-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
