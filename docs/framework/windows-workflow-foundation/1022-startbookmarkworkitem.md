---
description: 'Más información acerca de: 1022-StartBookmarkWorkItem'
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: 37d1ec1216df26a928b39189ca299dbb5b6c3d4b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792835"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="1c892-103">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="1c892-103">1022 - StartBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="1c892-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1c892-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1c892-105">Id.</span><span class="sxs-lookup"><span data-stu-id="1c892-105">ID</span></span>|<span data-ttu-id="1c892-106">1022</span><span class="sxs-lookup"><span data-stu-id="1c892-106">1022</span></span>|  
|<span data-ttu-id="1c892-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1c892-107">Keywords</span></span>|<span data-ttu-id="1c892-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1c892-108">WFRuntime</span></span>|  
|<span data-ttu-id="1c892-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="1c892-109">Level</span></span>|<span data-ttu-id="1c892-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="1c892-110">Verbose</span></span>|  
|<span data-ttu-id="1c892-111">Canal</span><span class="sxs-lookup"><span data-stu-id="1c892-111">Channel</span></span>|<span data-ttu-id="1c892-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1c892-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1c892-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c892-113">Description</span></span>  

 <span data-ttu-id="1c892-114">Indica que un BookmarkWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c892-114">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1c892-115">Message</span><span class="sxs-lookup"><span data-stu-id="1c892-115">Message</span></span>  

 <span data-ttu-id="1c892-116">Iniciando la ejecución de un BookmarkWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="1c892-116">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="1c892-117">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="1c892-117">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1c892-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="1c892-118">Details</span></span>  
  
|<span data-ttu-id="1c892-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="1c892-119">Data Item Name</span></span>|<span data-ttu-id="1c892-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="1c892-120">Data Item Type</span></span>|<span data-ttu-id="1c892-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c892-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1c892-122">Actividad</span><span class="sxs-lookup"><span data-stu-id="1c892-122">Activity</span></span>|<span data-ttu-id="1c892-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c892-123">xs:string</span></span>|<span data-ttu-id="1c892-124">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="1c892-124">The type name of the activity.</span></span>|  
|<span data-ttu-id="1c892-125">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1c892-125">DisplayName</span></span>|<span data-ttu-id="1c892-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c892-126">xs:string</span></span>|<span data-ttu-id="1c892-127">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="1c892-127">The display name of the activity.</span></span>|  
|<span data-ttu-id="1c892-128">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1c892-128">InstanceId</span></span>|<span data-ttu-id="1c892-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c892-129">xs:string</span></span>|<span data-ttu-id="1c892-130">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="1c892-130">The instance id of the activity.</span></span>|  
|<span data-ttu-id="1c892-131">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="1c892-131">BookmarkName</span></span>|<span data-ttu-id="1c892-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c892-132">xs:string</span></span>|<span data-ttu-id="1c892-133">Nombre del marcador.</span><span class="sxs-lookup"><span data-stu-id="1c892-133">The name of the bookmark.</span></span>|  
|<span data-ttu-id="1c892-134">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="1c892-134">BookmarkScope</span></span>|<span data-ttu-id="1c892-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c892-135">xs:string</span></span>|<span data-ttu-id="1c892-136">Ámbito del marcador.</span><span class="sxs-lookup"><span data-stu-id="1c892-136">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="1c892-137">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1c892-137">AppDomain</span></span>|<span data-ttu-id="1c892-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c892-138">xs:string</span></span>|<span data-ttu-id="1c892-139">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1c892-139">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
