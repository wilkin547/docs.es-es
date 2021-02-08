---
description: 'Más información acerca de: 1015-StartCompletionWorkItem'
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6c79a02b144aa1176eb1cb334c8430c8f0babc3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792926"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="b7e0f-103">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="b7e0f-103">1015 - StartCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="b7e0f-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b7e0f-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7e0f-105">Id.</span><span class="sxs-lookup"><span data-stu-id="b7e0f-105">ID</span></span>|<span data-ttu-id="b7e0f-106">1015</span><span class="sxs-lookup"><span data-stu-id="b7e0f-106">1015</span></span>|  
|<span data-ttu-id="b7e0f-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b7e0f-107">Keywords</span></span>|<span data-ttu-id="b7e0f-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b7e0f-108">WFRuntime</span></span>|  
|<span data-ttu-id="b7e0f-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="b7e0f-109">Level</span></span>|<span data-ttu-id="b7e0f-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="b7e0f-110">Verbose</span></span>|  
|<span data-ttu-id="b7e0f-111">Canal</span><span class="sxs-lookup"><span data-stu-id="b7e0f-111">Channel</span></span>|<span data-ttu-id="b7e0f-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b7e0f-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b7e0f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7e0f-113">Description</span></span>  

 <span data-ttu-id="b7e0f-114">Indica que un CompletionWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7e0f-114">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b7e0f-115">Message</span><span class="sxs-lookup"><span data-stu-id="b7e0f-115">Message</span></span>  

 <span data-ttu-id="b7e0f-116">Iniciar la ejecución de un CompletionWorkItem para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="b7e0f-116">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="b7e0f-117">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="b7e0f-117">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b7e0f-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="b7e0f-118">Details</span></span>  
  
|<span data-ttu-id="b7e0f-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b7e0f-119">Data Item Name</span></span>|<span data-ttu-id="b7e0f-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b7e0f-120">Data Item Type</span></span>|<span data-ttu-id="b7e0f-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7e0f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b7e0f-122">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="b7e0f-122">ParentActivity</span></span>|<span data-ttu-id="b7e0f-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7e0f-123">xs:string</span></span>|<span data-ttu-id="b7e0f-124">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="b7e0f-124">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="b7e0f-125">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="b7e0f-125">ParentDisplayName</span></span>|<span data-ttu-id="b7e0f-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7e0f-126">xs:string</span></span>|<span data-ttu-id="b7e0f-127">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="b7e0f-127">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="b7e0f-128">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="b7e0f-128">ParentInstanceId</span></span>|<span data-ttu-id="b7e0f-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7e0f-129">xs:string</span></span>|<span data-ttu-id="b7e0f-130">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="b7e0f-130">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="b7e0f-131">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="b7e0f-131">CompletedActivity</span></span>|<span data-ttu-id="b7e0f-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7e0f-132">xs:string</span></span>|<span data-ttu-id="b7e0f-133">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="b7e0f-133">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="b7e0f-134">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b7e0f-134">CompletedActivityDisplayName</span></span>|<span data-ttu-id="b7e0f-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7e0f-135">xs:string</span></span>|<span data-ttu-id="b7e0f-136">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="b7e0f-136">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="b7e0f-137">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b7e0f-137">CompletedActivityInstanceId</span></span>|<span data-ttu-id="b7e0f-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7e0f-138">xs:string</span></span>|<span data-ttu-id="b7e0f-139">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="b7e0f-139">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="b7e0f-140">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b7e0f-140">AppDomain</span></span>|<span data-ttu-id="b7e0f-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7e0f-141">xs:string</span></span>|<span data-ttu-id="b7e0f-142">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b7e0f-142">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
