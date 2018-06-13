---
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: 355281e6aa8f621bd2f9c0862e641fafec872750
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509702"
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="e117e-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="e117e-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="e117e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e117e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e117e-104">Id.</span><span class="sxs-lookup"><span data-stu-id="e117e-104">ID</span></span>|<span data-ttu-id="e117e-105">1010</span><span class="sxs-lookup"><span data-stu-id="e117e-105">1010</span></span>|  
|<span data-ttu-id="e117e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e117e-106">Keywords</span></span>|<span data-ttu-id="e117e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e117e-107">WFRuntime</span></span>|  
|<span data-ttu-id="e117e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="e117e-108">Level</span></span>|<span data-ttu-id="e117e-109">Información</span><span class="sxs-lookup"><span data-stu-id="e117e-109">Information</span></span>|  
|<span data-ttu-id="e117e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e117e-110">Channel</span></span>|<span data-ttu-id="e117e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e117e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e117e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e117e-112">Description</span></span>  
 <span data-ttu-id="e117e-113">Indica que una actividad ha completado su ejecución.</span><span class="sxs-lookup"><span data-stu-id="e117e-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e117e-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="e117e-114">Message</span></span>  
 <span data-ttu-id="e117e-115">Actividad “%1", DisplayName: “%2 ", InstanceId: “%3 " se ha completado en el estado “%4".</span><span class="sxs-lookup"><span data-stu-id="e117e-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e117e-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="e117e-116">Details</span></span>  
  
|<span data-ttu-id="e117e-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e117e-117">Data Item Name</span></span>|<span data-ttu-id="e117e-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e117e-118">Data Item Type</span></span>|<span data-ttu-id="e117e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e117e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e117e-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="e117e-120">Activity</span></span>|<span data-ttu-id="e117e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e117e-121">xs:string</span></span>|<span data-ttu-id="e117e-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="e117e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="e117e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e117e-123">DisplayName</span></span>|<span data-ttu-id="e117e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e117e-124">xs:string</span></span>|<span data-ttu-id="e117e-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="e117e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="e117e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e117e-126">InstanceId</span></span>|<span data-ttu-id="e117e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e117e-127">xs:string</span></span>|<span data-ttu-id="e117e-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="e117e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e117e-129">Estado</span><span class="sxs-lookup"><span data-stu-id="e117e-129">State</span></span>|<span data-ttu-id="e117e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e117e-130">xs:string</span></span>|<span data-ttu-id="e117e-131">Estado de la actividad.</span><span class="sxs-lookup"><span data-stu-id="e117e-131">The state of the activity.</span></span>|  
|<span data-ttu-id="e117e-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e117e-132">AppDomain</span></span>|<span data-ttu-id="e117e-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="e117e-133">xs:string</span></span>|<span data-ttu-id="e117e-134">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e117e-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
