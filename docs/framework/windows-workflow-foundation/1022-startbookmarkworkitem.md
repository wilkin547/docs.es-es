---
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: 93d906b32b51effaa709da6763f535708cd6f821
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509813"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="3b400-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="3b400-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3b400-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3b400-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b400-104">Id.</span><span class="sxs-lookup"><span data-stu-id="3b400-104">ID</span></span>|<span data-ttu-id="3b400-105">1022</span><span class="sxs-lookup"><span data-stu-id="3b400-105">1022</span></span>|  
|<span data-ttu-id="3b400-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3b400-106">Keywords</span></span>|<span data-ttu-id="3b400-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3b400-107">WFRuntime</span></span>|  
|<span data-ttu-id="3b400-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="3b400-108">Level</span></span>|<span data-ttu-id="3b400-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="3b400-109">Verbose</span></span>|  
|<span data-ttu-id="3b400-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3b400-110">Channel</span></span>|<span data-ttu-id="3b400-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3b400-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3b400-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b400-112">Description</span></span>  
 <span data-ttu-id="3b400-113">Indica que un BookmarkWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="3b400-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3b400-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="3b400-114">Message</span></span>  
 <span data-ttu-id="3b400-115">Iniciando la ejecución de un BookmarkWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="3b400-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="3b400-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="3b400-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3b400-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="3b400-117">Details</span></span>  
  
|<span data-ttu-id="3b400-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3b400-118">Data Item Name</span></span>|<span data-ttu-id="3b400-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3b400-119">Data Item Type</span></span>|<span data-ttu-id="3b400-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b400-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3b400-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="3b400-121">Activity</span></span>|<span data-ttu-id="3b400-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b400-122">xs:string</span></span>|<span data-ttu-id="3b400-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3b400-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="3b400-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3b400-124">DisplayName</span></span>|<span data-ttu-id="3b400-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b400-125">xs:string</span></span>|<span data-ttu-id="3b400-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3b400-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="3b400-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3b400-127">InstanceId</span></span>|<span data-ttu-id="3b400-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b400-128">xs:string</span></span>|<span data-ttu-id="3b400-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3b400-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3b400-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="3b400-130">BookmarkName</span></span>|<span data-ttu-id="3b400-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b400-131">xs:string</span></span>|<span data-ttu-id="3b400-132">Nombre del marcador.</span><span class="sxs-lookup"><span data-stu-id="3b400-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="3b400-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="3b400-133">BookmarkScope</span></span>|<span data-ttu-id="3b400-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b400-134">xs:string</span></span>|<span data-ttu-id="3b400-135">Ámbito del marcador.</span><span class="sxs-lookup"><span data-stu-id="3b400-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="3b400-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3b400-136">AppDomain</span></span>|<span data-ttu-id="3b400-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b400-137">xs:string</span></span>|<span data-ttu-id="3b400-138">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3b400-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
