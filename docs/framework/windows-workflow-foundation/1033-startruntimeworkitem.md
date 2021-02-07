---
description: 'Más información acerca de: 1033-StartRuntimeWorkItem'
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: 31e664070b7592d3350a2f6f84f0493cc8f11ea1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668011"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="4b7dc-103">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="4b7dc-103">1033 - StartRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="4b7dc-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4b7dc-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b7dc-105">Id.</span><span class="sxs-lookup"><span data-stu-id="4b7dc-105">ID</span></span>|<span data-ttu-id="4b7dc-106">3082</span><span class="sxs-lookup"><span data-stu-id="4b7dc-106">1033</span></span>|  
|<span data-ttu-id="4b7dc-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4b7dc-107">Keywords</span></span>|<span data-ttu-id="4b7dc-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4b7dc-108">WFRuntime</span></span>|  
|<span data-ttu-id="4b7dc-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="4b7dc-109">Level</span></span>|<span data-ttu-id="4b7dc-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="4b7dc-110">Verbose</span></span>|  
|<span data-ttu-id="4b7dc-111">Canal</span><span class="sxs-lookup"><span data-stu-id="4b7dc-111">Channel</span></span>|<span data-ttu-id="4b7dc-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4b7dc-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4b7dc-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b7dc-113">Description</span></span>  

 <span data-ttu-id="4b7dc-114">Indica que un RuntimeWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="4b7dc-114">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4b7dc-115">Message</span><span class="sxs-lookup"><span data-stu-id="4b7dc-115">Message</span></span>  

 <span data-ttu-id="4b7dc-116">Iniciando la ejecución de un elemento de trabajo de runtime para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="4b7dc-116">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4b7dc-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="4b7dc-117">Details</span></span>  
  
|<span data-ttu-id="4b7dc-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4b7dc-118">Data Item Name</span></span>|<span data-ttu-id="4b7dc-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4b7dc-119">Data Item Type</span></span>|<span data-ttu-id="4b7dc-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b7dc-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4b7dc-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="4b7dc-121">Activity</span></span>|<span data-ttu-id="4b7dc-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b7dc-122">xs:string</span></span>|<span data-ttu-id="4b7dc-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4b7dc-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="4b7dc-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4b7dc-124">DisplayName</span></span>|<span data-ttu-id="4b7dc-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b7dc-125">xs:string</span></span>|<span data-ttu-id="4b7dc-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4b7dc-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="4b7dc-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4b7dc-127">InstanceId</span></span>|<span data-ttu-id="4b7dc-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b7dc-128">xs:string</span></span>|<span data-ttu-id="4b7dc-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4b7dc-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4b7dc-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4b7dc-130">AppDomain</span></span>|<span data-ttu-id="4b7dc-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b7dc-131">xs:string</span></span>|<span data-ttu-id="4b7dc-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4b7dc-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
