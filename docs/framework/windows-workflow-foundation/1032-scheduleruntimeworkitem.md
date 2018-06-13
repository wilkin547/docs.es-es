---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: 505b852d54e256b2c2bfff8d90944dd4e993e0c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510252"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="b41fb-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="b41fb-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b41fb-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b41fb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b41fb-104">Id.</span><span class="sxs-lookup"><span data-stu-id="b41fb-104">ID</span></span>|<span data-ttu-id="b41fb-105">1032</span><span class="sxs-lookup"><span data-stu-id="b41fb-105">1032</span></span>|  
|<span data-ttu-id="b41fb-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b41fb-106">Keywords</span></span>|<span data-ttu-id="b41fb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b41fb-107">WFRuntime</span></span>|  
|<span data-ttu-id="b41fb-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b41fb-108">Level</span></span>|<span data-ttu-id="b41fb-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="b41fb-109">Verbose</span></span>|  
|<span data-ttu-id="b41fb-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b41fb-110">Channel</span></span>|<span data-ttu-id="b41fb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b41fb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b41fb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b41fb-112">Description</span></span>  
 <span data-ttu-id="b41fb-113">Indica que se ha programado un RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="b41fb-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b41fb-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b41fb-114">Message</span></span>  
 <span data-ttu-id="b41fb-115">Se ha programado un elemento de trabajo en tiempo de ejecución para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="b41fb-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b41fb-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="b41fb-116">Details</span></span>  
  
|<span data-ttu-id="b41fb-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b41fb-117">Data Item Name</span></span>|<span data-ttu-id="b41fb-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b41fb-118">Data Item Type</span></span>|<span data-ttu-id="b41fb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="b41fb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b41fb-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="b41fb-120">Activity</span></span>|<span data-ttu-id="b41fb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41fb-121">xs:string</span></span>|<span data-ttu-id="b41fb-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b41fb-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="b41fb-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b41fb-123">DisplayName</span></span>|<span data-ttu-id="b41fb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41fb-124">xs:string</span></span>|<span data-ttu-id="b41fb-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b41fb-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="b41fb-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b41fb-126">InstanceId</span></span>|<span data-ttu-id="b41fb-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41fb-127">xs:string</span></span>|<span data-ttu-id="b41fb-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b41fb-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b41fb-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b41fb-129">AppDomain</span></span>|<span data-ttu-id="b41fb-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41fb-130">xs:string</span></span>|<span data-ttu-id="b41fb-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b41fb-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
