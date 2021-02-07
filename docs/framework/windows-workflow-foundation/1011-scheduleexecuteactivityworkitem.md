---
description: 'Más información acerca de: 1011-ScheduleExecuteActivityWorkItem'
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 81010390de2ad01ec3063f2ac89608b97dcb713e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703359"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="b792d-103">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="b792d-103">1011 - ScheduleExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="b792d-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b792d-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b792d-105">Id.</span><span class="sxs-lookup"><span data-stu-id="b792d-105">ID</span></span>|<span data-ttu-id="b792d-106">1011</span><span class="sxs-lookup"><span data-stu-id="b792d-106">1011</span></span>|  
|<span data-ttu-id="b792d-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b792d-107">Keywords</span></span>|<span data-ttu-id="b792d-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b792d-108">WFRuntime</span></span>|  
|<span data-ttu-id="b792d-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="b792d-109">Level</span></span>|<span data-ttu-id="b792d-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="b792d-110">Verbose</span></span>|  
|<span data-ttu-id="b792d-111">Canal</span><span class="sxs-lookup"><span data-stu-id="b792d-111">Channel</span></span>|<span data-ttu-id="b792d-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b792d-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b792d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b792d-113">Description</span></span>  

 <span data-ttu-id="b792d-114">Indica que se ha programado un ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="b792d-114">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b792d-115">Message</span><span class="sxs-lookup"><span data-stu-id="b792d-115">Message</span></span>  

 <span data-ttu-id="b792d-116">Un ExecuteActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="b792d-116">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b792d-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="b792d-117">Details</span></span>  
  
|<span data-ttu-id="b792d-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b792d-118">Data Item Name</span></span>|<span data-ttu-id="b792d-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b792d-119">Data Item Type</span></span>|<span data-ttu-id="b792d-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b792d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b792d-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="b792d-121">Activity</span></span>|<span data-ttu-id="b792d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b792d-122">xs:string</span></span>|<span data-ttu-id="b792d-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b792d-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="b792d-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b792d-124">DisplayName</span></span>|<span data-ttu-id="b792d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b792d-125">xs:string</span></span>|<span data-ttu-id="b792d-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b792d-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="b792d-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b792d-127">InstanceId</span></span>|<span data-ttu-id="b792d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b792d-128">xs:string</span></span>|<span data-ttu-id="b792d-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b792d-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b792d-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b792d-130">AppDomain</span></span>|<span data-ttu-id="b792d-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b792d-131">xs:string</span></span>|<span data-ttu-id="b792d-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b792d-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
