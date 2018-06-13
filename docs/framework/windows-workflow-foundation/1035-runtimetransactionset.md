---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510039"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="0f578-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="0f578-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="0f578-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0f578-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f578-104">Id.</span><span class="sxs-lookup"><span data-stu-id="0f578-104">ID</span></span>|<span data-ttu-id="0f578-105">1035</span><span class="sxs-lookup"><span data-stu-id="0f578-105">1035</span></span>|  
|<span data-ttu-id="0f578-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0f578-106">Keywords</span></span>|<span data-ttu-id="0f578-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0f578-107">WFRuntime</span></span>|  
|<span data-ttu-id="0f578-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="0f578-108">Level</span></span>|<span data-ttu-id="0f578-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="0f578-109">Verbose</span></span>|  
|<span data-ttu-id="0f578-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0f578-110">Channel</span></span>|<span data-ttu-id="0f578-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0f578-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0f578-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f578-112">Description</span></span>  
 <span data-ttu-id="0f578-113">Indica que una actividad ha establecido la transacción en tiempo ejecución.</span><span class="sxs-lookup"><span data-stu-id="0f578-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0f578-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0f578-114">Message</span></span>  
 <span data-ttu-id="0f578-115">Se ha establecido la transacción en tiempo de ejecución por la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="0f578-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="0f578-116">Ejecución aislada a la actividad '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="0f578-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0f578-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="0f578-117">Details</span></span>  
  
|<span data-ttu-id="0f578-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0f578-118">Data Item Name</span></span>|<span data-ttu-id="0f578-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0f578-119">Data Item Type</span></span>|<span data-ttu-id="0f578-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f578-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0f578-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="0f578-121">Activity</span></span>|<span data-ttu-id="0f578-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f578-122">xs:string</span></span>|<span data-ttu-id="0f578-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0f578-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="0f578-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0f578-124">DisplayName</span></span>|<span data-ttu-id="0f578-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f578-125">xs:string</span></span>|<span data-ttu-id="0f578-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0f578-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="0f578-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0f578-127">InstanceId</span></span>|<span data-ttu-id="0f578-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f578-128">xs:string</span></span>|<span data-ttu-id="0f578-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0f578-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0f578-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="0f578-130">IsolatedActivity</span></span>|<span data-ttu-id="0f578-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f578-131">xs:string</span></span>|<span data-ttu-id="0f578-132">El nombre de tipo para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="0f578-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="0f578-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0f578-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="0f578-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f578-134">xs:string</span></span>|<span data-ttu-id="0f578-135">El nombre para mostrar de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="0f578-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="0f578-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0f578-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="0f578-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f578-137">xs:string</span></span>|<span data-ttu-id="0f578-138">El identificador de la instancia de la actividad en la que la transacción está aislada.</span><span class="sxs-lookup"><span data-stu-id="0f578-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="0f578-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0f578-139">AppDomain</span></span>|<span data-ttu-id="0f578-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f578-140">xs:string</span></span>|<span data-ttu-id="0f578-141">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0f578-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
