---
description: 'Más información acerca de: 1132-InvokeMethodDoesNotUseAsyncPattern'
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 05bbd1f6047ab4c6451d71a4f6007f3112f9630f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667283"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="26150-103">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="26150-103">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="26150-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="26150-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26150-105">Id.</span><span class="sxs-lookup"><span data-stu-id="26150-105">ID</span></span>|<span data-ttu-id="26150-106">1132</span><span class="sxs-lookup"><span data-stu-id="26150-106">1132</span></span>|  
|<span data-ttu-id="26150-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="26150-107">Keywords</span></span>|<span data-ttu-id="26150-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="26150-108">WFRuntime</span></span>|  
|<span data-ttu-id="26150-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="26150-109">Level</span></span>|<span data-ttu-id="26150-110">Información</span><span class="sxs-lookup"><span data-stu-id="26150-110">Information</span></span>|  
|<span data-ttu-id="26150-111">Canal</span><span class="sxs-lookup"><span data-stu-id="26150-111">Channel</span></span>|<span data-ttu-id="26150-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="26150-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="26150-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="26150-113">Description</span></span>  

 <span data-ttu-id="26150-114">Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="26150-114">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="26150-115">Message</span><span class="sxs-lookup"><span data-stu-id="26150-115">Message</span></span>  

 <span data-ttu-id="26150-116">InvokeMethod '%1': el método no usa un patrón asincrónico.</span><span class="sxs-lookup"><span data-stu-id="26150-116">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="26150-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="26150-117">Details</span></span>  
  
|<span data-ttu-id="26150-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="26150-118">Data Item Name</span></span>|<span data-ttu-id="26150-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="26150-119">Data Item Type</span></span>|<span data-ttu-id="26150-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="26150-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="26150-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="26150-121">InvokeMethod</span></span>|<span data-ttu-id="26150-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="26150-122">xs:string</span></span>|<span data-ttu-id="26150-123">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="26150-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="26150-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="26150-124">AppDomain</span></span>|<span data-ttu-id="26150-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="26150-125">xs:string</span></span>|<span data-ttu-id="26150-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="26150-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
