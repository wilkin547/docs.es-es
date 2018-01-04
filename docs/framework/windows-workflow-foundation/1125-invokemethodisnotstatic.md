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
ms.workload: dotnet
ms.openlocfilehash: c8b5e255e9a753c6476a070609b0cbda189d37a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="bea33-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="bea33-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="bea33-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bea33-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bea33-104">Id.</span><span class="sxs-lookup"><span data-stu-id="bea33-104">ID</span></span>|<span data-ttu-id="bea33-105">1125</span><span class="sxs-lookup"><span data-stu-id="bea33-105">1125</span></span>|  
|<span data-ttu-id="bea33-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="bea33-106">Keywords</span></span>|<span data-ttu-id="bea33-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bea33-107">WFRuntime</span></span>|  
|<span data-ttu-id="bea33-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="bea33-108">Level</span></span>|<span data-ttu-id="bea33-109">Información</span><span class="sxs-lookup"><span data-stu-id="bea33-109">Information</span></span>|  
|<span data-ttu-id="bea33-110">Canal</span><span class="sxs-lookup"><span data-stu-id="bea33-110">Channel</span></span>|<span data-ttu-id="bea33-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bea33-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bea33-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bea33-112">Description</span></span>  
 <span data-ttu-id="bea33-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que el método que se va a invocar no es estático.</span><span class="sxs-lookup"><span data-stu-id="bea33-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bea33-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="bea33-114">Message</span></span>  
 <span data-ttu-id="bea33-115">InvokeMethod '%1': el método no es estático.</span><span class="sxs-lookup"><span data-stu-id="bea33-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bea33-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="bea33-116">Details</span></span>  
  
|<span data-ttu-id="bea33-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="bea33-117">Data Item Name</span></span>|<span data-ttu-id="bea33-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="bea33-118">Data Item Type</span></span>|<span data-ttu-id="bea33-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="bea33-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bea33-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="bea33-120">InvokeMethod</span></span>|<span data-ttu-id="bea33-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bea33-121">xs:string</span></span>|<span data-ttu-id="bea33-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="bea33-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="bea33-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bea33-123">AppDomain</span></span>|<span data-ttu-id="bea33-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bea33-124">xs:string</span></span>|<span data-ttu-id="bea33-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bea33-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
