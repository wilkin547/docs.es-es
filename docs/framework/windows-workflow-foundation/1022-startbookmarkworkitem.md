---
title: 1022 - StartBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9aaabbdca455d31d22b232ae2b08edef0687ac30
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="66bb1-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="66bb1-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="66bb1-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="66bb1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66bb1-104">Id.</span><span class="sxs-lookup"><span data-stu-id="66bb1-104">ID</span></span>|<span data-ttu-id="66bb1-105">1022</span><span class="sxs-lookup"><span data-stu-id="66bb1-105">1022</span></span>|  
|<span data-ttu-id="66bb1-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="66bb1-106">Keywords</span></span>|<span data-ttu-id="66bb1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="66bb1-107">WFRuntime</span></span>|  
|<span data-ttu-id="66bb1-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="66bb1-108">Level</span></span>|<span data-ttu-id="66bb1-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="66bb1-109">Verbose</span></span>|  
|<span data-ttu-id="66bb1-110">Canal</span><span class="sxs-lookup"><span data-stu-id="66bb1-110">Channel</span></span>|<span data-ttu-id="66bb1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="66bb1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="66bb1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="66bb1-112">Description</span></span>  
 <span data-ttu-id="66bb1-113">Indica que un BookmarkWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="66bb1-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="66bb1-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="66bb1-114">Message</span></span>  
 <span data-ttu-id="66bb1-115">Iniciando la ejecución de un BookmarkWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="66bb1-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="66bb1-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="66bb1-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="66bb1-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="66bb1-117">Details</span></span>  
  
|<span data-ttu-id="66bb1-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="66bb1-118">Data Item Name</span></span>|<span data-ttu-id="66bb1-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="66bb1-119">Data Item Type</span></span>|<span data-ttu-id="66bb1-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="66bb1-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="66bb1-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="66bb1-121">Activity</span></span>|<span data-ttu-id="66bb1-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="66bb1-122">xs:string</span></span>|<span data-ttu-id="66bb1-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="66bb1-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="66bb1-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="66bb1-124">DisplayName</span></span>|<span data-ttu-id="66bb1-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="66bb1-125">xs:string</span></span>|<span data-ttu-id="66bb1-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="66bb1-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="66bb1-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="66bb1-127">InstanceId</span></span>|<span data-ttu-id="66bb1-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="66bb1-128">xs:string</span></span>|<span data-ttu-id="66bb1-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="66bb1-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="66bb1-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="66bb1-130">BookmarkName</span></span>|<span data-ttu-id="66bb1-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="66bb1-131">xs:string</span></span>|<span data-ttu-id="66bb1-132">Nombre del marcador.</span><span class="sxs-lookup"><span data-stu-id="66bb1-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="66bb1-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="66bb1-133">BookmarkScope</span></span>|<span data-ttu-id="66bb1-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="66bb1-134">xs:string</span></span>|<span data-ttu-id="66bb1-135">Ámbito del marcador.</span><span class="sxs-lookup"><span data-stu-id="66bb1-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="66bb1-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="66bb1-136">AppDomain</span></span>|<span data-ttu-id="66bb1-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="66bb1-137">xs:string</span></span>|<span data-ttu-id="66bb1-138">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="66bb1-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
