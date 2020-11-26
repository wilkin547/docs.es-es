---
title: 220 - MessageSentToTransport
ms.date: 03/30/2017
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
ms.openlocfilehash: 1b63877998ea7942886c83d8795fe5ee49fdf053
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241933"
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="aeaaf-102">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="aeaaf-102">220 - MessageSentToTransport</span></span>

## <a name="properties"></a><span data-ttu-id="aeaaf-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="aeaaf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aeaaf-104">Identificador</span><span class="sxs-lookup"><span data-stu-id="aeaaf-104">Id</span></span>|<span data-ttu-id="aeaaf-105">220</span><span class="sxs-lookup"><span data-stu-id="aeaaf-105">220</span></span>|  
|<span data-ttu-id="aeaaf-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="aeaaf-106">Keywords</span></span>|<span data-ttu-id="aeaaf-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="aeaaf-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="aeaaf-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="aeaaf-108">Level</span></span>|<span data-ttu-id="aeaaf-109">Información</span><span class="sxs-lookup"><span data-stu-id="aeaaf-109">Information</span></span>|  
|<span data-ttu-id="aeaaf-110">Canal</span><span class="sxs-lookup"><span data-stu-id="aeaaf-110">Channel</span></span>|<span data-ttu-id="aeaaf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="aeaaf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aeaaf-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="aeaaf-112">Description</span></span>  

 <span data-ttu-id="aeaaf-113">Este evento se emite cuando el modelo de servicio envía un mensaje al transporte.</span><span class="sxs-lookup"><span data-stu-id="aeaaf-113">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aeaaf-114">Este evento no se emitirá para transportes unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="aeaaf-114">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aeaaf-115">Message</span><span class="sxs-lookup"><span data-stu-id="aeaaf-115">Message</span></span>  

 <span data-ttu-id="aeaaf-116">El distribuidor envió un mensaje al transporte.</span><span class="sxs-lookup"><span data-stu-id="aeaaf-116">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="aeaaf-117">Id. de correlación == '%1'.</span><span class="sxs-lookup"><span data-stu-id="aeaaf-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aeaaf-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="aeaaf-118">Details</span></span>  
  
|<span data-ttu-id="aeaaf-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="aeaaf-119">Data Item Name</span></span>|<span data-ttu-id="aeaaf-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="aeaaf-120">Data Item Type</span></span>|<span data-ttu-id="aeaaf-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="aeaaf-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aeaaf-122">Id. de correlación</span><span class="sxs-lookup"><span data-stu-id="aeaaf-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="aeaaf-123">El identificador de actividad usado para poner en correlación un evento `MessageSentToTransport` de un servicio o cliente con su `MessageReceivedFromTransport` correspondiente en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="aeaaf-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="aeaaf-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="aeaaf-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="aeaaf-125">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="aeaaf-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="aeaaf-126">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="aeaaf-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="aeaaf-127">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="aeaaf-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="aeaaf-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aeaaf-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="aeaaf-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="aeaaf-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
