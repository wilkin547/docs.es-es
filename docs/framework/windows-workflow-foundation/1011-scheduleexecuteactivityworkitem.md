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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 498752bfc896891a43a6a2e7a8245c508795c1ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="ffe5e-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="ffe5e-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ffe5e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ffe5e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ffe5e-104">Id.</span><span class="sxs-lookup"><span data-stu-id="ffe5e-104">ID</span></span>|<span data-ttu-id="ffe5e-105">1011</span><span class="sxs-lookup"><span data-stu-id="ffe5e-105">1011</span></span>|  
|<span data-ttu-id="ffe5e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ffe5e-106">Keywords</span></span>|<span data-ttu-id="ffe5e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ffe5e-107">WFRuntime</span></span>|  
|<span data-ttu-id="ffe5e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ffe5e-108">Level</span></span>|<span data-ttu-id="ffe5e-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="ffe5e-109">Verbose</span></span>|  
|<span data-ttu-id="ffe5e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ffe5e-110">Channel</span></span>|<span data-ttu-id="ffe5e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ffe5e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ffe5e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ffe5e-112">Description</span></span>  
 <span data-ttu-id="ffe5e-113">Indica que se ha programado un ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="ffe5e-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ffe5e-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="ffe5e-114">Message</span></span>  
 <span data-ttu-id="ffe5e-115">Un ExecuteActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="ffe5e-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ffe5e-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="ffe5e-116">Details</span></span>  
  
|<span data-ttu-id="ffe5e-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ffe5e-117">Data Item Name</span></span>|<span data-ttu-id="ffe5e-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ffe5e-118">Data Item Type</span></span>|<span data-ttu-id="ffe5e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="ffe5e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ffe5e-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="ffe5e-120">Activity</span></span>|<span data-ttu-id="ffe5e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ffe5e-121">xs:string</span></span>|<span data-ttu-id="ffe5e-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ffe5e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ffe5e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ffe5e-123">DisplayName</span></span>|<span data-ttu-id="ffe5e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ffe5e-124">xs:string</span></span>|<span data-ttu-id="ffe5e-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ffe5e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ffe5e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ffe5e-126">InstanceId</span></span>|<span data-ttu-id="ffe5e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ffe5e-127">xs:string</span></span>|<span data-ttu-id="ffe5e-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ffe5e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ffe5e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ffe5e-129">AppDomain</span></span>|<span data-ttu-id="ffe5e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ffe5e-130">xs:string</span></span>|<span data-ttu-id="ffe5e-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ffe5e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
