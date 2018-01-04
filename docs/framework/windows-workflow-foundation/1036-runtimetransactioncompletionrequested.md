---
title: 1036 - RuntimeTransactionCompletionRequested
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 91fcac0bdfe885051941d100f1a2c131c547f19e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="aa16b-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="aa16b-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="aa16b-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="aa16b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa16b-104">Id.</span><span class="sxs-lookup"><span data-stu-id="aa16b-104">ID</span></span>|<span data-ttu-id="aa16b-105">1036</span><span class="sxs-lookup"><span data-stu-id="aa16b-105">1036</span></span>|  
|<span data-ttu-id="aa16b-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="aa16b-106">Keywords</span></span>|<span data-ttu-id="aa16b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="aa16b-107">WFRuntime</span></span>|  
|<span data-ttu-id="aa16b-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="aa16b-108">Level</span></span>|<span data-ttu-id="aa16b-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="aa16b-109">Verbose</span></span>|  
|<span data-ttu-id="aa16b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="aa16b-110">Channel</span></span>|<span data-ttu-id="aa16b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="aa16b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aa16b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa16b-112">Description</span></span>  
 <span data-ttu-id="aa16b-113">Indica que una actividad ha programado la finalización de la transacción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa16b-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aa16b-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="aa16b-114">Message</span></span>  
 <span data-ttu-id="aa16b-115">La actividad '%1', DisplayName: '%2', InstanceId: '%3' ha programado la finalización de la transacción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa16b-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aa16b-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="aa16b-116">Details</span></span>  
  
|<span data-ttu-id="aa16b-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="aa16b-117">Data Item Name</span></span>|<span data-ttu-id="aa16b-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="aa16b-118">Data Item Type</span></span>|<span data-ttu-id="aa16b-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa16b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aa16b-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="aa16b-120">Activity</span></span>|<span data-ttu-id="aa16b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa16b-121">xs:string</span></span>|<span data-ttu-id="aa16b-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="aa16b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="aa16b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="aa16b-123">DisplayName</span></span>|<span data-ttu-id="aa16b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa16b-124">xs:string</span></span>|<span data-ttu-id="aa16b-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="aa16b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="aa16b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="aa16b-126">InstanceId</span></span>|<span data-ttu-id="aa16b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa16b-127">xs:string</span></span>|<span data-ttu-id="aa16b-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="aa16b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="aa16b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aa16b-129">AppDomain</span></span>|<span data-ttu-id="aa16b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa16b-130">xs:string</span></span>|<span data-ttu-id="aa16b-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="aa16b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
