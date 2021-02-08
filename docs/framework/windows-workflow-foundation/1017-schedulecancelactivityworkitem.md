---
description: 'Más información acerca de: 1017-ScheduleCancelActivityWorkItem'
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 04dc4f663ceed1d7350dd14867e4926042bd11af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792900"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="b35ea-103">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="b35ea-103">1017 - ScheduleCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="b35ea-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b35ea-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b35ea-105">Id.</span><span class="sxs-lookup"><span data-stu-id="b35ea-105">ID</span></span>|<span data-ttu-id="b35ea-106">1017</span><span class="sxs-lookup"><span data-stu-id="b35ea-106">1017</span></span>|  
|<span data-ttu-id="b35ea-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b35ea-107">Keywords</span></span>|<span data-ttu-id="b35ea-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b35ea-108">WFRuntime</span></span>|  
|<span data-ttu-id="b35ea-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="b35ea-109">Level</span></span>|<span data-ttu-id="b35ea-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="b35ea-110">Verbose</span></span>|  
|<span data-ttu-id="b35ea-111">Canal</span><span class="sxs-lookup"><span data-stu-id="b35ea-111">Channel</span></span>|<span data-ttu-id="b35ea-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b35ea-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b35ea-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b35ea-113">Description</span></span>  

 <span data-ttu-id="b35ea-114">Indica que se ha programado un CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="b35ea-114">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b35ea-115">Message</span><span class="sxs-lookup"><span data-stu-id="b35ea-115">Message</span></span>  

 <span data-ttu-id="b35ea-116">Un CancelActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="b35ea-116">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b35ea-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="b35ea-117">Details</span></span>  
  
|<span data-ttu-id="b35ea-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b35ea-118">Data Item Name</span></span>|<span data-ttu-id="b35ea-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b35ea-119">Data Item Type</span></span>|<span data-ttu-id="b35ea-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b35ea-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b35ea-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="b35ea-121">Activity</span></span>|<span data-ttu-id="b35ea-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b35ea-122">xs:string</span></span>|<span data-ttu-id="b35ea-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b35ea-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="b35ea-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b35ea-124">DisplayName</span></span>|<span data-ttu-id="b35ea-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b35ea-125">xs:string</span></span>|<span data-ttu-id="b35ea-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b35ea-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="b35ea-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b35ea-127">InstanceId</span></span>|<span data-ttu-id="b35ea-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b35ea-128">xs:string</span></span>|<span data-ttu-id="b35ea-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b35ea-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b35ea-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b35ea-130">AppDomain</span></span>|<span data-ttu-id="b35ea-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b35ea-131">xs:string</span></span>|<span data-ttu-id="b35ea-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b35ea-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
