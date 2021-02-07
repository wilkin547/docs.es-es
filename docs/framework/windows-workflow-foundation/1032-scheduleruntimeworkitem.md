---
description: 'Más información acerca de: 1032-ScheduleRuntimeWorkItem'
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: d96226b4ab0f856218d292c9c2481bca6c463c8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668050"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="26acb-103">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="26acb-103">1032 - ScheduleRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="26acb-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="26acb-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26acb-105">Id.</span><span class="sxs-lookup"><span data-stu-id="26acb-105">ID</span></span>|<span data-ttu-id="26acb-106">1032</span><span class="sxs-lookup"><span data-stu-id="26acb-106">1032</span></span>|  
|<span data-ttu-id="26acb-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="26acb-107">Keywords</span></span>|<span data-ttu-id="26acb-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="26acb-108">WFRuntime</span></span>|  
|<span data-ttu-id="26acb-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="26acb-109">Level</span></span>|<span data-ttu-id="26acb-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="26acb-110">Verbose</span></span>|  
|<span data-ttu-id="26acb-111">Canal</span><span class="sxs-lookup"><span data-stu-id="26acb-111">Channel</span></span>|<span data-ttu-id="26acb-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="26acb-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="26acb-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="26acb-113">Description</span></span>  

 <span data-ttu-id="26acb-114">Indica que se ha programado un RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="26acb-114">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="26acb-115">Message</span><span class="sxs-lookup"><span data-stu-id="26acb-115">Message</span></span>  

 <span data-ttu-id="26acb-116">Se ha programado un elemento de trabajo en runtime para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="26acb-116">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="26acb-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="26acb-117">Details</span></span>  
  
|<span data-ttu-id="26acb-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="26acb-118">Data Item Name</span></span>|<span data-ttu-id="26acb-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="26acb-119">Data Item Type</span></span>|<span data-ttu-id="26acb-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="26acb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="26acb-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="26acb-121">Activity</span></span>|<span data-ttu-id="26acb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="26acb-122">xs:string</span></span>|<span data-ttu-id="26acb-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="26acb-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="26acb-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="26acb-124">DisplayName</span></span>|<span data-ttu-id="26acb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="26acb-125">xs:string</span></span>|<span data-ttu-id="26acb-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="26acb-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="26acb-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="26acb-127">InstanceId</span></span>|<span data-ttu-id="26acb-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="26acb-128">xs:string</span></span>|<span data-ttu-id="26acb-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="26acb-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="26acb-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="26acb-130">AppDomain</span></span>|<span data-ttu-id="26acb-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="26acb-131">xs:string</span></span>|<span data-ttu-id="26acb-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="26acb-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
