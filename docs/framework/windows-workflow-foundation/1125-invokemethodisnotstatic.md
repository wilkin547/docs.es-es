---
title: 1125 - InvokeMethodIsNotStatic
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b31bb8db8252474d20f7523e08cadf35bfcc84a8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="56b7d-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="56b7d-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="56b7d-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="56b7d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56b7d-104">Id.</span><span class="sxs-lookup"><span data-stu-id="56b7d-104">ID</span></span>|<span data-ttu-id="56b7d-105">1125</span><span class="sxs-lookup"><span data-stu-id="56b7d-105">1125</span></span>|  
|<span data-ttu-id="56b7d-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="56b7d-106">Keywords</span></span>|<span data-ttu-id="56b7d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="56b7d-107">WFRuntime</span></span>|  
|<span data-ttu-id="56b7d-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="56b7d-108">Level</span></span>|<span data-ttu-id="56b7d-109">Información</span><span class="sxs-lookup"><span data-stu-id="56b7d-109">Information</span></span>|  
|<span data-ttu-id="56b7d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="56b7d-110">Channel</span></span>|<span data-ttu-id="56b7d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="56b7d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="56b7d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="56b7d-112">Description</span></span>  
 <span data-ttu-id="56b7d-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que el método que se va a invocar no es estático.</span><span class="sxs-lookup"><span data-stu-id="56b7d-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="56b7d-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="56b7d-114">Message</span></span>  
 <span data-ttu-id="56b7d-115">InvokeMethod '%1': el método no es estático.</span><span class="sxs-lookup"><span data-stu-id="56b7d-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="56b7d-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="56b7d-116">Details</span></span>  
  
|<span data-ttu-id="56b7d-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="56b7d-117">Data Item Name</span></span>|<span data-ttu-id="56b7d-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="56b7d-118">Data Item Type</span></span>|<span data-ttu-id="56b7d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="56b7d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="56b7d-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="56b7d-120">InvokeMethod</span></span>|<span data-ttu-id="56b7d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="56b7d-121">xs:string</span></span>|<span data-ttu-id="56b7d-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="56b7d-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="56b7d-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="56b7d-123">AppDomain</span></span>|<span data-ttu-id="56b7d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="56b7d-124">xs:string</span></span>|<span data-ttu-id="56b7d-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="56b7d-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
