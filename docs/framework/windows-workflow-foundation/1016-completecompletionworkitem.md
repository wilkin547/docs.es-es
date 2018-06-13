---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510301"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="8242a-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="8242a-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8242a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8242a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8242a-104">Id.</span><span class="sxs-lookup"><span data-stu-id="8242a-104">ID</span></span>|<span data-ttu-id="8242a-105">1016</span><span class="sxs-lookup"><span data-stu-id="8242a-105">1016</span></span>|  
|<span data-ttu-id="8242a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8242a-106">Keywords</span></span>|<span data-ttu-id="8242a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8242a-107">WFRuntime</span></span>|  
|<span data-ttu-id="8242a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="8242a-108">Level</span></span>|<span data-ttu-id="8242a-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="8242a-109">Verbose</span></span>|  
|<span data-ttu-id="8242a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="8242a-110">Channel</span></span>|<span data-ttu-id="8242a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8242a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8242a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8242a-112">Description</span></span>  
 <span data-ttu-id="8242a-113">Indica que se ha completado un CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="8242a-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8242a-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="8242a-114">Message</span></span>  
 <span data-ttu-id="8242a-115">Un CompletionWorkItem se ha completado para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="8242a-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="8242a-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="8242a-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8242a-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="8242a-117">Details</span></span>  
  
|<span data-ttu-id="8242a-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8242a-118">Data Item Name</span></span>|<span data-ttu-id="8242a-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8242a-119">Data Item Type</span></span>|<span data-ttu-id="8242a-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="8242a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8242a-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="8242a-121">ParentActivity</span></span>|<span data-ttu-id="8242a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8242a-122">xs:string</span></span>|<span data-ttu-id="8242a-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="8242a-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="8242a-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="8242a-124">ParentDisplayName</span></span>|<span data-ttu-id="8242a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8242a-125">xs:string</span></span>|<span data-ttu-id="8242a-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="8242a-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="8242a-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="8242a-127">ParentInstanceId</span></span>|<span data-ttu-id="8242a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8242a-128">xs:string</span></span>|<span data-ttu-id="8242a-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="8242a-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="8242a-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="8242a-130">CompletedActivity</span></span>|<span data-ttu-id="8242a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8242a-131">xs:string</span></span>|<span data-ttu-id="8242a-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="8242a-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="8242a-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="8242a-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="8242a-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="8242a-134">xs:string</span></span>|<span data-ttu-id="8242a-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="8242a-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="8242a-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="8242a-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="8242a-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="8242a-137">xs:string</span></span>|<span data-ttu-id="8242a-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="8242a-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="8242a-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8242a-139">AppDomain</span></span>|<span data-ttu-id="8242a-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="8242a-140">xs:string</span></span>|<span data-ttu-id="8242a-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8242a-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
