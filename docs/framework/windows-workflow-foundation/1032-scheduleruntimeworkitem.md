---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: da35201f2b3e3bc07e0b9139b0584ce37011e168
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294318"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="d8d65-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="d8d65-102">1032 - ScheduleRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="d8d65-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d8d65-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8d65-104">ID</span><span class="sxs-lookup"><span data-stu-id="d8d65-104">ID</span></span>|<span data-ttu-id="d8d65-105">1032</span><span class="sxs-lookup"><span data-stu-id="d8d65-105">1032</span></span>|  
|<span data-ttu-id="d8d65-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d8d65-106">Keywords</span></span>|<span data-ttu-id="d8d65-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d8d65-107">WFRuntime</span></span>|  
|<span data-ttu-id="d8d65-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d8d65-108">Level</span></span>|<span data-ttu-id="d8d65-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="d8d65-109">Verbose</span></span>|  
|<span data-ttu-id="d8d65-110">Canal</span><span class="sxs-lookup"><span data-stu-id="d8d65-110">Channel</span></span>|<span data-ttu-id="d8d65-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d8d65-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d8d65-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8d65-112">Description</span></span>  

 <span data-ttu-id="d8d65-113">Indica que se ha programado un RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="d8d65-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d8d65-114">Message</span><span class="sxs-lookup"><span data-stu-id="d8d65-114">Message</span></span>  

 <span data-ttu-id="d8d65-115">Se ha programado un elemento de trabajo en runtime para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="d8d65-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d8d65-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="d8d65-116">Details</span></span>  
  
|<span data-ttu-id="d8d65-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d8d65-117">Data Item Name</span></span>|<span data-ttu-id="d8d65-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d8d65-118">Data Item Type</span></span>|<span data-ttu-id="d8d65-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8d65-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d8d65-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="d8d65-120">Activity</span></span>|<span data-ttu-id="d8d65-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8d65-121">xs:string</span></span>|<span data-ttu-id="d8d65-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d8d65-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="d8d65-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d8d65-123">DisplayName</span></span>|<span data-ttu-id="d8d65-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8d65-124">xs:string</span></span>|<span data-ttu-id="d8d65-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d8d65-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="d8d65-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d8d65-126">InstanceId</span></span>|<span data-ttu-id="d8d65-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8d65-127">xs:string</span></span>|<span data-ttu-id="d8d65-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d8d65-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d8d65-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d8d65-129">AppDomain</span></span>|<span data-ttu-id="d8d65-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8d65-130">xs:string</span></span>|<span data-ttu-id="d8d65-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d8d65-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
