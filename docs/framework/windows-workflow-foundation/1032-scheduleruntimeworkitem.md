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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4de69b1fc2647d7723db8aebb02942938db7478f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="8b4e1-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="8b4e1-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8b4e1-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8b4e1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8b4e1-104">Id.</span><span class="sxs-lookup"><span data-stu-id="8b4e1-104">ID</span></span>|<span data-ttu-id="8b4e1-105">1032</span><span class="sxs-lookup"><span data-stu-id="8b4e1-105">1032</span></span>|  
|<span data-ttu-id="8b4e1-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b4e1-106">Keywords</span></span>|<span data-ttu-id="8b4e1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8b4e1-107">WFRuntime</span></span>|  
|<span data-ttu-id="8b4e1-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="8b4e1-108">Level</span></span>|<span data-ttu-id="8b4e1-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="8b4e1-109">Verbose</span></span>|  
|<span data-ttu-id="8b4e1-110">Canal</span><span class="sxs-lookup"><span data-stu-id="8b4e1-110">Channel</span></span>|<span data-ttu-id="8b4e1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8b4e1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8b4e1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b4e1-112">Description</span></span>  
 <span data-ttu-id="8b4e1-113">Indica que se ha programado un RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="8b4e1-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8b4e1-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="8b4e1-114">Message</span></span>  
 <span data-ttu-id="8b4e1-115">Se ha programado un elemento de trabajo en tiempo de ejecución para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="8b4e1-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8b4e1-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="8b4e1-116">Details</span></span>  
  
|<span data-ttu-id="8b4e1-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8b4e1-117">Data Item Name</span></span>|<span data-ttu-id="8b4e1-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8b4e1-118">Data Item Type</span></span>|<span data-ttu-id="8b4e1-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b4e1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8b4e1-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="8b4e1-120">Activity</span></span>|<span data-ttu-id="8b4e1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b4e1-121">xs:string</span></span>|<span data-ttu-id="8b4e1-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="8b4e1-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8b4e1-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8b4e1-123">DisplayName</span></span>|<span data-ttu-id="8b4e1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b4e1-124">xs:string</span></span>|<span data-ttu-id="8b4e1-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="8b4e1-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8b4e1-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8b4e1-126">InstanceId</span></span>|<span data-ttu-id="8b4e1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b4e1-127">xs:string</span></span>|<span data-ttu-id="8b4e1-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="8b4e1-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8b4e1-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8b4e1-129">AppDomain</span></span>|<span data-ttu-id="8b4e1-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b4e1-130">xs:string</span></span>|<span data-ttu-id="8b4e1-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8b4e1-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
