---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: 46a3dc8d313ec72ac90abc2e2e333b274dad2e4c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294305"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="c3b14-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="c3b14-102">1033 - StartRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="c3b14-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c3b14-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3b14-104">ID</span><span class="sxs-lookup"><span data-stu-id="c3b14-104">ID</span></span>|<span data-ttu-id="c3b14-105">3082</span><span class="sxs-lookup"><span data-stu-id="c3b14-105">1033</span></span>|  
|<span data-ttu-id="c3b14-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c3b14-106">Keywords</span></span>|<span data-ttu-id="c3b14-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c3b14-107">WFRuntime</span></span>|  
|<span data-ttu-id="c3b14-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="c3b14-108">Level</span></span>|<span data-ttu-id="c3b14-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="c3b14-109">Verbose</span></span>|  
|<span data-ttu-id="c3b14-110">Canal</span><span class="sxs-lookup"><span data-stu-id="c3b14-110">Channel</span></span>|<span data-ttu-id="c3b14-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c3b14-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c3b14-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3b14-112">Description</span></span>  

 <span data-ttu-id="c3b14-113">Indica que un RuntimeWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c3b14-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c3b14-114">Message</span><span class="sxs-lookup"><span data-stu-id="c3b14-114">Message</span></span>  

 <span data-ttu-id="c3b14-115">Iniciando la ejecución de un elemento de trabajo de runtime para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="c3b14-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c3b14-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="c3b14-116">Details</span></span>  
  
|<span data-ttu-id="c3b14-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c3b14-117">Data Item Name</span></span>|<span data-ttu-id="c3b14-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c3b14-118">Data Item Type</span></span>|<span data-ttu-id="c3b14-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3b14-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c3b14-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="c3b14-120">Activity</span></span>|<span data-ttu-id="c3b14-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3b14-121">xs:string</span></span>|<span data-ttu-id="c3b14-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="c3b14-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="c3b14-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c3b14-123">DisplayName</span></span>|<span data-ttu-id="c3b14-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3b14-124">xs:string</span></span>|<span data-ttu-id="c3b14-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="c3b14-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="c3b14-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c3b14-126">InstanceId</span></span>|<span data-ttu-id="c3b14-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3b14-127">xs:string</span></span>|<span data-ttu-id="c3b14-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="c3b14-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c3b14-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c3b14-129">AppDomain</span></span>|<span data-ttu-id="c3b14-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3b14-130">xs:string</span></span>|<span data-ttu-id="c3b14-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c3b14-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
