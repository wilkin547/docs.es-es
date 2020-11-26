---
title: 1124 - InvokeMethodIsStatic
ms.date: 03/30/2017
ms.assetid: b9643641-fb52-4fa8-b354-4dd6617d68f6
ms.openlocfilehash: d7ad99131f9813c2102f52784fc33605bed37557
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242128"
---
# <a name="1124---invokemethodisstatic"></a><span data-ttu-id="115e5-102">1124 - InvokeMethodIsStatic</span><span class="sxs-lookup"><span data-stu-id="115e5-102">1124 - InvokeMethodIsStatic</span></span>

## <a name="properties"></a><span data-ttu-id="115e5-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="115e5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="115e5-104">ID</span><span class="sxs-lookup"><span data-stu-id="115e5-104">ID</span></span>|<span data-ttu-id="115e5-105">1124</span><span class="sxs-lookup"><span data-stu-id="115e5-105">1124</span></span>|  
|<span data-ttu-id="115e5-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="115e5-106">Keywords</span></span>|<span data-ttu-id="115e5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="115e5-107">WFRuntime</span></span>|  
|<span data-ttu-id="115e5-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="115e5-108">Level</span></span>|<span data-ttu-id="115e5-109">Información</span><span class="sxs-lookup"><span data-stu-id="115e5-109">Information</span></span>|  
|<span data-ttu-id="115e5-110">Canal</span><span class="sxs-lookup"><span data-stu-id="115e5-110">Channel</span></span>|<span data-ttu-id="115e5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="115e5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="115e5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="115e5-112">Description</span></span>  

 <span data-ttu-id="115e5-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que el método que se va a invocar es estático.</span><span class="sxs-lookup"><span data-stu-id="115e5-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="115e5-114">Message</span><span class="sxs-lookup"><span data-stu-id="115e5-114">Message</span></span>  

 <span data-ttu-id="115e5-115">InvokeMethod '%1': el método es estático.</span><span class="sxs-lookup"><span data-stu-id="115e5-115">InvokeMethod '%1' - method is Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="115e5-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="115e5-116">Details</span></span>  
  
|<span data-ttu-id="115e5-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="115e5-117">Data Item Name</span></span>|<span data-ttu-id="115e5-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="115e5-118">Data Item Type</span></span>|<span data-ttu-id="115e5-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="115e5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="115e5-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="115e5-120">InvokeMethod</span></span>|<span data-ttu-id="115e5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="115e5-121">xs:string</span></span>|<span data-ttu-id="115e5-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="115e5-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="115e5-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="115e5-123">AppDomain</span></span>|<span data-ttu-id="115e5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="115e5-124">xs:string</span></span>|<span data-ttu-id="115e5-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="115e5-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
