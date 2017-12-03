---
title: 1012 - StartExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a06cec1ab251b8f7e82aef71589bd56e5f55f2e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="57a52-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="57a52-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="57a52-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="57a52-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57a52-104">Id.</span><span class="sxs-lookup"><span data-stu-id="57a52-104">ID</span></span>|<span data-ttu-id="57a52-105">1012</span><span class="sxs-lookup"><span data-stu-id="57a52-105">1012</span></span>|  
|<span data-ttu-id="57a52-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="57a52-106">Keywords</span></span>|<span data-ttu-id="57a52-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="57a52-107">WFRuntime</span></span>|  
|<span data-ttu-id="57a52-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="57a52-108">Level</span></span>|<span data-ttu-id="57a52-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="57a52-109">Verbose</span></span>|  
|<span data-ttu-id="57a52-110">Canal</span><span class="sxs-lookup"><span data-stu-id="57a52-110">Channel</span></span>|<span data-ttu-id="57a52-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="57a52-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="57a52-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="57a52-112">Description</span></span>  
 <span data-ttu-id="57a52-113">Indica que un ExecuteActivityWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="57a52-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="57a52-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="57a52-114">Message</span></span>  
 <span data-ttu-id="57a52-115">Iniciando la ejecución de un ExecuteActivityWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="57a52-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="57a52-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="57a52-116">Details</span></span>  
  
|<span data-ttu-id="57a52-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="57a52-117">Data Item Name</span></span>|<span data-ttu-id="57a52-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="57a52-118">Data Item Type</span></span>|<span data-ttu-id="57a52-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="57a52-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="57a52-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="57a52-120">Activity</span></span>|<span data-ttu-id="57a52-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="57a52-121">xs:string</span></span>|<span data-ttu-id="57a52-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="57a52-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="57a52-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="57a52-123">DisplayName</span></span>|<span data-ttu-id="57a52-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="57a52-124">xs:string</span></span>|<span data-ttu-id="57a52-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="57a52-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="57a52-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="57a52-126">InstanceId</span></span>|<span data-ttu-id="57a52-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="57a52-127">xs:string</span></span>|<span data-ttu-id="57a52-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="57a52-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="57a52-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="57a52-129">AppDomain</span></span>|<span data-ttu-id="57a52-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="57a52-130">xs:string</span></span>|<span data-ttu-id="57a52-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="57a52-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
