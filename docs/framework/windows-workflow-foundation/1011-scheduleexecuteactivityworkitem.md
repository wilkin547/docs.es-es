---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec89acb9d83a28ac280db7c3d536bfe63669fa97
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="b621a-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="b621a-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b621a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b621a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b621a-104">Id.</span><span class="sxs-lookup"><span data-stu-id="b621a-104">ID</span></span>|<span data-ttu-id="b621a-105">1011</span><span class="sxs-lookup"><span data-stu-id="b621a-105">1011</span></span>|  
|<span data-ttu-id="b621a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b621a-106">Keywords</span></span>|<span data-ttu-id="b621a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b621a-107">WFRuntime</span></span>|  
|<span data-ttu-id="b621a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b621a-108">Level</span></span>|<span data-ttu-id="b621a-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="b621a-109">Verbose</span></span>|  
|<span data-ttu-id="b621a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b621a-110">Channel</span></span>|<span data-ttu-id="b621a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b621a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b621a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b621a-112">Description</span></span>  
 <span data-ttu-id="b621a-113">Indica que se ha programado un ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="b621a-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b621a-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b621a-114">Message</span></span>  
 <span data-ttu-id="b621a-115">Un ExecuteActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="b621a-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b621a-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="b621a-116">Details</span></span>  
  
|<span data-ttu-id="b621a-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b621a-117">Data Item Name</span></span>|<span data-ttu-id="b621a-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b621a-118">Data Item Type</span></span>|<span data-ttu-id="b621a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="b621a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b621a-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="b621a-120">Activity</span></span>|<span data-ttu-id="b621a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b621a-121">xs:string</span></span>|<span data-ttu-id="b621a-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b621a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="b621a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b621a-123">DisplayName</span></span>|<span data-ttu-id="b621a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b621a-124">xs:string</span></span>|<span data-ttu-id="b621a-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b621a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="b621a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b621a-126">InstanceId</span></span>|<span data-ttu-id="b621a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b621a-127">xs:string</span></span>|<span data-ttu-id="b621a-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b621a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b621a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b621a-129">AppDomain</span></span>|<span data-ttu-id="b621a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b621a-130">xs:string</span></span>|<span data-ttu-id="b621a-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b621a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
