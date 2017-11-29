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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7457b65f81e9e26b9de6055df474a83ce4264846
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="f5a80-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="f5a80-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f5a80-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f5a80-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5a80-104">Id.</span><span class="sxs-lookup"><span data-stu-id="f5a80-104">ID</span></span>|<span data-ttu-id="f5a80-105">1015</span><span class="sxs-lookup"><span data-stu-id="f5a80-105">1015</span></span>|  
|<span data-ttu-id="f5a80-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f5a80-106">Keywords</span></span>|<span data-ttu-id="f5a80-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f5a80-107">WFRuntime</span></span>|  
|<span data-ttu-id="f5a80-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f5a80-108">Level</span></span>|<span data-ttu-id="f5a80-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="f5a80-109">Verbose</span></span>|  
|<span data-ttu-id="f5a80-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f5a80-110">Channel</span></span>|<span data-ttu-id="f5a80-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f5a80-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f5a80-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5a80-112">Description</span></span>  
 <span data-ttu-id="f5a80-113">Indica que un CompletionWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="f5a80-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f5a80-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="f5a80-114">Message</span></span>  
 <span data-ttu-id="f5a80-115">Iniciar la ejecución de un CompletionWorkItem para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="f5a80-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="f5a80-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="f5a80-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f5a80-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="f5a80-117">Details</span></span>  
  
|<span data-ttu-id="f5a80-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f5a80-118">Data Item Name</span></span>|<span data-ttu-id="f5a80-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f5a80-119">Data Item Type</span></span>|<span data-ttu-id="f5a80-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5a80-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f5a80-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="f5a80-121">ParentActivity</span></span>|<span data-ttu-id="f5a80-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5a80-122">xs:string</span></span>|<span data-ttu-id="f5a80-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="f5a80-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="f5a80-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="f5a80-124">ParentDisplayName</span></span>|<span data-ttu-id="f5a80-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5a80-125">xs:string</span></span>|<span data-ttu-id="f5a80-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="f5a80-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="f5a80-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="f5a80-127">ParentInstanceId</span></span>|<span data-ttu-id="f5a80-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5a80-128">xs:string</span></span>|<span data-ttu-id="f5a80-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="f5a80-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="f5a80-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="f5a80-130">CompletedActivity</span></span>|<span data-ttu-id="f5a80-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5a80-131">xs:string</span></span>|<span data-ttu-id="f5a80-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="f5a80-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="f5a80-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f5a80-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="f5a80-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5a80-134">xs:string</span></span>|<span data-ttu-id="f5a80-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="f5a80-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="f5a80-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f5a80-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="f5a80-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5a80-137">xs:string</span></span>|<span data-ttu-id="f5a80-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="f5a80-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="f5a80-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f5a80-139">AppDomain</span></span>|<span data-ttu-id="f5a80-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5a80-140">xs:string</span></span>|<span data-ttu-id="f5a80-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f5a80-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
