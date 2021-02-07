---
description: 'Más información acerca de: 1035-RuntimeTransactionSet'
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 513ba49962a8f02ab47b8e5b762949cd09154a3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667907"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="7afe9-103">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="7afe9-103">1035 - RuntimeTransactionSet</span></span>

## <a name="properties"></a><span data-ttu-id="7afe9-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7afe9-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7afe9-105">Id.</span><span class="sxs-lookup"><span data-stu-id="7afe9-105">ID</span></span>|<span data-ttu-id="7afe9-106">1035</span><span class="sxs-lookup"><span data-stu-id="7afe9-106">1035</span></span>|  
|<span data-ttu-id="7afe9-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="7afe9-107">Keywords</span></span>|<span data-ttu-id="7afe9-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7afe9-108">WFRuntime</span></span>|  
|<span data-ttu-id="7afe9-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="7afe9-109">Level</span></span>|<span data-ttu-id="7afe9-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="7afe9-110">Verbose</span></span>|  
|<span data-ttu-id="7afe9-111">Canal</span><span class="sxs-lookup"><span data-stu-id="7afe9-111">Channel</span></span>|<span data-ttu-id="7afe9-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7afe9-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7afe9-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7afe9-113">Description</span></span>  

 <span data-ttu-id="7afe9-114">Indica que una actividad ha establecido la transacción en tiempo ejecución.</span><span class="sxs-lookup"><span data-stu-id="7afe9-114">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7afe9-115">Message</span><span class="sxs-lookup"><span data-stu-id="7afe9-115">Message</span></span>  

 <span data-ttu-id="7afe9-116">La actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 ' estableció la transacción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7afe9-116">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="7afe9-117">Ejecución aislada de la actividad ' %4 ', DisplayName: ' %5 ', InstanceId: ' %6 '.</span><span class="sxs-lookup"><span data-stu-id="7afe9-117">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7afe9-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="7afe9-118">Details</span></span>  
  
|<span data-ttu-id="7afe9-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7afe9-119">Data Item Name</span></span>|<span data-ttu-id="7afe9-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7afe9-120">Data Item Type</span></span>|<span data-ttu-id="7afe9-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7afe9-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7afe9-122">Actividad</span><span class="sxs-lookup"><span data-stu-id="7afe9-122">Activity</span></span>|<span data-ttu-id="7afe9-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="7afe9-123">xs:string</span></span>|<span data-ttu-id="7afe9-124">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7afe9-124">The type name of the activity.</span></span>|  
|<span data-ttu-id="7afe9-125">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7afe9-125">DisplayName</span></span>|<span data-ttu-id="7afe9-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="7afe9-126">xs:string</span></span>|<span data-ttu-id="7afe9-127">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7afe9-127">The display name of the activity.</span></span>|  
|<span data-ttu-id="7afe9-128">InstanceId</span><span class="sxs-lookup"><span data-stu-id="7afe9-128">InstanceId</span></span>|<span data-ttu-id="7afe9-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="7afe9-129">xs:string</span></span>|<span data-ttu-id="7afe9-130">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7afe9-130">The instance id of the activity.</span></span>|  
|<span data-ttu-id="7afe9-131">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="7afe9-131">IsolatedActivity</span></span>|<span data-ttu-id="7afe9-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="7afe9-132">xs:string</span></span>|<span data-ttu-id="7afe9-133">El nombre de tipo para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="7afe9-133">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="7afe9-134">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="7afe9-134">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="7afe9-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="7afe9-135">xs:string</span></span>|<span data-ttu-id="7afe9-136">El nombre para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="7afe9-136">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="7afe9-137">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="7afe9-137">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="7afe9-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="7afe9-138">xs:string</span></span>|<span data-ttu-id="7afe9-139">El identificador de la instancia de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="7afe9-139">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="7afe9-140">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7afe9-140">AppDomain</span></span>|<span data-ttu-id="7afe9-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="7afe9-141">xs:string</span></span>|<span data-ttu-id="7afe9-142">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7afe9-142">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
