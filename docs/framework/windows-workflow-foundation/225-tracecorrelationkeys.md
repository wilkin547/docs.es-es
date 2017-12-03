---
title: 225 - TraceCorrelationKeys
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f4b6eb5df59977de91f1651a47a96cdf44bcf29
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="bf590-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="bf590-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="bf590-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bf590-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf590-104">Id.</span><span class="sxs-lookup"><span data-stu-id="bf590-104">ID</span></span>|<span data-ttu-id="bf590-105">225</span><span class="sxs-lookup"><span data-stu-id="bf590-105">225</span></span>|  
|<span data-ttu-id="bf590-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="bf590-106">Keywords</span></span>|<span data-ttu-id="bf590-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bf590-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="bf590-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="bf590-108">Level</span></span>|<span data-ttu-id="bf590-109">Información</span><span class="sxs-lookup"><span data-stu-id="bf590-109">Information</span></span>|  
|<span data-ttu-id="bf590-110">Canal</span><span class="sxs-lookup"><span data-stu-id="bf590-110">Channel</span></span>|<span data-ttu-id="bf590-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="bf590-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bf590-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf590-112">Description</span></span>  
 <span data-ttu-id="bf590-113">Se emite este evento cuando se utiliza una correlación basada en contenido para un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bf590-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="bf590-114">Contiene las claves de correlación que se aplican para poner en correlación un mensaje y una instancia.</span><span class="sxs-lookup"><span data-stu-id="bf590-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bf590-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="bf590-115">Message</span></span>  
 <span data-ttu-id="bf590-116">Clave de correlación calculada '%1' que usa valores '%2' en el ámbito principal '%3'.</span><span class="sxs-lookup"><span data-stu-id="bf590-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bf590-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="bf590-117">Details</span></span>  
  
|<span data-ttu-id="bf590-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="bf590-118">Data Item Name</span></span>|<span data-ttu-id="bf590-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="bf590-119">Data Item Type</span></span>|<span data-ttu-id="bf590-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf590-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bf590-121">Instance Key</span><span class="sxs-lookup"><span data-stu-id="bf590-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="bf590-122">La clave generada a partir de los valores de correlación.</span><span class="sxs-lookup"><span data-stu-id="bf590-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="bf590-123">Valores</span><span class="sxs-lookup"><span data-stu-id="bf590-123">Values</span></span>|`xs:string`|<span data-ttu-id="bf590-124">Los valores utilizados para calcular la clave de instancia de correlación.</span><span class="sxs-lookup"><span data-stu-id="bf590-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="bf590-125">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="bf590-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="bf590-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="bf590-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="bf590-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="bf590-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="bf590-128">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="bf590-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="bf590-129">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="bf590-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="bf590-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bf590-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bf590-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bf590-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
