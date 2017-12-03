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
ms.openlocfilehash: d2a150b9e9c78a9ce1f5e20b962a58ef2d5dde9d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="266e6-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="266e6-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="266e6-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="266e6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="266e6-104">Id.</span><span class="sxs-lookup"><span data-stu-id="266e6-104">ID</span></span>|<span data-ttu-id="266e6-105">1032</span><span class="sxs-lookup"><span data-stu-id="266e6-105">1032</span></span>|  
|<span data-ttu-id="266e6-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="266e6-106">Keywords</span></span>|<span data-ttu-id="266e6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="266e6-107">WFRuntime</span></span>|  
|<span data-ttu-id="266e6-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="266e6-108">Level</span></span>|<span data-ttu-id="266e6-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="266e6-109">Verbose</span></span>|  
|<span data-ttu-id="266e6-110">Canal</span><span class="sxs-lookup"><span data-stu-id="266e6-110">Channel</span></span>|<span data-ttu-id="266e6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="266e6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="266e6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="266e6-112">Description</span></span>  
 <span data-ttu-id="266e6-113">Indica que se ha programado un RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="266e6-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="266e6-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="266e6-114">Message</span></span>  
 <span data-ttu-id="266e6-115">Se ha programado un elemento de trabajo en tiempo de ejecución para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="266e6-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="266e6-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="266e6-116">Details</span></span>  
  
|<span data-ttu-id="266e6-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="266e6-117">Data Item Name</span></span>|<span data-ttu-id="266e6-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="266e6-118">Data Item Type</span></span>|<span data-ttu-id="266e6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="266e6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="266e6-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="266e6-120">Activity</span></span>|<span data-ttu-id="266e6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="266e6-121">xs:string</span></span>|<span data-ttu-id="266e6-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="266e6-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="266e6-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="266e6-123">DisplayName</span></span>|<span data-ttu-id="266e6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="266e6-124">xs:string</span></span>|<span data-ttu-id="266e6-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="266e6-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="266e6-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="266e6-126">InstanceId</span></span>|<span data-ttu-id="266e6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="266e6-127">xs:string</span></span>|<span data-ttu-id="266e6-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="266e6-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="266e6-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="266e6-129">AppDomain</span></span>|<span data-ttu-id="266e6-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="266e6-130">xs:string</span></span>|<span data-ttu-id="266e6-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="266e6-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
