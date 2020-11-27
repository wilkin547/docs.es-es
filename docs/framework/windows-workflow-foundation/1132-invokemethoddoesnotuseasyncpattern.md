---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 9249bdd0fe996ee7c1b04783ac8fef2c48063cc0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294162"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="45620-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="45620-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="45620-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="45620-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45620-104">ID</span><span class="sxs-lookup"><span data-stu-id="45620-104">ID</span></span>|<span data-ttu-id="45620-105">1132</span><span class="sxs-lookup"><span data-stu-id="45620-105">1132</span></span>|  
|<span data-ttu-id="45620-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="45620-106">Keywords</span></span>|<span data-ttu-id="45620-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="45620-107">WFRuntime</span></span>|  
|<span data-ttu-id="45620-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="45620-108">Level</span></span>|<span data-ttu-id="45620-109">Información</span><span class="sxs-lookup"><span data-stu-id="45620-109">Information</span></span>|  
|<span data-ttu-id="45620-110">Canal</span><span class="sxs-lookup"><span data-stu-id="45620-110">Channel</span></span>|<span data-ttu-id="45620-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="45620-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="45620-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="45620-112">Description</span></span>  

 <span data-ttu-id="45620-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="45620-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="45620-114">Message</span><span class="sxs-lookup"><span data-stu-id="45620-114">Message</span></span>  

 <span data-ttu-id="45620-115">InvokeMethod '%1': el método no usa un patrón asincrónico.</span><span class="sxs-lookup"><span data-stu-id="45620-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="45620-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="45620-116">Details</span></span>  
  
|<span data-ttu-id="45620-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="45620-117">Data Item Name</span></span>|<span data-ttu-id="45620-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="45620-118">Data Item Type</span></span>|<span data-ttu-id="45620-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="45620-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="45620-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="45620-120">InvokeMethod</span></span>|<span data-ttu-id="45620-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="45620-121">xs:string</span></span>|<span data-ttu-id="45620-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="45620-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="45620-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="45620-123">AppDomain</span></span>|<span data-ttu-id="45620-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="45620-124">xs:string</span></span>|<span data-ttu-id="45620-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="45620-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
