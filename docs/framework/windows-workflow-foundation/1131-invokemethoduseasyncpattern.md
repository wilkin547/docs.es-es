---
title: 1131 - InvokeMethodUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f9f8f4e836d5c5b437edcfaff6460c7b97210ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="750e9-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="750e9-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="750e9-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="750e9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="750e9-104">Id.</span><span class="sxs-lookup"><span data-stu-id="750e9-104">ID</span></span>|<span data-ttu-id="750e9-105">1131</span><span class="sxs-lookup"><span data-stu-id="750e9-105">1131</span></span>|  
|<span data-ttu-id="750e9-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="750e9-106">Keywords</span></span>|<span data-ttu-id="750e9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="750e9-107">WFRuntime</span></span>|  
|<span data-ttu-id="750e9-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="750e9-108">Level</span></span>|<span data-ttu-id="750e9-109">Información</span><span class="sxs-lookup"><span data-stu-id="750e9-109">Information</span></span>|  
|<span data-ttu-id="750e9-110">Canal</span><span class="sxs-lookup"><span data-stu-id="750e9-110">Channel</span></span>|<span data-ttu-id="750e9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="750e9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="750e9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="750e9-112">Description</span></span>  
 <span data-ttu-id="750e9-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="750e9-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="750e9-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="750e9-114">Message</span></span>  
 <span data-ttu-id="750e9-115">InvokeMethod '%1': el método usa el patrón asincrónico de '%2' y '%3'.</span><span class="sxs-lookup"><span data-stu-id="750e9-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="750e9-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="750e9-116">Details</span></span>  
  
|<span data-ttu-id="750e9-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="750e9-117">Data Item Name</span></span>|<span data-ttu-id="750e9-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="750e9-118">Data Item Type</span></span>|<span data-ttu-id="750e9-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="750e9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="750e9-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="750e9-120">InvokeMethod</span></span>|<span data-ttu-id="750e9-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="750e9-121">xs:string</span></span>|<span data-ttu-id="750e9-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="750e9-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="750e9-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="750e9-123">BeginMethod</span></span>|<span data-ttu-id="750e9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="750e9-124">xs:string</span></span>|<span data-ttu-id="750e9-125">Nombre del método de inicio.</span><span class="sxs-lookup"><span data-stu-id="750e9-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="750e9-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="750e9-126">EndMethod</span></span>|<span data-ttu-id="750e9-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="750e9-127">xs:string</span></span>|<span data-ttu-id="750e9-128">Nombre del método de fin.</span><span class="sxs-lookup"><span data-stu-id="750e9-128">The name of the end method.</span></span>|  
|<span data-ttu-id="750e9-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="750e9-129">AppDomain</span></span>|<span data-ttu-id="750e9-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="750e9-130">xs:string</span></span>|<span data-ttu-id="750e9-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="750e9-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
