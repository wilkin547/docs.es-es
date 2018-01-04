---
title: 1018 - StartCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d64d18474ff867ee5679e07c18a288f07185f60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="884a7-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="884a7-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="884a7-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="884a7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="884a7-104">Id.</span><span class="sxs-lookup"><span data-stu-id="884a7-104">ID</span></span>|<span data-ttu-id="884a7-105">1018</span><span class="sxs-lookup"><span data-stu-id="884a7-105">1018</span></span>|  
|<span data-ttu-id="884a7-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="884a7-106">Keywords</span></span>|<span data-ttu-id="884a7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="884a7-107">WFRuntime</span></span>|  
|<span data-ttu-id="884a7-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="884a7-108">Level</span></span>|<span data-ttu-id="884a7-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="884a7-109">Verbose</span></span>|  
|<span data-ttu-id="884a7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="884a7-110">Channel</span></span>|<span data-ttu-id="884a7-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="884a7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="884a7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="884a7-112">Description</span></span>  
 <span data-ttu-id="884a7-113">Indica que un CancelActivityWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="884a7-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="884a7-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="884a7-114">Message</span></span>  
 <span data-ttu-id="884a7-115">Iniciando la ejecución de un CancelActivityWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="884a7-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="884a7-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="884a7-116">Details</span></span>  
  
|<span data-ttu-id="884a7-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="884a7-117">Data Item Name</span></span>|<span data-ttu-id="884a7-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="884a7-118">Data Item Type</span></span>|<span data-ttu-id="884a7-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="884a7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="884a7-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="884a7-120">Activity</span></span>|<span data-ttu-id="884a7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="884a7-121">xs:string</span></span>|<span data-ttu-id="884a7-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="884a7-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="884a7-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="884a7-123">DisplayName</span></span>|<span data-ttu-id="884a7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="884a7-124">xs:string</span></span>|<span data-ttu-id="884a7-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="884a7-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="884a7-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="884a7-126">InstanceId</span></span>|<span data-ttu-id="884a7-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="884a7-127">xs:string</span></span>|<span data-ttu-id="884a7-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="884a7-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="884a7-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="884a7-129">AppDomain</span></span>|<span data-ttu-id="884a7-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="884a7-130">xs:string</span></span>|<span data-ttu-id="884a7-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="884a7-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
