---
title: 1010 - ActivityCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1378ddd1550db614c9eddc44f79b19ff94ed585c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="96422-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="96422-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="96422-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="96422-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96422-104">Id.</span><span class="sxs-lookup"><span data-stu-id="96422-104">ID</span></span>|<span data-ttu-id="96422-105">1010</span><span class="sxs-lookup"><span data-stu-id="96422-105">1010</span></span>|  
|<span data-ttu-id="96422-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="96422-106">Keywords</span></span>|<span data-ttu-id="96422-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="96422-107">WFRuntime</span></span>|  
|<span data-ttu-id="96422-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="96422-108">Level</span></span>|<span data-ttu-id="96422-109">Información</span><span class="sxs-lookup"><span data-stu-id="96422-109">Information</span></span>|  
|<span data-ttu-id="96422-110">Canal</span><span class="sxs-lookup"><span data-stu-id="96422-110">Channel</span></span>|<span data-ttu-id="96422-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="96422-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="96422-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="96422-112">Description</span></span>  
 <span data-ttu-id="96422-113">Indica que una actividad ha completado su ejecución.</span><span class="sxs-lookup"><span data-stu-id="96422-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="96422-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="96422-114">Message</span></span>  
 <span data-ttu-id="96422-115">Actividad “%1", DisplayName: “%2 ", InstanceId: “%3 " se ha completado en el estado “%4".</span><span class="sxs-lookup"><span data-stu-id="96422-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="96422-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="96422-116">Details</span></span>  
  
|<span data-ttu-id="96422-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="96422-117">Data Item Name</span></span>|<span data-ttu-id="96422-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="96422-118">Data Item Type</span></span>|<span data-ttu-id="96422-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="96422-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="96422-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="96422-120">Activity</span></span>|<span data-ttu-id="96422-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="96422-121">xs:string</span></span>|<span data-ttu-id="96422-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="96422-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="96422-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="96422-123">DisplayName</span></span>|<span data-ttu-id="96422-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="96422-124">xs:string</span></span>|<span data-ttu-id="96422-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="96422-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="96422-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="96422-126">InstanceId</span></span>|<span data-ttu-id="96422-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="96422-127">xs:string</span></span>|<span data-ttu-id="96422-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="96422-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="96422-129">Estado</span><span class="sxs-lookup"><span data-stu-id="96422-129">State</span></span>|<span data-ttu-id="96422-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="96422-130">xs:string</span></span>|<span data-ttu-id="96422-131">Estado de la actividad.</span><span class="sxs-lookup"><span data-stu-id="96422-131">The state of the activity.</span></span>|  
|<span data-ttu-id="96422-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="96422-132">AppDomain</span></span>|<span data-ttu-id="96422-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="96422-133">xs:string</span></span>|<span data-ttu-id="96422-134">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="96422-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
