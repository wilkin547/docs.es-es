---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: 42ed23654622e29df8ffc210c8d5ba572fa69fd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275354"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="6d564-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="6d564-102">1021 - ScheduleBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="6d564-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6d564-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d564-104">ID</span><span class="sxs-lookup"><span data-stu-id="6d564-104">ID</span></span>|<span data-ttu-id="6d564-105">1021</span><span class="sxs-lookup"><span data-stu-id="6d564-105">1021</span></span>|  
|<span data-ttu-id="6d564-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6d564-106">Keywords</span></span>|<span data-ttu-id="6d564-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6d564-107">WFRuntime</span></span>|  
|<span data-ttu-id="6d564-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="6d564-108">Level</span></span>|<span data-ttu-id="6d564-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="6d564-109">Verbose</span></span>|  
|<span data-ttu-id="6d564-110">Canal</span><span class="sxs-lookup"><span data-stu-id="6d564-110">Channel</span></span>|<span data-ttu-id="6d564-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6d564-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6d564-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d564-112">Description</span></span>  

 <span data-ttu-id="6d564-113">Indica que se ha programado un BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="6d564-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6d564-114">Message</span><span class="sxs-lookup"><span data-stu-id="6d564-114">Message</span></span>  

 <span data-ttu-id="6d564-115">Se ha programado un BookmarkWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="6d564-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="6d564-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="6d564-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6d564-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="6d564-117">Details</span></span>  
  
|<span data-ttu-id="6d564-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6d564-118">Data Item Name</span></span>|<span data-ttu-id="6d564-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6d564-119">Data Item Type</span></span>|<span data-ttu-id="6d564-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d564-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6d564-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="6d564-121">Activity</span></span>|<span data-ttu-id="6d564-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d564-122">xs:string</span></span>|<span data-ttu-id="6d564-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="6d564-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="6d564-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="6d564-124">DisplayName</span></span>|<span data-ttu-id="6d564-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d564-125">xs:string</span></span>|<span data-ttu-id="6d564-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="6d564-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="6d564-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="6d564-127">InstanceId</span></span>|<span data-ttu-id="6d564-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d564-128">xs:string</span></span>|<span data-ttu-id="6d564-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="6d564-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="6d564-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="6d564-130">BookmarkName</span></span>|<span data-ttu-id="6d564-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d564-131">xs:string</span></span>|<span data-ttu-id="6d564-132">Nombre del marcador.</span><span class="sxs-lookup"><span data-stu-id="6d564-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="6d564-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="6d564-133">BookmarkScope</span></span>|<span data-ttu-id="6d564-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d564-134">xs:string</span></span>|<span data-ttu-id="6d564-135">Ámbito del marcador.</span><span class="sxs-lookup"><span data-stu-id="6d564-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="6d564-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6d564-136">AppDomain</span></span>|<span data-ttu-id="6d564-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d564-137">xs:string</span></span>|<span data-ttu-id="6d564-138">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6d564-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
