---
title: 1021 - ScheduleBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61c67792f807907f58480f3bfa3d192b811766b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="02165-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="02165-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="02165-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="02165-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02165-104">Id.</span><span class="sxs-lookup"><span data-stu-id="02165-104">ID</span></span>|<span data-ttu-id="02165-105">1021</span><span class="sxs-lookup"><span data-stu-id="02165-105">1021</span></span>|  
|<span data-ttu-id="02165-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="02165-106">Keywords</span></span>|<span data-ttu-id="02165-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="02165-107">WFRuntime</span></span>|  
|<span data-ttu-id="02165-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="02165-108">Level</span></span>|<span data-ttu-id="02165-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="02165-109">Verbose</span></span>|  
|<span data-ttu-id="02165-110">Canal</span><span class="sxs-lookup"><span data-stu-id="02165-110">Channel</span></span>|<span data-ttu-id="02165-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="02165-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="02165-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="02165-112">Description</span></span>  
 <span data-ttu-id="02165-113">Indica que se ha programado un BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="02165-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="02165-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="02165-114">Message</span></span>  
 <span data-ttu-id="02165-115">Un BookmarkWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="02165-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="02165-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="02165-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="02165-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="02165-117">Details</span></span>  
  
|<span data-ttu-id="02165-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="02165-118">Data Item Name</span></span>|<span data-ttu-id="02165-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="02165-119">Data Item Type</span></span>|<span data-ttu-id="02165-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="02165-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="02165-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="02165-121">Activity</span></span>|<span data-ttu-id="02165-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="02165-122">xs:string</span></span>|<span data-ttu-id="02165-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="02165-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="02165-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="02165-124">DisplayName</span></span>|<span data-ttu-id="02165-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="02165-125">xs:string</span></span>|<span data-ttu-id="02165-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="02165-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="02165-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="02165-127">InstanceId</span></span>|<span data-ttu-id="02165-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="02165-128">xs:string</span></span>|<span data-ttu-id="02165-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="02165-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="02165-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="02165-130">BookmarkName</span></span>|<span data-ttu-id="02165-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="02165-131">xs:string</span></span>|<span data-ttu-id="02165-132">Nombre del marcador.</span><span class="sxs-lookup"><span data-stu-id="02165-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="02165-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="02165-133">BookmarkScope</span></span>|<span data-ttu-id="02165-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="02165-134">xs:string</span></span>|<span data-ttu-id="02165-135">Ámbito del marcador.</span><span class="sxs-lookup"><span data-stu-id="02165-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="02165-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="02165-136">AppDomain</span></span>|<span data-ttu-id="02165-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="02165-137">xs:string</span></span>|<span data-ttu-id="02165-138">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="02165-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
