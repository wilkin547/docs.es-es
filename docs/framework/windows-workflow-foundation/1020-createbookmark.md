---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 2a382a2f12f4800cd70286a553af253e2af64c9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510464"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="23423-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="23423-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="23423-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="23423-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23423-104">Id.</span><span class="sxs-lookup"><span data-stu-id="23423-104">ID</span></span>|<span data-ttu-id="23423-105">1020</span><span class="sxs-lookup"><span data-stu-id="23423-105">1020</span></span>|  
|<span data-ttu-id="23423-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="23423-106">Keywords</span></span>|<span data-ttu-id="23423-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="23423-107">WFRuntime</span></span>|  
|<span data-ttu-id="23423-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="23423-108">Level</span></span>|<span data-ttu-id="23423-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="23423-109">Verbose</span></span>|  
|<span data-ttu-id="23423-110">Canal</span><span class="sxs-lookup"><span data-stu-id="23423-110">Channel</span></span>|<span data-ttu-id="23423-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="23423-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="23423-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="23423-112">Description</span></span>  
 <span data-ttu-id="23423-113">Indica que se ha creado un marcador para una actividad.</span><span class="sxs-lookup"><span data-stu-id="23423-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="23423-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="23423-114">Message</span></span>  
 <span data-ttu-id="23423-115">Se ha creado un marcador para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="23423-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="23423-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="23423-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="23423-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="23423-117">Details</span></span>  
  
|<span data-ttu-id="23423-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="23423-118">Data Item Name</span></span>|<span data-ttu-id="23423-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="23423-119">Data Item Type</span></span>|<span data-ttu-id="23423-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="23423-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="23423-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="23423-121">Activity</span></span>|<span data-ttu-id="23423-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="23423-122">xs:string</span></span>|<span data-ttu-id="23423-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="23423-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="23423-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="23423-124">DisplayName</span></span>|<span data-ttu-id="23423-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="23423-125">xs:string</span></span>|<span data-ttu-id="23423-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="23423-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="23423-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="23423-127">InstanceId</span></span>|<span data-ttu-id="23423-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="23423-128">xs:string</span></span>|<span data-ttu-id="23423-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="23423-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="23423-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="23423-130">BookmarkName</span></span>|<span data-ttu-id="23423-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="23423-131">xs:string</span></span>|<span data-ttu-id="23423-132">Nombre del marcador.</span><span class="sxs-lookup"><span data-stu-id="23423-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="23423-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="23423-133">BookmarkScope</span></span>|<span data-ttu-id="23423-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="23423-134">xs:string</span></span>|<span data-ttu-id="23423-135">Ámbito del marcador.</span><span class="sxs-lookup"><span data-stu-id="23423-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="23423-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="23423-136">AppDomain</span></span>|<span data-ttu-id="23423-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="23423-137">xs:string</span></span>|<span data-ttu-id="23423-138">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="23423-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
