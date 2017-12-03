---
title: 211 - ParameterInspectorAfterCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 78424b8057518f5d9f201ead33b2784ffeeb7e58
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="a13a8-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="a13a8-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="a13a8-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a13a8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a13a8-104">Id.</span><span class="sxs-lookup"><span data-stu-id="a13a8-104">ID</span></span>|<span data-ttu-id="a13a8-105">211</span><span class="sxs-lookup"><span data-stu-id="a13a8-105">211</span></span>|  
|<span data-ttu-id="a13a8-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a13a8-106">Keywords</span></span>|<span data-ttu-id="a13a8-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a13a8-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a13a8-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a13a8-108">Level</span></span>|<span data-ttu-id="a13a8-109">Información</span><span class="sxs-lookup"><span data-stu-id="a13a8-109">Information</span></span>|  
|<span data-ttu-id="a13a8-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a13a8-110">Channel</span></span>|<span data-ttu-id="a13a8-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a13a8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a13a8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a13a8-112">Description</span></span>  
 <span data-ttu-id="a13a8-113">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterCall` en `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="a13a8-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a13a8-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a13a8-114">Message</span></span>  
 <span data-ttu-id="a13a8-115">El distribuidor invocó 'AfterCall' en un ParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="a13a8-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a13a8-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="a13a8-116">Details</span></span>  
  
|<span data-ttu-id="a13a8-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a13a8-117">Data Item Name</span></span>|<span data-ttu-id="a13a8-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a13a8-118">Data Item Type</span></span>|<span data-ttu-id="a13a8-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a13a8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a13a8-120">Nombre de tipo</span><span class="sxs-lookup"><span data-stu-id="a13a8-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="a13a8-121">Nombre completo (FullName) de CLR del tipo del `ParameterInspector` invocado.</span><span class="sxs-lookup"><span data-stu-id="a13a8-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="a13a8-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="a13a8-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="a13a8-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="a13a8-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a13a8-124">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="a13a8-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a13a8-125">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="a13a8-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a13a8-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a13a8-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a13a8-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a13a8-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
