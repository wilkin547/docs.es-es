---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89aea40ece7717abf37c8a014e4b375e3b1df9a1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="9f88d-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="9f88d-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="9f88d-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9f88d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f88d-104">Id.</span><span class="sxs-lookup"><span data-stu-id="9f88d-104">ID</span></span>|<span data-ttu-id="9f88d-105">203</span><span class="sxs-lookup"><span data-stu-id="9f88d-105">203</span></span>|  
|<span data-ttu-id="9f88d-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9f88d-106">Keywords</span></span>|<span data-ttu-id="9f88d-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9f88d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9f88d-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="9f88d-108">Level</span></span>|<span data-ttu-id="9f88d-109">Información</span><span class="sxs-lookup"><span data-stu-id="9f88d-109">Information</span></span>|  
|<span data-ttu-id="9f88d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="9f88d-110">Channel</span></span>|<span data-ttu-id="9f88d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9f88d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9f88d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f88d-112">Description</span></span>  
 <span data-ttu-id="9f88d-113">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterCall` en un inspector de parámetro de cliente.</span><span class="sxs-lookup"><span data-stu-id="9f88d-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9f88d-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="9f88d-114">Message</span></span>  
 <span data-ttu-id="9f88d-115">El distribuidor invocó 'AfterCall' en ClientParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="9f88d-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9f88d-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="9f88d-116">Details</span></span>  
  
|<span data-ttu-id="9f88d-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9f88d-117">Data Item Name</span></span>|<span data-ttu-id="9f88d-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9f88d-118">Data Item Type</span></span>|<span data-ttu-id="9f88d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f88d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9f88d-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="9f88d-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="9f88d-121">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="9f88d-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="9f88d-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="9f88d-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="9f88d-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="9f88d-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9f88d-124">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="9f88d-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9f88d-125">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="9f88d-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9f88d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9f88d-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9f88d-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9f88d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
