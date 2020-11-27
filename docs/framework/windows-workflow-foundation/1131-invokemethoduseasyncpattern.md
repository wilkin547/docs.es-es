---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 2192b63b8a08657b69f6e3984f898bd6baddbc5f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294188"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="37b9a-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="37b9a-102">1131 - InvokeMethodUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="37b9a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="37b9a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37b9a-104">ID</span><span class="sxs-lookup"><span data-stu-id="37b9a-104">ID</span></span>|<span data-ttu-id="37b9a-105">1131</span><span class="sxs-lookup"><span data-stu-id="37b9a-105">1131</span></span>|  
|<span data-ttu-id="37b9a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="37b9a-106">Keywords</span></span>|<span data-ttu-id="37b9a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="37b9a-107">WFRuntime</span></span>|  
|<span data-ttu-id="37b9a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="37b9a-108">Level</span></span>|<span data-ttu-id="37b9a-109">Información</span><span class="sxs-lookup"><span data-stu-id="37b9a-109">Information</span></span>|  
|<span data-ttu-id="37b9a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="37b9a-110">Channel</span></span>|<span data-ttu-id="37b9a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="37b9a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="37b9a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="37b9a-112">Description</span></span>  

 <span data-ttu-id="37b9a-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="37b9a-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="37b9a-114">Message</span><span class="sxs-lookup"><span data-stu-id="37b9a-114">Message</span></span>  

 <span data-ttu-id="37b9a-115">InvokeMethod '%1': el método usa el patrón asincrónico de '%2' y '%3'.</span><span class="sxs-lookup"><span data-stu-id="37b9a-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="37b9a-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="37b9a-116">Details</span></span>  
  
|<span data-ttu-id="37b9a-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="37b9a-117">Data Item Name</span></span>|<span data-ttu-id="37b9a-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="37b9a-118">Data Item Type</span></span>|<span data-ttu-id="37b9a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="37b9a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="37b9a-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="37b9a-120">InvokeMethod</span></span>|<span data-ttu-id="37b9a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="37b9a-121">xs:string</span></span>|<span data-ttu-id="37b9a-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="37b9a-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="37b9a-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="37b9a-123">BeginMethod</span></span>|<span data-ttu-id="37b9a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="37b9a-124">xs:string</span></span>|<span data-ttu-id="37b9a-125">Nombre del método de inicio.</span><span class="sxs-lookup"><span data-stu-id="37b9a-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="37b9a-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="37b9a-126">EndMethod</span></span>|<span data-ttu-id="37b9a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="37b9a-127">xs:string</span></span>|<span data-ttu-id="37b9a-128">Nombre del método de fin.</span><span class="sxs-lookup"><span data-stu-id="37b9a-128">The name of the end method.</span></span>|  
|<span data-ttu-id="37b9a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="37b9a-129">AppDomain</span></span>|<span data-ttu-id="37b9a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="37b9a-130">xs:string</span></span>|<span data-ttu-id="37b9a-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="37b9a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
