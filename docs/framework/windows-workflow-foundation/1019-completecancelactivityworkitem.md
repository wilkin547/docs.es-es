---
title: 1019 - CompleteCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9f8af4486d4659afd4c98016a6f88719271f1a1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="34cf2-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="34cf2-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="34cf2-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="34cf2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34cf2-104">Id.</span><span class="sxs-lookup"><span data-stu-id="34cf2-104">ID</span></span>|<span data-ttu-id="34cf2-105">1019</span><span class="sxs-lookup"><span data-stu-id="34cf2-105">1019</span></span>|  
|<span data-ttu-id="34cf2-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="34cf2-106">Keywords</span></span>|<span data-ttu-id="34cf2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="34cf2-107">WFRuntime</span></span>|  
|<span data-ttu-id="34cf2-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="34cf2-108">Level</span></span>|<span data-ttu-id="34cf2-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="34cf2-109">Verbose</span></span>|  
|<span data-ttu-id="34cf2-110">Canal</span><span class="sxs-lookup"><span data-stu-id="34cf2-110">Channel</span></span>|<span data-ttu-id="34cf2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="34cf2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="34cf2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="34cf2-112">Description</span></span>  
 <span data-ttu-id="34cf2-113">Indica que se ha completado un CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="34cf2-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="34cf2-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="34cf2-114">Message</span></span>  
 <span data-ttu-id="34cf2-115">Un CancelActivityWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="34cf2-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="34cf2-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="34cf2-116">Details</span></span>  
  
|<span data-ttu-id="34cf2-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="34cf2-117">Data Item Name</span></span>|<span data-ttu-id="34cf2-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="34cf2-118">Data Item Type</span></span>|<span data-ttu-id="34cf2-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="34cf2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="34cf2-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="34cf2-120">Activity</span></span>|<span data-ttu-id="34cf2-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="34cf2-121">xs:string</span></span>|<span data-ttu-id="34cf2-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="34cf2-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="34cf2-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="34cf2-123">DisplayName</span></span>|<span data-ttu-id="34cf2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="34cf2-124">xs:string</span></span>|<span data-ttu-id="34cf2-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="34cf2-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="34cf2-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="34cf2-126">InstanceId</span></span>|<span data-ttu-id="34cf2-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="34cf2-127">xs:string</span></span>|<span data-ttu-id="34cf2-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="34cf2-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="34cf2-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="34cf2-129">AppDomain</span></span>|<span data-ttu-id="34cf2-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="34cf2-130">xs:string</span></span>|<span data-ttu-id="34cf2-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="34cf2-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
