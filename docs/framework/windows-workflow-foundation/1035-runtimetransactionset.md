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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3fcd93dbc30b20f7822a54babde8277e32d8335
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="412f0-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="412f0-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="412f0-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="412f0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="412f0-104">Id.</span><span class="sxs-lookup"><span data-stu-id="412f0-104">ID</span></span>|<span data-ttu-id="412f0-105">1035</span><span class="sxs-lookup"><span data-stu-id="412f0-105">1035</span></span>|  
|<span data-ttu-id="412f0-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="412f0-106">Keywords</span></span>|<span data-ttu-id="412f0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="412f0-107">WFRuntime</span></span>|  
|<span data-ttu-id="412f0-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="412f0-108">Level</span></span>|<span data-ttu-id="412f0-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="412f0-109">Verbose</span></span>|  
|<span data-ttu-id="412f0-110">Canal</span><span class="sxs-lookup"><span data-stu-id="412f0-110">Channel</span></span>|<span data-ttu-id="412f0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="412f0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="412f0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="412f0-112">Description</span></span>  
 <span data-ttu-id="412f0-113">Indica que una actividad ha establecido la transacción en tiempo ejecución.</span><span class="sxs-lookup"><span data-stu-id="412f0-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="412f0-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="412f0-114">Message</span></span>  
 <span data-ttu-id="412f0-115">Se ha establecido la transacción en tiempo de ejecución por la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="412f0-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="412f0-116">Ejecución aislada a la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="412f0-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="412f0-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="412f0-117">Details</span></span>  
  
|<span data-ttu-id="412f0-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="412f0-118">Data Item Name</span></span>|<span data-ttu-id="412f0-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="412f0-119">Data Item Type</span></span>|<span data-ttu-id="412f0-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="412f0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="412f0-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="412f0-121">Activity</span></span>|<span data-ttu-id="412f0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="412f0-122">xs:string</span></span>|<span data-ttu-id="412f0-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="412f0-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="412f0-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="412f0-124">DisplayName</span></span>|<span data-ttu-id="412f0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="412f0-125">xs:string</span></span>|<span data-ttu-id="412f0-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="412f0-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="412f0-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="412f0-127">InstanceId</span></span>|<span data-ttu-id="412f0-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="412f0-128">xs:string</span></span>|<span data-ttu-id="412f0-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="412f0-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="412f0-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="412f0-130">IsolatedActivity</span></span>|<span data-ttu-id="412f0-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="412f0-131">xs:string</span></span>|<span data-ttu-id="412f0-132">El nombre de tipo para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="412f0-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="412f0-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="412f0-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="412f0-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="412f0-134">xs:string</span></span>|<span data-ttu-id="412f0-135">El nombre para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="412f0-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="412f0-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="412f0-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="412f0-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="412f0-137">xs:string</span></span>|<span data-ttu-id="412f0-138">El identificador de la instancia de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="412f0-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="412f0-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="412f0-139">AppDomain</span></span>|<span data-ttu-id="412f0-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="412f0-140">xs:string</span></span>|<span data-ttu-id="412f0-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="412f0-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
