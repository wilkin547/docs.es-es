---
description: 'Más información acerca de: 225-TraceCorrelationKeys'
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: c5fdb9305815cdc4df6bbae3e54209d2b5cffd9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778118"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="26360-103">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="26360-103">225 - TraceCorrelationKeys</span></span>

## <a name="properties"></a><span data-ttu-id="26360-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="26360-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26360-105">Id.</span><span class="sxs-lookup"><span data-stu-id="26360-105">ID</span></span>|<span data-ttu-id="26360-106">225</span><span class="sxs-lookup"><span data-stu-id="26360-106">225</span></span>|  
|<span data-ttu-id="26360-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="26360-107">Keywords</span></span>|<span data-ttu-id="26360-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="26360-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="26360-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="26360-109">Level</span></span>|<span data-ttu-id="26360-110">Información</span><span class="sxs-lookup"><span data-stu-id="26360-110">Information</span></span>|  
|<span data-ttu-id="26360-111">Canal</span><span class="sxs-lookup"><span data-stu-id="26360-111">Channel</span></span>|<span data-ttu-id="26360-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="26360-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="26360-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="26360-113">Description</span></span>  

 <span data-ttu-id="26360-114">Se emite este evento cuando se utiliza una correlación basada en contenido para un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="26360-114">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="26360-115">Contiene las claves de correlación que se aplican para poner en correlación un mensaje y una instancia.</span><span class="sxs-lookup"><span data-stu-id="26360-115">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="26360-116">Message</span><span class="sxs-lookup"><span data-stu-id="26360-116">Message</span></span>  

 <span data-ttu-id="26360-117">Clave de correlación calculada '%1' que usa valores '%2' en el ámbito principal '%3'.</span><span class="sxs-lookup"><span data-stu-id="26360-117">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="26360-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="26360-118">Details</span></span>  
  
|<span data-ttu-id="26360-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="26360-119">Data Item Name</span></span>|<span data-ttu-id="26360-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="26360-120">Data Item Type</span></span>|<span data-ttu-id="26360-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="26360-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="26360-122">Instance Key</span><span class="sxs-lookup"><span data-stu-id="26360-122">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="26360-123">La clave generada a partir de los valores de correlación.</span><span class="sxs-lookup"><span data-stu-id="26360-123">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="26360-124">Valores</span><span class="sxs-lookup"><span data-stu-id="26360-124">Values</span></span>|`xs:string`|<span data-ttu-id="26360-125">Los valores utilizados para calcular la clave de instancia de correlación.</span><span class="sxs-lookup"><span data-stu-id="26360-125">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="26360-126">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="26360-126">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="26360-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="26360-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="26360-128">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="26360-128">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="26360-129">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="26360-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="26360-130">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="26360-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="26360-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="26360-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="26360-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="26360-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
