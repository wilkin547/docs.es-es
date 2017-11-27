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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3dc30100cb134740f51e6b2b38c00b2054d2ab0a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="f58ab-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="f58ab-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f58ab-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f58ab-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f58ab-104">Id.</span><span class="sxs-lookup"><span data-stu-id="f58ab-104">ID</span></span>|<span data-ttu-id="f58ab-105">1021</span><span class="sxs-lookup"><span data-stu-id="f58ab-105">1021</span></span>|  
|<span data-ttu-id="f58ab-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f58ab-106">Keywords</span></span>|<span data-ttu-id="f58ab-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f58ab-107">WFRuntime</span></span>|  
|<span data-ttu-id="f58ab-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f58ab-108">Level</span></span>|<span data-ttu-id="f58ab-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="f58ab-109">Verbose</span></span>|  
|<span data-ttu-id="f58ab-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f58ab-110">Channel</span></span>|<span data-ttu-id="f58ab-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f58ab-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f58ab-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f58ab-112">Description</span></span>  
 <span data-ttu-id="f58ab-113">Indica que se ha programado un BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="f58ab-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f58ab-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="f58ab-114">Message</span></span>  
 <span data-ttu-id="f58ab-115">Un BookmarkWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="f58ab-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="f58ab-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="f58ab-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f58ab-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="f58ab-117">Details</span></span>  
  
|<span data-ttu-id="f58ab-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f58ab-118">Data Item Name</span></span>|<span data-ttu-id="f58ab-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f58ab-119">Data Item Type</span></span>|<span data-ttu-id="f58ab-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f58ab-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f58ab-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="f58ab-121">Activity</span></span>|<span data-ttu-id="f58ab-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f58ab-122">xs:string</span></span>|<span data-ttu-id="f58ab-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="f58ab-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="f58ab-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f58ab-124">DisplayName</span></span>|<span data-ttu-id="f58ab-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f58ab-125">xs:string</span></span>|<span data-ttu-id="f58ab-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="f58ab-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="f58ab-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f58ab-127">InstanceId</span></span>|<span data-ttu-id="f58ab-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f58ab-128">xs:string</span></span>|<span data-ttu-id="f58ab-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="f58ab-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f58ab-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="f58ab-130">BookmarkName</span></span>|<span data-ttu-id="f58ab-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f58ab-131">xs:string</span></span>|<span data-ttu-id="f58ab-132">Nombre del marcador.</span><span class="sxs-lookup"><span data-stu-id="f58ab-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="f58ab-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="f58ab-133">BookmarkScope</span></span>|<span data-ttu-id="f58ab-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f58ab-134">xs:string</span></span>|<span data-ttu-id="f58ab-135">Ámbito del marcador.</span><span class="sxs-lookup"><span data-stu-id="f58ab-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="f58ab-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f58ab-136">AppDomain</span></span>|<span data-ttu-id="f58ab-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f58ab-137">xs:string</span></span>|<span data-ttu-id="f58ab-138">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f58ab-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
