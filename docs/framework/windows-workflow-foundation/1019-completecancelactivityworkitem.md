---
description: 'Más información acerca de: 1019-CompleteCancelActivityWorkItem'
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 33e58931562d7244987dd8c0d9cf5d34fb894190
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792874"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="9baa4-103">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="9baa4-103">1019 - CompleteCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="9baa4-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9baa4-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9baa4-105">Id.</span><span class="sxs-lookup"><span data-stu-id="9baa4-105">ID</span></span>|<span data-ttu-id="9baa4-106">1019</span><span class="sxs-lookup"><span data-stu-id="9baa4-106">1019</span></span>|  
|<span data-ttu-id="9baa4-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9baa4-107">Keywords</span></span>|<span data-ttu-id="9baa4-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9baa4-108">WFRuntime</span></span>|  
|<span data-ttu-id="9baa4-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="9baa4-109">Level</span></span>|<span data-ttu-id="9baa4-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="9baa4-110">Verbose</span></span>|  
|<span data-ttu-id="9baa4-111">Canal</span><span class="sxs-lookup"><span data-stu-id="9baa4-111">Channel</span></span>|<span data-ttu-id="9baa4-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9baa4-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9baa4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9baa4-113">Description</span></span>  

 <span data-ttu-id="9baa4-114">Indica que se ha completado un CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="9baa4-114">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9baa4-115">Message</span><span class="sxs-lookup"><span data-stu-id="9baa4-115">Message</span></span>  

 <span data-ttu-id="9baa4-116">Un CancelActivityWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="9baa4-116">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9baa4-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="9baa4-117">Details</span></span>  
  
|<span data-ttu-id="9baa4-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9baa4-118">Data Item Name</span></span>|<span data-ttu-id="9baa4-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9baa4-119">Data Item Type</span></span>|<span data-ttu-id="9baa4-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="9baa4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9baa4-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="9baa4-121">Activity</span></span>|<span data-ttu-id="9baa4-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="9baa4-122">xs:string</span></span>|<span data-ttu-id="9baa4-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="9baa4-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="9baa4-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9baa4-124">DisplayName</span></span>|<span data-ttu-id="9baa4-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="9baa4-125">xs:string</span></span>|<span data-ttu-id="9baa4-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="9baa4-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="9baa4-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9baa4-127">InstanceId</span></span>|<span data-ttu-id="9baa4-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="9baa4-128">xs:string</span></span>|<span data-ttu-id="9baa4-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="9baa4-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9baa4-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9baa4-130">AppDomain</span></span>|<span data-ttu-id="9baa4-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="9baa4-131">xs:string</span></span>|<span data-ttu-id="9baa4-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9baa4-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
