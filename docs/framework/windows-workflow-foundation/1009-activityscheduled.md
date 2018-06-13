---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509977"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="d4298-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="d4298-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="d4298-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d4298-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4298-104">Id.</span><span class="sxs-lookup"><span data-stu-id="d4298-104">ID</span></span>|<span data-ttu-id="d4298-105">1009</span><span class="sxs-lookup"><span data-stu-id="d4298-105">1009</span></span>|  
|<span data-ttu-id="d4298-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d4298-106">Keywords</span></span>|<span data-ttu-id="d4298-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d4298-107">WFRuntime</span></span>|  
|<span data-ttu-id="d4298-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d4298-108">Level</span></span>|<span data-ttu-id="d4298-109">Información</span><span class="sxs-lookup"><span data-stu-id="d4298-109">Information</span></span>|  
|<span data-ttu-id="d4298-110">Canal</span><span class="sxs-lookup"><span data-stu-id="d4298-110">Channel</span></span>|<span data-ttu-id="d4298-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d4298-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d4298-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4298-112">Description</span></span>  
 <span data-ttu-id="d4298-113">Indica que una actividad se está programando para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="d4298-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d4298-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="d4298-114">Message</span></span>  
 <span data-ttu-id="d4298-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="d4298-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d4298-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="d4298-116">Details</span></span>  
  
|<span data-ttu-id="d4298-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d4298-117">Data Item Name</span></span>|<span data-ttu-id="d4298-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d4298-118">Data Item Type</span></span>|<span data-ttu-id="d4298-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4298-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d4298-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="d4298-120">ParentActivity</span></span>|<span data-ttu-id="d4298-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4298-121">xs:string</span></span>|<span data-ttu-id="d4298-122">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="d4298-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="d4298-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="d4298-123">ParentDisplayName</span></span>|<span data-ttu-id="d4298-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4298-124">xs:string</span></span>|<span data-ttu-id="d4298-125">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="d4298-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="d4298-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="d4298-126">ParentInstanceId</span></span>|<span data-ttu-id="d4298-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4298-127">xs:string</span></span>|<span data-ttu-id="d4298-128">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="d4298-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="d4298-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="d4298-129">ChildActivity</span></span>|<span data-ttu-id="d4298-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4298-130">xs:string</span></span>|<span data-ttu-id="d4298-131">Nombre del tipo de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="d4298-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="d4298-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="d4298-132">ChildDisplayName</span></span>|<span data-ttu-id="d4298-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4298-133">xs:string</span></span>|<span data-ttu-id="d4298-134">El nombre para mostrar de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="d4298-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="d4298-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="d4298-135">ChildInstanceId</span></span>|<span data-ttu-id="d4298-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4298-136">xs:string</span></span>|<span data-ttu-id="d4298-137">Identificador de instancia de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="d4298-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="d4298-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d4298-138">AppDomain</span></span>|<span data-ttu-id="d4298-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4298-139">xs:string</span></span>|<span data-ttu-id="d4298-140">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d4298-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
