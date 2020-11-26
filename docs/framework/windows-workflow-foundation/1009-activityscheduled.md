---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 812531d4206dfee20f183b9461330e71263b0bf8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239775"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="30e29-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="30e29-102">1009 - ActivityScheduled</span></span>

## <a name="properties"></a><span data-ttu-id="30e29-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="30e29-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30e29-104">ID</span><span class="sxs-lookup"><span data-stu-id="30e29-104">ID</span></span>|<span data-ttu-id="30e29-105">1009</span><span class="sxs-lookup"><span data-stu-id="30e29-105">1009</span></span>|  
|<span data-ttu-id="30e29-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="30e29-106">Keywords</span></span>|<span data-ttu-id="30e29-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="30e29-107">WFRuntime</span></span>|  
|<span data-ttu-id="30e29-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="30e29-108">Level</span></span>|<span data-ttu-id="30e29-109">Información</span><span class="sxs-lookup"><span data-stu-id="30e29-109">Information</span></span>|  
|<span data-ttu-id="30e29-110">Canal</span><span class="sxs-lookup"><span data-stu-id="30e29-110">Channel</span></span>|<span data-ttu-id="30e29-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="30e29-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="30e29-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="30e29-112">Description</span></span>  

 <span data-ttu-id="30e29-113">Indica que una actividad se está programando para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="30e29-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="30e29-114">Message</span><span class="sxs-lookup"><span data-stu-id="30e29-114">Message</span></span>  

 <span data-ttu-id="30e29-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="30e29-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="30e29-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="30e29-116">Details</span></span>  
  
|<span data-ttu-id="30e29-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="30e29-117">Data Item Name</span></span>|<span data-ttu-id="30e29-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="30e29-118">Data Item Type</span></span>|<span data-ttu-id="30e29-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="30e29-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="30e29-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="30e29-120">ParentActivity</span></span>|<span data-ttu-id="30e29-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="30e29-121">xs:string</span></span>|<span data-ttu-id="30e29-122">Nombre del tipo de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="30e29-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="30e29-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="30e29-123">ParentDisplayName</span></span>|<span data-ttu-id="30e29-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="30e29-124">xs:string</span></span>|<span data-ttu-id="30e29-125">Identificación y nombre para mostrar de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="30e29-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="30e29-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="30e29-126">ParentInstanceId</span></span>|<span data-ttu-id="30e29-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="30e29-127">xs:string</span></span>|<span data-ttu-id="30e29-128">Identificador de instancia de la actividad principal.</span><span class="sxs-lookup"><span data-stu-id="30e29-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="30e29-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="30e29-129">ChildActivity</span></span>|<span data-ttu-id="30e29-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="30e29-130">xs:string</span></span>|<span data-ttu-id="30e29-131">Nombre del tipo de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="30e29-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="30e29-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="30e29-132">ChildDisplayName</span></span>|<span data-ttu-id="30e29-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="30e29-133">xs:string</span></span>|<span data-ttu-id="30e29-134">El nombre para mostrar de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="30e29-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="30e29-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="30e29-135">ChildInstanceId</span></span>|<span data-ttu-id="30e29-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="30e29-136">xs:string</span></span>|<span data-ttu-id="30e29-137">Identificador de instancia de la actividad secundaria programada.</span><span class="sxs-lookup"><span data-stu-id="30e29-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="30e29-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="30e29-138">AppDomain</span></span>|<span data-ttu-id="30e29-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="30e29-139">xs:string</span></span>|<span data-ttu-id="30e29-140">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="30e29-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
