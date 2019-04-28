---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924857"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="c44c3-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="c44c3-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="c44c3-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c44c3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c44c3-104">ID</span><span class="sxs-lookup"><span data-stu-id="c44c3-104">ID</span></span>|<span data-ttu-id="c44c3-105">1035</span><span class="sxs-lookup"><span data-stu-id="c44c3-105">1035</span></span>|  
|<span data-ttu-id="c44c3-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c44c3-106">Keywords</span></span>|<span data-ttu-id="c44c3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c44c3-107">WFRuntime</span></span>|  
|<span data-ttu-id="c44c3-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="c44c3-108">Level</span></span>|<span data-ttu-id="c44c3-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="c44c3-109">Verbose</span></span>|  
|<span data-ttu-id="c44c3-110">Canal</span><span class="sxs-lookup"><span data-stu-id="c44c3-110">Channel</span></span>|<span data-ttu-id="c44c3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c44c3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c44c3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c44c3-112">Description</span></span>  
 <span data-ttu-id="c44c3-113">Indica que una actividad ha establecido la transacción en tiempo ejecución.</span><span class="sxs-lookup"><span data-stu-id="c44c3-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c44c3-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="c44c3-114">Message</span></span>  
 <span data-ttu-id="c44c3-115">Se ha establecido la transacción en tiempo de ejecución mediante la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="c44c3-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c44c3-116">Ejecución aislada para la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="c44c3-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c44c3-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="c44c3-117">Details</span></span>  
  
|<span data-ttu-id="c44c3-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c44c3-118">Data Item Name</span></span>|<span data-ttu-id="c44c3-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c44c3-119">Data Item Type</span></span>|<span data-ttu-id="c44c3-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c44c3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c44c3-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="c44c3-121">Activity</span></span>|<span data-ttu-id="c44c3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c44c3-122">xs:string</span></span>|<span data-ttu-id="c44c3-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="c44c3-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="c44c3-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c44c3-124">DisplayName</span></span>|<span data-ttu-id="c44c3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c44c3-125">xs:string</span></span>|<span data-ttu-id="c44c3-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="c44c3-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="c44c3-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c44c3-127">InstanceId</span></span>|<span data-ttu-id="c44c3-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c44c3-128">xs:string</span></span>|<span data-ttu-id="c44c3-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="c44c3-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c44c3-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="c44c3-130">IsolatedActivity</span></span>|<span data-ttu-id="c44c3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c44c3-131">xs:string</span></span>|<span data-ttu-id="c44c3-132">El nombre de tipo para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="c44c3-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="c44c3-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c44c3-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="c44c3-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c44c3-134">xs:string</span></span>|<span data-ttu-id="c44c3-135">El nombre para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="c44c3-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="c44c3-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c44c3-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="c44c3-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c44c3-137">xs:string</span></span>|<span data-ttu-id="c44c3-138">El identificador de la instancia de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="c44c3-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="c44c3-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c44c3-139">AppDomain</span></span>|<span data-ttu-id="c44c3-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="c44c3-140">xs:string</span></span>|<span data-ttu-id="c44c3-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c44c3-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
