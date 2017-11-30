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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f74a133a685699bcefc014269a9ecb3ebea4e505
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="00225-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="00225-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="00225-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="00225-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00225-104">Id.</span><span class="sxs-lookup"><span data-stu-id="00225-104">ID</span></span>|<span data-ttu-id="00225-105">1018</span><span class="sxs-lookup"><span data-stu-id="00225-105">1018</span></span>|  
|<span data-ttu-id="00225-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="00225-106">Keywords</span></span>|<span data-ttu-id="00225-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="00225-107">WFRuntime</span></span>|  
|<span data-ttu-id="00225-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="00225-108">Level</span></span>|<span data-ttu-id="00225-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="00225-109">Verbose</span></span>|  
|<span data-ttu-id="00225-110">Canal</span><span class="sxs-lookup"><span data-stu-id="00225-110">Channel</span></span>|<span data-ttu-id="00225-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="00225-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="00225-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="00225-112">Description</span></span>  
 <span data-ttu-id="00225-113">Indica que un CancelActivityWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="00225-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="00225-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="00225-114">Message</span></span>  
 <span data-ttu-id="00225-115">Iniciando la ejecución de un CancelActivityWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="00225-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="00225-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="00225-116">Details</span></span>  
  
|<span data-ttu-id="00225-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="00225-117">Data Item Name</span></span>|<span data-ttu-id="00225-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="00225-118">Data Item Type</span></span>|<span data-ttu-id="00225-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="00225-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="00225-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="00225-120">Activity</span></span>|<span data-ttu-id="00225-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="00225-121">xs:string</span></span>|<span data-ttu-id="00225-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="00225-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="00225-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="00225-123">DisplayName</span></span>|<span data-ttu-id="00225-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="00225-124">xs:string</span></span>|<span data-ttu-id="00225-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="00225-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="00225-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="00225-126">InstanceId</span></span>|<span data-ttu-id="00225-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="00225-127">xs:string</span></span>|<span data-ttu-id="00225-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="00225-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="00225-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="00225-129">AppDomain</span></span>|<span data-ttu-id="00225-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="00225-130">xs:string</span></span>|<span data-ttu-id="00225-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="00225-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
