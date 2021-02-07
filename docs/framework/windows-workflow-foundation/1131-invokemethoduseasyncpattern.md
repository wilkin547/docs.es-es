---
description: 'Más información acerca de: 1131-InvokeMethodUseAsyncPattern'
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 59d8e5e1fe7c5b038df6fce3211fd01977abc4f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667322"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="23743-103">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="23743-103">1131 - InvokeMethodUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="23743-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="23743-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23743-105">Id.</span><span class="sxs-lookup"><span data-stu-id="23743-105">ID</span></span>|<span data-ttu-id="23743-106">1131</span><span class="sxs-lookup"><span data-stu-id="23743-106">1131</span></span>|  
|<span data-ttu-id="23743-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="23743-107">Keywords</span></span>|<span data-ttu-id="23743-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="23743-108">WFRuntime</span></span>|  
|<span data-ttu-id="23743-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="23743-109">Level</span></span>|<span data-ttu-id="23743-110">Información</span><span class="sxs-lookup"><span data-stu-id="23743-110">Information</span></span>|  
|<span data-ttu-id="23743-111">Canal</span><span class="sxs-lookup"><span data-stu-id="23743-111">Channel</span></span>|<span data-ttu-id="23743-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="23743-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="23743-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="23743-113">Description</span></span>  

 <span data-ttu-id="23743-114">Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="23743-114">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="23743-115">Message</span><span class="sxs-lookup"><span data-stu-id="23743-115">Message</span></span>  

 <span data-ttu-id="23743-116">InvokeMethod '%1': el método usa el patrón asincrónico de '%2' y '%3'.</span><span class="sxs-lookup"><span data-stu-id="23743-116">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="23743-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="23743-117">Details</span></span>  
  
|<span data-ttu-id="23743-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="23743-118">Data Item Name</span></span>|<span data-ttu-id="23743-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="23743-119">Data Item Type</span></span>|<span data-ttu-id="23743-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="23743-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="23743-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="23743-121">InvokeMethod</span></span>|<span data-ttu-id="23743-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="23743-122">xs:string</span></span>|<span data-ttu-id="23743-123">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="23743-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="23743-124">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="23743-124">BeginMethod</span></span>|<span data-ttu-id="23743-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="23743-125">xs:string</span></span>|<span data-ttu-id="23743-126">Nombre del método de inicio.</span><span class="sxs-lookup"><span data-stu-id="23743-126">The name of the begin method.</span></span>|  
|<span data-ttu-id="23743-127">EndMethod</span><span class="sxs-lookup"><span data-stu-id="23743-127">EndMethod</span></span>|<span data-ttu-id="23743-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="23743-128">xs:string</span></span>|<span data-ttu-id="23743-129">Nombre del método de fin.</span><span class="sxs-lookup"><span data-stu-id="23743-129">The name of the end method.</span></span>|  
|<span data-ttu-id="23743-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="23743-130">AppDomain</span></span>|<span data-ttu-id="23743-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="23743-131">xs:string</span></span>|<span data-ttu-id="23743-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="23743-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
