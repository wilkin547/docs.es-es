---
title: 1035 - RuntimeTransactionSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fcd6662c0f8899b6830dc8e06cee4f56b5ff906
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="0be5c-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="0be5c-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="0be5c-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0be5c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0be5c-104">Id.</span><span class="sxs-lookup"><span data-stu-id="0be5c-104">ID</span></span>|<span data-ttu-id="0be5c-105">1035</span><span class="sxs-lookup"><span data-stu-id="0be5c-105">1035</span></span>|  
|<span data-ttu-id="0be5c-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0be5c-106">Keywords</span></span>|<span data-ttu-id="0be5c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0be5c-107">WFRuntime</span></span>|  
|<span data-ttu-id="0be5c-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="0be5c-108">Level</span></span>|<span data-ttu-id="0be5c-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="0be5c-109">Verbose</span></span>|  
|<span data-ttu-id="0be5c-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0be5c-110">Channel</span></span>|<span data-ttu-id="0be5c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0be5c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0be5c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0be5c-112">Description</span></span>  
 <span data-ttu-id="0be5c-113">Indica que una actividad ha establecido la transacción en tiempo ejecución.</span><span class="sxs-lookup"><span data-stu-id="0be5c-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0be5c-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0be5c-114">Message</span></span>  
 <span data-ttu-id="0be5c-115">Se ha establecido la transacción en tiempo de ejecución por la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="0be5c-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="0be5c-116">Ejecución aislada a la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="0be5c-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0be5c-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="0be5c-117">Details</span></span>  
  
|<span data-ttu-id="0be5c-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0be5c-118">Data Item Name</span></span>|<span data-ttu-id="0be5c-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0be5c-119">Data Item Type</span></span>|<span data-ttu-id="0be5c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0be5c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0be5c-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="0be5c-121">Activity</span></span>|<span data-ttu-id="0be5c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5c-122">xs:string</span></span>|<span data-ttu-id="0be5c-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0be5c-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="0be5c-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0be5c-124">DisplayName</span></span>|<span data-ttu-id="0be5c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5c-125">xs:string</span></span>|<span data-ttu-id="0be5c-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0be5c-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="0be5c-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0be5c-127">InstanceId</span></span>|<span data-ttu-id="0be5c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5c-128">xs:string</span></span>|<span data-ttu-id="0be5c-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0be5c-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0be5c-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="0be5c-130">IsolatedActivity</span></span>|<span data-ttu-id="0be5c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5c-131">xs:string</span></span>|<span data-ttu-id="0be5c-132">El nombre de tipo para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="0be5c-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="0be5c-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0be5c-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="0be5c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5c-134">xs:string</span></span>|<span data-ttu-id="0be5c-135">El nombre para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="0be5c-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="0be5c-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0be5c-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="0be5c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5c-137">xs:string</span></span>|<span data-ttu-id="0be5c-138">El identificador de la instancia de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="0be5c-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="0be5c-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0be5c-139">AppDomain</span></span>|<span data-ttu-id="0be5c-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5c-140">xs:string</span></span>|<span data-ttu-id="0be5c-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0be5c-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
