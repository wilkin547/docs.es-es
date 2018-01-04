---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75386b56f7926b9ddb883e0ca212d795898fe6f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="d8ea0-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="d8ea0-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="d8ea0-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d8ea0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8ea0-104">Id.</span><span class="sxs-lookup"><span data-stu-id="d8ea0-104">ID</span></span>|<span data-ttu-id="d8ea0-105">1132</span><span class="sxs-lookup"><span data-stu-id="d8ea0-105">1132</span></span>|  
|<span data-ttu-id="d8ea0-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d8ea0-106">Keywords</span></span>|<span data-ttu-id="d8ea0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d8ea0-107">WFRuntime</span></span>|  
|<span data-ttu-id="d8ea0-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d8ea0-108">Level</span></span>|<span data-ttu-id="d8ea0-109">Información</span><span class="sxs-lookup"><span data-stu-id="d8ea0-109">Information</span></span>|  
|<span data-ttu-id="d8ea0-110">Canal</span><span class="sxs-lookup"><span data-stu-id="d8ea0-110">Channel</span></span>|<span data-ttu-id="d8ea0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d8ea0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d8ea0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8ea0-112">Description</span></span>  
 <span data-ttu-id="d8ea0-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="d8ea0-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d8ea0-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="d8ea0-114">Message</span></span>  
 <span data-ttu-id="d8ea0-115">InvokeMethod '%1': el método no usa un patrón asincrónico.</span><span class="sxs-lookup"><span data-stu-id="d8ea0-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d8ea0-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="d8ea0-116">Details</span></span>  
  
|<span data-ttu-id="d8ea0-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d8ea0-117">Data Item Name</span></span>|<span data-ttu-id="d8ea0-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d8ea0-118">Data Item Type</span></span>|<span data-ttu-id="d8ea0-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8ea0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d8ea0-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="d8ea0-120">InvokeMethod</span></span>|<span data-ttu-id="d8ea0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8ea0-121">xs:string</span></span>|<span data-ttu-id="d8ea0-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="d8ea0-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="d8ea0-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d8ea0-123">AppDomain</span></span>|<span data-ttu-id="d8ea0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8ea0-124">xs:string</span></span>|<span data-ttu-id="d8ea0-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d8ea0-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
