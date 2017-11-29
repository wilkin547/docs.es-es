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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 300e843529bfc76df4193b46cd713ce0bd9cdbfd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="a6d3f-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="a6d3f-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="a6d3f-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a6d3f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6d3f-104">Id.</span><span class="sxs-lookup"><span data-stu-id="a6d3f-104">ID</span></span>|<span data-ttu-id="a6d3f-105">1132</span><span class="sxs-lookup"><span data-stu-id="a6d3f-105">1132</span></span>|  
|<span data-ttu-id="a6d3f-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a6d3f-106">Keywords</span></span>|<span data-ttu-id="a6d3f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a6d3f-107">WFRuntime</span></span>|  
|<span data-ttu-id="a6d3f-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a6d3f-108">Level</span></span>|<span data-ttu-id="a6d3f-109">Información</span><span class="sxs-lookup"><span data-stu-id="a6d3f-109">Information</span></span>|  
|<span data-ttu-id="a6d3f-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a6d3f-110">Channel</span></span>|<span data-ttu-id="a6d3f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a6d3f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a6d3f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6d3f-112">Description</span></span>  
 <span data-ttu-id="a6d3f-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="a6d3f-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a6d3f-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a6d3f-114">Message</span></span>  
 <span data-ttu-id="a6d3f-115">InvokeMethod '%1': el método no usa un patrón asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a6d3f-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a6d3f-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="a6d3f-116">Details</span></span>  
  
|<span data-ttu-id="a6d3f-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a6d3f-117">Data Item Name</span></span>|<span data-ttu-id="a6d3f-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a6d3f-118">Data Item Type</span></span>|<span data-ttu-id="a6d3f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6d3f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a6d3f-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="a6d3f-120">InvokeMethod</span></span>|<span data-ttu-id="a6d3f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6d3f-121">xs:string</span></span>|<span data-ttu-id="a6d3f-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="a6d3f-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="a6d3f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a6d3f-123">AppDomain</span></span>|<span data-ttu-id="a6d3f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6d3f-124">xs:string</span></span>|<span data-ttu-id="a6d3f-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a6d3f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
