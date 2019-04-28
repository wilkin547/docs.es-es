---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924662"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="888f3-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="888f3-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="888f3-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="888f3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="888f3-104">ID</span><span class="sxs-lookup"><span data-stu-id="888f3-104">ID</span></span>|<span data-ttu-id="888f3-105">1009</span><span class="sxs-lookup"><span data-stu-id="888f3-105">1009</span></span>|  
|<span data-ttu-id="888f3-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="888f3-106">Keywords</span></span>|<span data-ttu-id="888f3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="888f3-107">WFRuntime</span></span>|  
|<span data-ttu-id="888f3-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="888f3-108">Level</span></span>|<span data-ttu-id="888f3-109">Información</span><span class="sxs-lookup"><span data-stu-id="888f3-109">Information</span></span>|  
|<span data-ttu-id="888f3-110">Canal</span><span class="sxs-lookup"><span data-stu-id="888f3-110">Channel</span></span>|<span data-ttu-id="888f3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="888f3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="888f3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="888f3-112">Description</span></span>  
 <span data-ttu-id="888f3-113">Indica que una actividad se está programando para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="888f3-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="888f3-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="888f3-114">Message</span></span>  
 <span data-ttu-id="888f3-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="888f3-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="888f3-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="888f3-116">Details</span></span>  
  
|<span data-ttu-id="888f3-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="888f3-117">Data Item Name</span></span>|<span data-ttu-id="888f3-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="888f3-118">Data Item Type</span></span>|<span data-ttu-id="888f3-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="888f3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="888f3-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="888f3-120">ParentActivity</span></span>|<span data-ttu-id="888f3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="888f3-121">xs:string</span></span>|<span data-ttu-id="888f3-122">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="888f3-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="888f3-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="888f3-123">ParentDisplayName</span></span>|<span data-ttu-id="888f3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="888f3-124">xs:string</span></span>|<span data-ttu-id="888f3-125">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="888f3-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="888f3-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="888f3-126">ParentInstanceId</span></span>|<span data-ttu-id="888f3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="888f3-127">xs:string</span></span>|<span data-ttu-id="888f3-128">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="888f3-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="888f3-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="888f3-129">ChildActivity</span></span>|<span data-ttu-id="888f3-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="888f3-130">xs:string</span></span>|<span data-ttu-id="888f3-131">Nombre del tipo de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="888f3-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="888f3-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="888f3-132">ChildDisplayName</span></span>|<span data-ttu-id="888f3-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="888f3-133">xs:string</span></span>|<span data-ttu-id="888f3-134">El nombre para mostrar de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="888f3-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="888f3-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="888f3-135">ChildInstanceId</span></span>|<span data-ttu-id="888f3-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="888f3-136">xs:string</span></span>|<span data-ttu-id="888f3-137">Identificador de instancia de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="888f3-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="888f3-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="888f3-138">AppDomain</span></span>|<span data-ttu-id="888f3-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="888f3-139">xs:string</span></span>|<span data-ttu-id="888f3-140">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="888f3-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
