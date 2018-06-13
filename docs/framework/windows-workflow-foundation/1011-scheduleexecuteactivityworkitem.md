---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 299d09b7c4db94a2e27378ba0cc3dfeb03734ab4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509621"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="80c97-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="80c97-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="80c97-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="80c97-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="80c97-104">Id.</span><span class="sxs-lookup"><span data-stu-id="80c97-104">ID</span></span>|<span data-ttu-id="80c97-105">1011</span><span class="sxs-lookup"><span data-stu-id="80c97-105">1011</span></span>|  
|<span data-ttu-id="80c97-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="80c97-106">Keywords</span></span>|<span data-ttu-id="80c97-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="80c97-107">WFRuntime</span></span>|  
|<span data-ttu-id="80c97-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="80c97-108">Level</span></span>|<span data-ttu-id="80c97-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="80c97-109">Verbose</span></span>|  
|<span data-ttu-id="80c97-110">Canal</span><span class="sxs-lookup"><span data-stu-id="80c97-110">Channel</span></span>|<span data-ttu-id="80c97-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="80c97-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="80c97-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="80c97-112">Description</span></span>  
 <span data-ttu-id="80c97-113">Indica que se ha programado un ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="80c97-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="80c97-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="80c97-114">Message</span></span>  
 <span data-ttu-id="80c97-115">Un ExecuteActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="80c97-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="80c97-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="80c97-116">Details</span></span>  
  
|<span data-ttu-id="80c97-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="80c97-117">Data Item Name</span></span>|<span data-ttu-id="80c97-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="80c97-118">Data Item Type</span></span>|<span data-ttu-id="80c97-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="80c97-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="80c97-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="80c97-120">Activity</span></span>|<span data-ttu-id="80c97-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="80c97-121">xs:string</span></span>|<span data-ttu-id="80c97-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="80c97-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="80c97-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="80c97-123">DisplayName</span></span>|<span data-ttu-id="80c97-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="80c97-124">xs:string</span></span>|<span data-ttu-id="80c97-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="80c97-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="80c97-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="80c97-126">InstanceId</span></span>|<span data-ttu-id="80c97-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="80c97-127">xs:string</span></span>|<span data-ttu-id="80c97-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="80c97-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="80c97-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="80c97-129">AppDomain</span></span>|<span data-ttu-id="80c97-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="80c97-130">xs:string</span></span>|<span data-ttu-id="80c97-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="80c97-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
