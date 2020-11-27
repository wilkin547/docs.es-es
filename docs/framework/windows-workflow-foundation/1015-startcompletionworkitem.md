---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: c0d8572f192a8faa22327fd671cd9ea49c5054ca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275549"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="f5aff-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="f5aff-102">1015 - StartCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="f5aff-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f5aff-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5aff-104">ID</span><span class="sxs-lookup"><span data-stu-id="f5aff-104">ID</span></span>|<span data-ttu-id="f5aff-105">1015</span><span class="sxs-lookup"><span data-stu-id="f5aff-105">1015</span></span>|  
|<span data-ttu-id="f5aff-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f5aff-106">Keywords</span></span>|<span data-ttu-id="f5aff-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f5aff-107">WFRuntime</span></span>|  
|<span data-ttu-id="f5aff-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f5aff-108">Level</span></span>|<span data-ttu-id="f5aff-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="f5aff-109">Verbose</span></span>|  
|<span data-ttu-id="f5aff-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f5aff-110">Channel</span></span>|<span data-ttu-id="f5aff-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f5aff-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f5aff-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5aff-112">Description</span></span>  

 <span data-ttu-id="f5aff-113">Indica que un CompletionWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="f5aff-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f5aff-114">Message</span><span class="sxs-lookup"><span data-stu-id="f5aff-114">Message</span></span>  

 <span data-ttu-id="f5aff-115">Iniciar la ejecución de un CompletionWorkItem para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="f5aff-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="f5aff-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="f5aff-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f5aff-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="f5aff-117">Details</span></span>  
  
|<span data-ttu-id="f5aff-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f5aff-118">Data Item Name</span></span>|<span data-ttu-id="f5aff-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f5aff-119">Data Item Type</span></span>|<span data-ttu-id="f5aff-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5aff-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f5aff-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="f5aff-121">ParentActivity</span></span>|<span data-ttu-id="f5aff-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5aff-122">xs:string</span></span>|<span data-ttu-id="f5aff-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="f5aff-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="f5aff-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="f5aff-124">ParentDisplayName</span></span>|<span data-ttu-id="f5aff-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5aff-125">xs:string</span></span>|<span data-ttu-id="f5aff-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="f5aff-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="f5aff-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="f5aff-127">ParentInstanceId</span></span>|<span data-ttu-id="f5aff-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5aff-128">xs:string</span></span>|<span data-ttu-id="f5aff-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="f5aff-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="f5aff-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="f5aff-130">CompletedActivity</span></span>|<span data-ttu-id="f5aff-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5aff-131">xs:string</span></span>|<span data-ttu-id="f5aff-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="f5aff-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="f5aff-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f5aff-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="f5aff-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5aff-134">xs:string</span></span>|<span data-ttu-id="f5aff-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="f5aff-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="f5aff-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f5aff-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="f5aff-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5aff-137">xs:string</span></span>|<span data-ttu-id="f5aff-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="f5aff-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="f5aff-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f5aff-139">AppDomain</span></span>|<span data-ttu-id="f5aff-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5aff-140">xs:string</span></span>|<span data-ttu-id="f5aff-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f5aff-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
