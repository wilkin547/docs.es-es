---
title: 1131 - InvokeMethodUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 739357df85ceb73e246adcb2b09f88d270d853ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="a2fc3-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="a2fc3-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="a2fc3-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a2fc3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2fc3-104">Id.</span><span class="sxs-lookup"><span data-stu-id="a2fc3-104">ID</span></span>|<span data-ttu-id="a2fc3-105">1131</span><span class="sxs-lookup"><span data-stu-id="a2fc3-105">1131</span></span>|  
|<span data-ttu-id="a2fc3-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a2fc3-106">Keywords</span></span>|<span data-ttu-id="a2fc3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a2fc3-107">WFRuntime</span></span>|  
|<span data-ttu-id="a2fc3-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a2fc3-108">Level</span></span>|<span data-ttu-id="a2fc3-109">Información</span><span class="sxs-lookup"><span data-stu-id="a2fc3-109">Information</span></span>|  
|<span data-ttu-id="a2fc3-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a2fc3-110">Channel</span></span>|<span data-ttu-id="a2fc3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a2fc3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a2fc3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2fc3-112">Description</span></span>  
 <span data-ttu-id="a2fc3-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="a2fc3-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a2fc3-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a2fc3-114">Message</span></span>  
 <span data-ttu-id="a2fc3-115">InvokeMethod '%1': el método usa el patrón asincrónico de '%2' y '%3'.</span><span class="sxs-lookup"><span data-stu-id="a2fc3-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a2fc3-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="a2fc3-116">Details</span></span>  
  
|<span data-ttu-id="a2fc3-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a2fc3-117">Data Item Name</span></span>|<span data-ttu-id="a2fc3-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a2fc3-118">Data Item Type</span></span>|<span data-ttu-id="a2fc3-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2fc3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a2fc3-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="a2fc3-120">InvokeMethod</span></span>|<span data-ttu-id="a2fc3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2fc3-121">xs:string</span></span>|<span data-ttu-id="a2fc3-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="a2fc3-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="a2fc3-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="a2fc3-123">BeginMethod</span></span>|<span data-ttu-id="a2fc3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2fc3-124">xs:string</span></span>|<span data-ttu-id="a2fc3-125">Nombre del método de inicio.</span><span class="sxs-lookup"><span data-stu-id="a2fc3-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="a2fc3-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="a2fc3-126">EndMethod</span></span>|<span data-ttu-id="a2fc3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2fc3-127">xs:string</span></span>|<span data-ttu-id="a2fc3-128">Nombre del método de fin.</span><span class="sxs-lookup"><span data-stu-id="a2fc3-128">The name of the end method.</span></span>|  
|<span data-ttu-id="a2fc3-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a2fc3-129">AppDomain</span></span>|<span data-ttu-id="a2fc3-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a2fc3-130">xs:string</span></span>|<span data-ttu-id="a2fc3-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a2fc3-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
