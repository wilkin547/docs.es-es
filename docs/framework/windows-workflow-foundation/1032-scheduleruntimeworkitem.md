---
title: 1032 - ScheduleRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81cc73a5ab58e90f1a0ee5bdaf9a491d20206fb3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="a8b19-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="a8b19-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a8b19-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a8b19-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8b19-104">Id.</span><span class="sxs-lookup"><span data-stu-id="a8b19-104">ID</span></span>|<span data-ttu-id="a8b19-105">1032</span><span class="sxs-lookup"><span data-stu-id="a8b19-105">1032</span></span>|  
|<span data-ttu-id="a8b19-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a8b19-106">Keywords</span></span>|<span data-ttu-id="a8b19-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a8b19-107">WFRuntime</span></span>|  
|<span data-ttu-id="a8b19-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a8b19-108">Level</span></span>|<span data-ttu-id="a8b19-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="a8b19-109">Verbose</span></span>|  
|<span data-ttu-id="a8b19-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a8b19-110">Channel</span></span>|<span data-ttu-id="a8b19-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a8b19-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a8b19-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8b19-112">Description</span></span>  
 <span data-ttu-id="a8b19-113">Indica que se ha programado un RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="a8b19-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a8b19-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a8b19-114">Message</span></span>  
 <span data-ttu-id="a8b19-115">Se ha programado un elemento de trabajo en tiempo de ejecución para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="a8b19-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a8b19-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="a8b19-116">Details</span></span>  
  
|<span data-ttu-id="a8b19-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a8b19-117">Data Item Name</span></span>|<span data-ttu-id="a8b19-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a8b19-118">Data Item Type</span></span>|<span data-ttu-id="a8b19-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8b19-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a8b19-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="a8b19-120">Activity</span></span>|<span data-ttu-id="a8b19-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a8b19-121">xs:string</span></span>|<span data-ttu-id="a8b19-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="a8b19-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="a8b19-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a8b19-123">DisplayName</span></span>|<span data-ttu-id="a8b19-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a8b19-124">xs:string</span></span>|<span data-ttu-id="a8b19-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="a8b19-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="a8b19-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a8b19-126">InstanceId</span></span>|<span data-ttu-id="a8b19-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a8b19-127">xs:string</span></span>|<span data-ttu-id="a8b19-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="a8b19-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="a8b19-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a8b19-129">AppDomain</span></span>|<span data-ttu-id="a8b19-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a8b19-130">xs:string</span></span>|<span data-ttu-id="a8b19-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a8b19-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
