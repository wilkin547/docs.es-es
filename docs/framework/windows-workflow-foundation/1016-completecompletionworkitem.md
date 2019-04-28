---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925091"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="ecb5e-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="ecb5e-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ecb5e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ecb5e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecb5e-104">ID</span><span class="sxs-lookup"><span data-stu-id="ecb5e-104">ID</span></span>|<span data-ttu-id="ecb5e-105">1016</span><span class="sxs-lookup"><span data-stu-id="ecb5e-105">1016</span></span>|  
|<span data-ttu-id="ecb5e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ecb5e-106">Keywords</span></span>|<span data-ttu-id="ecb5e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ecb5e-107">WFRuntime</span></span>|  
|<span data-ttu-id="ecb5e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ecb5e-108">Level</span></span>|<span data-ttu-id="ecb5e-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="ecb5e-109">Verbose</span></span>|  
|<span data-ttu-id="ecb5e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ecb5e-110">Channel</span></span>|<span data-ttu-id="ecb5e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ecb5e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ecb5e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecb5e-112">Description</span></span>  
 <span data-ttu-id="ecb5e-113">Indica que se ha completado un CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="ecb5e-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ecb5e-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="ecb5e-114">Message</span></span>  
 <span data-ttu-id="ecb5e-115">Un CompletionWorkItem se ha completado para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="ecb5e-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="ecb5e-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="ecb5e-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ecb5e-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="ecb5e-117">Details</span></span>  
  
|<span data-ttu-id="ecb5e-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ecb5e-118">Data Item Name</span></span>|<span data-ttu-id="ecb5e-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ecb5e-119">Data Item Type</span></span>|<span data-ttu-id="ecb5e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecb5e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ecb5e-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="ecb5e-121">ParentActivity</span></span>|<span data-ttu-id="ecb5e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ecb5e-122">xs:string</span></span>|<span data-ttu-id="ecb5e-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="ecb5e-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="ecb5e-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="ecb5e-124">ParentDisplayName</span></span>|<span data-ttu-id="ecb5e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ecb5e-125">xs:string</span></span>|<span data-ttu-id="ecb5e-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="ecb5e-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="ecb5e-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="ecb5e-127">ParentInstanceId</span></span>|<span data-ttu-id="ecb5e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ecb5e-128">xs:string</span></span>|<span data-ttu-id="ecb5e-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="ecb5e-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="ecb5e-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="ecb5e-130">CompletedActivity</span></span>|<span data-ttu-id="ecb5e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="ecb5e-131">xs:string</span></span>|<span data-ttu-id="ecb5e-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="ecb5e-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="ecb5e-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ecb5e-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="ecb5e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="ecb5e-134">xs:string</span></span>|<span data-ttu-id="ecb5e-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="ecb5e-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="ecb5e-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ecb5e-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="ecb5e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="ecb5e-137">xs:string</span></span>|<span data-ttu-id="ecb5e-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="ecb5e-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="ecb5e-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ecb5e-139">AppDomain</span></span>|<span data-ttu-id="ecb5e-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="ecb5e-140">xs:string</span></span>|<span data-ttu-id="ecb5e-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ecb5e-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
