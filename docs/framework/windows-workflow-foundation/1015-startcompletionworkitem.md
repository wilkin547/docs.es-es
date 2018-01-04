---
title: 1015 - StartCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc317157ed7658a52aa60c9b74942f9e84d47257
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="6e8a3-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="6e8a3-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="6e8a3-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6e8a3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6e8a3-104">Id.</span><span class="sxs-lookup"><span data-stu-id="6e8a3-104">ID</span></span>|<span data-ttu-id="6e8a3-105">1015</span><span class="sxs-lookup"><span data-stu-id="6e8a3-105">1015</span></span>|  
|<span data-ttu-id="6e8a3-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e8a3-106">Keywords</span></span>|<span data-ttu-id="6e8a3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6e8a3-107">WFRuntime</span></span>|  
|<span data-ttu-id="6e8a3-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="6e8a3-108">Level</span></span>|<span data-ttu-id="6e8a3-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="6e8a3-109">Verbose</span></span>|  
|<span data-ttu-id="6e8a3-110">Canal</span><span class="sxs-lookup"><span data-stu-id="6e8a3-110">Channel</span></span>|<span data-ttu-id="6e8a3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6e8a3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6e8a3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e8a3-112">Description</span></span>  
 <span data-ttu-id="6e8a3-113">Indica que un CompletionWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="6e8a3-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6e8a3-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="6e8a3-114">Message</span></span>  
 <span data-ttu-id="6e8a3-115">Iniciar la ejecución de un CompletionWorkItem para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="6e8a3-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="6e8a3-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="6e8a3-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6e8a3-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="6e8a3-117">Details</span></span>  
  
|<span data-ttu-id="6e8a3-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6e8a3-118">Data Item Name</span></span>|<span data-ttu-id="6e8a3-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6e8a3-119">Data Item Type</span></span>|<span data-ttu-id="6e8a3-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e8a3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6e8a3-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="6e8a3-121">ParentActivity</span></span>|<span data-ttu-id="6e8a3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6e8a3-122">xs:string</span></span>|<span data-ttu-id="6e8a3-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="6e8a3-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="6e8a3-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="6e8a3-124">ParentDisplayName</span></span>|<span data-ttu-id="6e8a3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6e8a3-125">xs:string</span></span>|<span data-ttu-id="6e8a3-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="6e8a3-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="6e8a3-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="6e8a3-127">ParentInstanceId</span></span>|<span data-ttu-id="6e8a3-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="6e8a3-128">xs:string</span></span>|<span data-ttu-id="6e8a3-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="6e8a3-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="6e8a3-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="6e8a3-130">CompletedActivity</span></span>|<span data-ttu-id="6e8a3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="6e8a3-131">xs:string</span></span>|<span data-ttu-id="6e8a3-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="6e8a3-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="6e8a3-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="6e8a3-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="6e8a3-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="6e8a3-134">xs:string</span></span>|<span data-ttu-id="6e8a3-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="6e8a3-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="6e8a3-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="6e8a3-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="6e8a3-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="6e8a3-137">xs:string</span></span>|<span data-ttu-id="6e8a3-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="6e8a3-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="6e8a3-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6e8a3-139">AppDomain</span></span>|<span data-ttu-id="6e8a3-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="6e8a3-140">xs:string</span></span>|<span data-ttu-id="6e8a3-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6e8a3-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
