---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6a2d4c866ec7d43e8ae40b5616a97c3b7adf1843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032271"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="fd790-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="fd790-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fd790-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fd790-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd790-104">ID</span><span class="sxs-lookup"><span data-stu-id="fd790-104">ID</span></span>|<span data-ttu-id="fd790-105">1015</span><span class="sxs-lookup"><span data-stu-id="fd790-105">1015</span></span>|  
|<span data-ttu-id="fd790-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="fd790-106">Keywords</span></span>|<span data-ttu-id="fd790-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fd790-107">WFRuntime</span></span>|  
|<span data-ttu-id="fd790-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="fd790-108">Level</span></span>|<span data-ttu-id="fd790-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="fd790-109">Verbose</span></span>|  
|<span data-ttu-id="fd790-110">Canal</span><span class="sxs-lookup"><span data-stu-id="fd790-110">Channel</span></span>|<span data-ttu-id="fd790-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fd790-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fd790-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd790-112">Description</span></span>  
 <span data-ttu-id="fd790-113">Indica que un CompletionWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="fd790-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fd790-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="fd790-114">Message</span></span>  
 <span data-ttu-id="fd790-115">Iniciar la ejecución de un CompletionWorkItem para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="fd790-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="fd790-116">Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="fd790-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fd790-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="fd790-117">Details</span></span>  
  
|<span data-ttu-id="fd790-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fd790-118">Data Item Name</span></span>|<span data-ttu-id="fd790-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fd790-119">Data Item Type</span></span>|<span data-ttu-id="fd790-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd790-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fd790-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="fd790-121">ParentActivity</span></span>|<span data-ttu-id="fd790-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd790-122">xs:string</span></span>|<span data-ttu-id="fd790-123">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="fd790-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="fd790-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="fd790-124">ParentDisplayName</span></span>|<span data-ttu-id="fd790-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd790-125">xs:string</span></span>|<span data-ttu-id="fd790-126">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="fd790-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="fd790-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="fd790-127">ParentInstanceId</span></span>|<span data-ttu-id="fd790-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd790-128">xs:string</span></span>|<span data-ttu-id="fd790-129">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="fd790-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="fd790-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="fd790-130">CompletedActivity</span></span>|<span data-ttu-id="fd790-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd790-131">xs:string</span></span>|<span data-ttu-id="fd790-132">El nombre del tipo de la actividad que se completó.</span><span class="sxs-lookup"><span data-stu-id="fd790-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="fd790-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="fd790-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="fd790-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd790-134">xs:string</span></span>|<span data-ttu-id="fd790-135">Nombre para mostrar de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="fd790-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="fd790-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="fd790-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="fd790-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd790-137">xs:string</span></span>|<span data-ttu-id="fd790-138">Identificador de instancia de la actividad que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="fd790-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="fd790-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fd790-139">AppDomain</span></span>|<span data-ttu-id="fd790-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd790-140">xs:string</span></span>|<span data-ttu-id="fd790-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fd790-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
