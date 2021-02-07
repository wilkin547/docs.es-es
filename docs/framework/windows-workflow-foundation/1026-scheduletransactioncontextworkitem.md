---
description: 'Más información acerca de: 1026-ScheduleTransactionContextWorkItem'
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 913af6903d38cea8f5c8d3e6e72dff04ff706195
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755491"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="e27a8-103">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="e27a8-103">1026 - ScheduleTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="e27a8-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e27a8-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e27a8-105">Id.</span><span class="sxs-lookup"><span data-stu-id="e27a8-105">ID</span></span>|<span data-ttu-id="e27a8-106">1026</span><span class="sxs-lookup"><span data-stu-id="e27a8-106">1026</span></span>|  
|<span data-ttu-id="e27a8-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e27a8-107">Keywords</span></span>|<span data-ttu-id="e27a8-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e27a8-108">WFRuntime</span></span>|  
|<span data-ttu-id="e27a8-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="e27a8-109">Level</span></span>|<span data-ttu-id="e27a8-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="e27a8-110">Verbose</span></span>|  
|<span data-ttu-id="e27a8-111">Canal</span><span class="sxs-lookup"><span data-stu-id="e27a8-111">Channel</span></span>|<span data-ttu-id="e27a8-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e27a8-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e27a8-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e27a8-113">Description</span></span>  

 <span data-ttu-id="e27a8-114">Indica que se ha programado una TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="e27a8-114">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e27a8-115">Message</span><span class="sxs-lookup"><span data-stu-id="e27a8-115">Message</span></span>  

 <span data-ttu-id="e27a8-116">Un TransactionContextWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="e27a8-116">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e27a8-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="e27a8-117">Details</span></span>  
  
|<span data-ttu-id="e27a8-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e27a8-118">Data Item Name</span></span>|<span data-ttu-id="e27a8-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e27a8-119">Data Item Type</span></span>|<span data-ttu-id="e27a8-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="e27a8-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e27a8-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="e27a8-121">Activity</span></span>|<span data-ttu-id="e27a8-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="e27a8-122">xs:string</span></span>|<span data-ttu-id="e27a8-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="e27a8-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="e27a8-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e27a8-124">DisplayName</span></span>|<span data-ttu-id="e27a8-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="e27a8-125">xs:string</span></span>|<span data-ttu-id="e27a8-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="e27a8-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="e27a8-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e27a8-127">InstanceId</span></span>|<span data-ttu-id="e27a8-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="e27a8-128">xs:string</span></span>|<span data-ttu-id="e27a8-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="e27a8-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e27a8-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e27a8-130">AppDomain</span></span>|<span data-ttu-id="e27a8-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="e27a8-131">xs:string</span></span>|<span data-ttu-id="e27a8-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e27a8-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
