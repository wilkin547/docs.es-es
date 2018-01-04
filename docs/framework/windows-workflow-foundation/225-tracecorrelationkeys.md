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
ms.workload: dotnet
ms.openlocfilehash: 9a8d9120c4173d90d7bf6b1ff2054117f80ac96a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="bd495-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="bd495-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="bd495-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bd495-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd495-104">Id.</span><span class="sxs-lookup"><span data-stu-id="bd495-104">ID</span></span>|<span data-ttu-id="bd495-105">225</span><span class="sxs-lookup"><span data-stu-id="bd495-105">225</span></span>|  
|<span data-ttu-id="bd495-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="bd495-106">Keywords</span></span>|<span data-ttu-id="bd495-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bd495-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="bd495-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="bd495-108">Level</span></span>|<span data-ttu-id="bd495-109">Información</span><span class="sxs-lookup"><span data-stu-id="bd495-109">Information</span></span>|  
|<span data-ttu-id="bd495-110">Canal</span><span class="sxs-lookup"><span data-stu-id="bd495-110">Channel</span></span>|<span data-ttu-id="bd495-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="bd495-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bd495-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd495-112">Description</span></span>  
 <span data-ttu-id="bd495-113">Se emite este evento cuando se utiliza una correlación basada en contenido para un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bd495-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="bd495-114">Contiene las claves de correlación que se aplican para poner en correlación un mensaje y una instancia.</span><span class="sxs-lookup"><span data-stu-id="bd495-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bd495-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="bd495-115">Message</span></span>  
 <span data-ttu-id="bd495-116">Clave de correlación calculada '%1' que usa valores '%2' en el ámbito principal '%3'.</span><span class="sxs-lookup"><span data-stu-id="bd495-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bd495-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="bd495-117">Details</span></span>  
  
|<span data-ttu-id="bd495-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="bd495-118">Data Item Name</span></span>|<span data-ttu-id="bd495-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="bd495-119">Data Item Type</span></span>|<span data-ttu-id="bd495-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd495-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bd495-121">Instance Key</span><span class="sxs-lookup"><span data-stu-id="bd495-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="bd495-122">La clave generada a partir de los valores de correlación.</span><span class="sxs-lookup"><span data-stu-id="bd495-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="bd495-123">Valores</span><span class="sxs-lookup"><span data-stu-id="bd495-123">Values</span></span>|`xs:string`|<span data-ttu-id="bd495-124">Los valores utilizados para calcular la clave de instancia de correlación.</span><span class="sxs-lookup"><span data-stu-id="bd495-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="bd495-125">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="bd495-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="bd495-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="bd495-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="bd495-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="bd495-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="bd495-128">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="bd495-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="bd495-129">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="bd495-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="bd495-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bd495-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bd495-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bd495-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
