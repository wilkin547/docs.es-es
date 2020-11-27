---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: b8bf8431c4e2b82c6aac95820eb45de2a404e976
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294279"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="3e76b-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="3e76b-102">1035 - RuntimeTransactionSet</span></span>

## <a name="properties"></a><span data-ttu-id="3e76b-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3e76b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e76b-104">ID</span><span class="sxs-lookup"><span data-stu-id="3e76b-104">ID</span></span>|<span data-ttu-id="3e76b-105">1035</span><span class="sxs-lookup"><span data-stu-id="3e76b-105">1035</span></span>|  
|<span data-ttu-id="3e76b-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3e76b-106">Keywords</span></span>|<span data-ttu-id="3e76b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3e76b-107">WFRuntime</span></span>|  
|<span data-ttu-id="3e76b-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="3e76b-108">Level</span></span>|<span data-ttu-id="3e76b-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="3e76b-109">Verbose</span></span>|  
|<span data-ttu-id="3e76b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3e76b-110">Channel</span></span>|<span data-ttu-id="3e76b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3e76b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3e76b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e76b-112">Description</span></span>  

 <span data-ttu-id="3e76b-113">Indica que una actividad ha establecido la transacción en tiempo ejecución.</span><span class="sxs-lookup"><span data-stu-id="3e76b-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3e76b-114">Message</span><span class="sxs-lookup"><span data-stu-id="3e76b-114">Message</span></span>  

 <span data-ttu-id="3e76b-115">La actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 ' estableció la transacción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3e76b-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="3e76b-116">Ejecución aislada de la actividad ' %4 ', DisplayName: ' %5 ', InstanceId: ' %6 '.</span><span class="sxs-lookup"><span data-stu-id="3e76b-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3e76b-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="3e76b-117">Details</span></span>  
  
|<span data-ttu-id="3e76b-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3e76b-118">Data Item Name</span></span>|<span data-ttu-id="3e76b-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3e76b-119">Data Item Type</span></span>|<span data-ttu-id="3e76b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e76b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3e76b-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="3e76b-121">Activity</span></span>|<span data-ttu-id="3e76b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e76b-122">xs:string</span></span>|<span data-ttu-id="3e76b-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3e76b-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="3e76b-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3e76b-124">DisplayName</span></span>|<span data-ttu-id="3e76b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e76b-125">xs:string</span></span>|<span data-ttu-id="3e76b-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3e76b-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="3e76b-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3e76b-127">InstanceId</span></span>|<span data-ttu-id="3e76b-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e76b-128">xs:string</span></span>|<span data-ttu-id="3e76b-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3e76b-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3e76b-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="3e76b-130">IsolatedActivity</span></span>|<span data-ttu-id="3e76b-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e76b-131">xs:string</span></span>|<span data-ttu-id="3e76b-132">El nombre de tipo para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="3e76b-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="3e76b-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="3e76b-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="3e76b-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e76b-134">xs:string</span></span>|<span data-ttu-id="3e76b-135">El nombre para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="3e76b-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="3e76b-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="3e76b-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="3e76b-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e76b-137">xs:string</span></span>|<span data-ttu-id="3e76b-138">El identificador de la instancia de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="3e76b-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="3e76b-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3e76b-139">AppDomain</span></span>|<span data-ttu-id="3e76b-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e76b-140">xs:string</span></span>|<span data-ttu-id="3e76b-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3e76b-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
