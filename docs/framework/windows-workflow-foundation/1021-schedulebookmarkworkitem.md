---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: abc026165568d05faef619da28c94f27f37eea27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509761"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="87159-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="87159-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="87159-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="87159-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87159-104">Id.</span><span class="sxs-lookup"><span data-stu-id="87159-104">ID</span></span>|<span data-ttu-id="87159-105">1021</span><span class="sxs-lookup"><span data-stu-id="87159-105">1021</span></span>|  
|<span data-ttu-id="87159-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="87159-106">Keywords</span></span>|<span data-ttu-id="87159-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="87159-107">WFRuntime</span></span>|  
|<span data-ttu-id="87159-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="87159-108">Level</span></span>|<span data-ttu-id="87159-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="87159-109">Verbose</span></span>|  
|<span data-ttu-id="87159-110">Canal</span><span class="sxs-lookup"><span data-stu-id="87159-110">Channel</span></span>|<span data-ttu-id="87159-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="87159-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="87159-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="87159-112">Description</span></span>  
 <span data-ttu-id="87159-113">Indica que se ha programado un BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="87159-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="87159-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="87159-114">Message</span></span>  
 <span data-ttu-id="87159-115">Un BookmarkWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="87159-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="87159-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="87159-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="87159-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="87159-117">Details</span></span>  
  
|<span data-ttu-id="87159-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="87159-118">Data Item Name</span></span>|<span data-ttu-id="87159-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="87159-119">Data Item Type</span></span>|<span data-ttu-id="87159-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="87159-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="87159-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="87159-121">Activity</span></span>|<span data-ttu-id="87159-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="87159-122">xs:string</span></span>|<span data-ttu-id="87159-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="87159-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="87159-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="87159-124">DisplayName</span></span>|<span data-ttu-id="87159-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="87159-125">xs:string</span></span>|<span data-ttu-id="87159-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="87159-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="87159-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="87159-127">InstanceId</span></span>|<span data-ttu-id="87159-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="87159-128">xs:string</span></span>|<span data-ttu-id="87159-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="87159-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="87159-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="87159-130">BookmarkName</span></span>|<span data-ttu-id="87159-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="87159-131">xs:string</span></span>|<span data-ttu-id="87159-132">Nombre del marcador.</span><span class="sxs-lookup"><span data-stu-id="87159-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="87159-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="87159-133">BookmarkScope</span></span>|<span data-ttu-id="87159-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="87159-134">xs:string</span></span>|<span data-ttu-id="87159-135">Ámbito del marcador.</span><span class="sxs-lookup"><span data-stu-id="87159-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="87159-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="87159-136">AppDomain</span></span>|<span data-ttu-id="87159-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="87159-137">xs:string</span></span>|<span data-ttu-id="87159-138">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="87159-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
