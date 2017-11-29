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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 934c2947e86b429e9b990c273f22c0511f209a53
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="c230c-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="c230c-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="c230c-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c230c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c230c-104">Id.</span><span class="sxs-lookup"><span data-stu-id="c230c-104">ID</span></span>|<span data-ttu-id="c230c-105">1125</span><span class="sxs-lookup"><span data-stu-id="c230c-105">1125</span></span>|  
|<span data-ttu-id="c230c-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c230c-106">Keywords</span></span>|<span data-ttu-id="c230c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c230c-107">WFRuntime</span></span>|  
|<span data-ttu-id="c230c-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="c230c-108">Level</span></span>|<span data-ttu-id="c230c-109">Información</span><span class="sxs-lookup"><span data-stu-id="c230c-109">Information</span></span>|  
|<span data-ttu-id="c230c-110">Canal</span><span class="sxs-lookup"><span data-stu-id="c230c-110">Channel</span></span>|<span data-ttu-id="c230c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c230c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c230c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c230c-112">Description</span></span>  
 <span data-ttu-id="c230c-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que el método que se va a invocar no es estático.</span><span class="sxs-lookup"><span data-stu-id="c230c-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c230c-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="c230c-114">Message</span></span>  
 <span data-ttu-id="c230c-115">InvokeMethod '%1': el método no es estático.</span><span class="sxs-lookup"><span data-stu-id="c230c-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c230c-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="c230c-116">Details</span></span>  
  
|<span data-ttu-id="c230c-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c230c-117">Data Item Name</span></span>|<span data-ttu-id="c230c-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c230c-118">Data Item Type</span></span>|<span data-ttu-id="c230c-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c230c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c230c-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="c230c-120">InvokeMethod</span></span>|<span data-ttu-id="c230c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c230c-121">xs:string</span></span>|<span data-ttu-id="c230c-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="c230c-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="c230c-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c230c-123">AppDomain</span></span>|<span data-ttu-id="c230c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c230c-124">xs:string</span></span>|<span data-ttu-id="c230c-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c230c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
