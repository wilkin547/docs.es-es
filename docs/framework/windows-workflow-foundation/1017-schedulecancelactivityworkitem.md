---
title: 1017 - ScheduleCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c6d348ec18b4d5eff7156d1e9809eb793ac1681d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="7a278-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="7a278-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="7a278-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7a278-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7a278-104">Id.</span><span class="sxs-lookup"><span data-stu-id="7a278-104">ID</span></span>|<span data-ttu-id="7a278-105">1017</span><span class="sxs-lookup"><span data-stu-id="7a278-105">1017</span></span>|  
|<span data-ttu-id="7a278-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="7a278-106">Keywords</span></span>|<span data-ttu-id="7a278-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7a278-107">WFRuntime</span></span>|  
|<span data-ttu-id="7a278-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="7a278-108">Level</span></span>|<span data-ttu-id="7a278-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="7a278-109">Verbose</span></span>|  
|<span data-ttu-id="7a278-110">Canal</span><span class="sxs-lookup"><span data-stu-id="7a278-110">Channel</span></span>|<span data-ttu-id="7a278-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7a278-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7a278-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a278-112">Description</span></span>  
 <span data-ttu-id="7a278-113">Indica que se ha programado un CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="7a278-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7a278-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="7a278-114">Message</span></span>  
 <span data-ttu-id="7a278-115">Un CancelActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="7a278-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7a278-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="7a278-116">Details</span></span>  
  
|<span data-ttu-id="7a278-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7a278-117">Data Item Name</span></span>|<span data-ttu-id="7a278-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7a278-118">Data Item Type</span></span>|<span data-ttu-id="7a278-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a278-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7a278-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="7a278-120">Activity</span></span>|<span data-ttu-id="7a278-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7a278-121">xs:string</span></span>|<span data-ttu-id="7a278-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7a278-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="7a278-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7a278-123">DisplayName</span></span>|<span data-ttu-id="7a278-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7a278-124">xs:string</span></span>|<span data-ttu-id="7a278-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7a278-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="7a278-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="7a278-126">InstanceId</span></span>|<span data-ttu-id="7a278-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7a278-127">xs:string</span></span>|<span data-ttu-id="7a278-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7a278-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="7a278-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7a278-129">AppDomain</span></span>|<span data-ttu-id="7a278-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="7a278-130">xs:string</span></span>|<span data-ttu-id="7a278-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7a278-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
