---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6a2d4c866ec7d43e8ae40b5616a97c3b7adf1843
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509639"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="a2128-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="a2128-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a2128-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a2128-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2128-104">Id.</span><span class="sxs-lookup"><span data-stu-id="a2128-104">ID</span></span>|<span data-ttu-id="a2128-105">1015</span><span class="sxs-lookup"><span data-stu-id="a2128-105">1015</span></span>|  
|<span data-ttu-id="a2128-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a2128-106">Keywords</span></span>|<span data-ttu-id="a2128-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a2128-107">WFRuntime</span></span>|  
|<span data-ttu-id="a2128-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a2128-108">Level</span></span>|<span data-ttu-id="a2128-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="a2128-109">Verbose</span></span>|  
|<span data-ttu-id="a2128-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a2128-110">Channel</span></span>|<span data-ttu-id="a2128-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a2128-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a2128-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2128-112">Description</span></span>  
 <span data-ttu-id="a2128-113">Indica que un CompletionWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a2128-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a2128-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a2128-114">Message</span></span>  
 <span data-ttu-id="a2128-115">Iniciar la ejecución de un CompletionWorkItem para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="a2128-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="a2128-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="a2128-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a2128-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="a2128-117">Details</span></span>  
  
|<span data-ttu-id="a2128-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a2128-118">Data Item Name</span></span>|<span data-ttu-id="a2128-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a2128-119">Data Item Type</span></span>|<span data-ttu-id="a2128-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2128-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a2128-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="a2128-121">ParentActivity</span></span>|<span data-ttu-id="a2128-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2128-122">xs:string</span></span>|<span data-ttu-id="a2128-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="a2128-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="a2128-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="a2128-124">ParentDisplayName</span></span>|<span data-ttu-id="a2128-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2128-125">xs:string</span></span>|<span data-ttu-id="a2128-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="a2128-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="a2128-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="a2128-127">ParentInstanceId</span></span>|<span data-ttu-id="a2128-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2128-128">xs:string</span></span>|<span data-ttu-id="a2128-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="a2128-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="a2128-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="a2128-130">CompletedActivity</span></span>|<span data-ttu-id="a2128-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2128-131">xs:string</span></span>|<span data-ttu-id="a2128-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="a2128-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="a2128-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="a2128-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="a2128-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2128-134">xs:string</span></span>|<span data-ttu-id="a2128-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="a2128-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="a2128-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="a2128-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="a2128-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2128-137">xs:string</span></span>|<span data-ttu-id="a2128-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="a2128-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="a2128-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a2128-139">AppDomain</span></span>|<span data-ttu-id="a2128-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2128-140">xs:string</span></span>|<span data-ttu-id="a2128-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a2128-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
