---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 0bb54387dbd738a01225008edfc45ecb7297cd00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512143"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="07f97-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="07f97-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="07f97-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="07f97-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07f97-104">Id.</span><span class="sxs-lookup"><span data-stu-id="07f97-104">ID</span></span>|<span data-ttu-id="07f97-105">225</span><span class="sxs-lookup"><span data-stu-id="07f97-105">225</span></span>|  
|<span data-ttu-id="07f97-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="07f97-106">Keywords</span></span>|<span data-ttu-id="07f97-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="07f97-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="07f97-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="07f97-108">Level</span></span>|<span data-ttu-id="07f97-109">Información</span><span class="sxs-lookup"><span data-stu-id="07f97-109">Information</span></span>|  
|<span data-ttu-id="07f97-110">Canal</span><span class="sxs-lookup"><span data-stu-id="07f97-110">Channel</span></span>|<span data-ttu-id="07f97-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="07f97-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="07f97-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="07f97-112">Description</span></span>  
 <span data-ttu-id="07f97-113">Se emite este evento cuando se utiliza una correlación basada en contenido para un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="07f97-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="07f97-114">Contiene las claves de correlación que se aplican para poner en correlación un mensaje y una instancia.</span><span class="sxs-lookup"><span data-stu-id="07f97-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="07f97-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="07f97-115">Message</span></span>  
 <span data-ttu-id="07f97-116">Clave de correlación calculada '%1' que usa valores '%2' en el ámbito principal '%3'.</span><span class="sxs-lookup"><span data-stu-id="07f97-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="07f97-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="07f97-117">Details</span></span>  
  
|<span data-ttu-id="07f97-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="07f97-118">Data Item Name</span></span>|<span data-ttu-id="07f97-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="07f97-119">Data Item Type</span></span>|<span data-ttu-id="07f97-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="07f97-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="07f97-121">Instance Key</span><span class="sxs-lookup"><span data-stu-id="07f97-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="07f97-122">La clave generada a partir de los valores de correlación.</span><span class="sxs-lookup"><span data-stu-id="07f97-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="07f97-123">Valores</span><span class="sxs-lookup"><span data-stu-id="07f97-123">Values</span></span>|`xs:string`|<span data-ttu-id="07f97-124">Los valores utilizados para calcular la clave de instancia de correlación.</span><span class="sxs-lookup"><span data-stu-id="07f97-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="07f97-125">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="07f97-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="07f97-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="07f97-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="07f97-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="07f97-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="07f97-128">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="07f97-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="07f97-129">Ejemplo: ' predeterminado sitio Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="07f97-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="07f97-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="07f97-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="07f97-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="07f97-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
