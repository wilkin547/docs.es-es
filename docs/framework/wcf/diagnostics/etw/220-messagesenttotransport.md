---
description: 'Más información acerca de: 220-MessageSentToTransport'
title: 220 - MessageSentToTransport
ms.date: 03/30/2017
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
ms.openlocfilehash: 8d76f147c8a31a5aa08c21073cd03e63436095ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794317"
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="23479-103">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="23479-103">220 - MessageSentToTransport</span></span>

## <a name="properties"></a><span data-ttu-id="23479-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="23479-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23479-105">Identificador</span><span class="sxs-lookup"><span data-stu-id="23479-105">Id</span></span>|<span data-ttu-id="23479-106">220</span><span class="sxs-lookup"><span data-stu-id="23479-106">220</span></span>|  
|<span data-ttu-id="23479-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="23479-107">Keywords</span></span>|<span data-ttu-id="23479-108">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="23479-108">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="23479-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="23479-109">Level</span></span>|<span data-ttu-id="23479-110">Información</span><span class="sxs-lookup"><span data-stu-id="23479-110">Information</span></span>|  
|<span data-ttu-id="23479-111">Canal</span><span class="sxs-lookup"><span data-stu-id="23479-111">Channel</span></span>|<span data-ttu-id="23479-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="23479-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="23479-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="23479-113">Description</span></span>  

 <span data-ttu-id="23479-114">Este evento se emite cuando el modelo de servicio envía un mensaje al transporte.</span><span class="sxs-lookup"><span data-stu-id="23479-114">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23479-115">Este evento no se emitirá para transportes unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="23479-115">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="23479-116">Message</span><span class="sxs-lookup"><span data-stu-id="23479-116">Message</span></span>  

 <span data-ttu-id="23479-117">El distribuidor envió un mensaje al transporte.</span><span class="sxs-lookup"><span data-stu-id="23479-117">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="23479-118">Id. de correlación == '%1'.</span><span class="sxs-lookup"><span data-stu-id="23479-118">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="23479-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="23479-119">Details</span></span>  
  
|<span data-ttu-id="23479-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="23479-120">Data Item Name</span></span>|<span data-ttu-id="23479-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="23479-121">Data Item Type</span></span>|<span data-ttu-id="23479-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="23479-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="23479-123">Id. de correlación</span><span class="sxs-lookup"><span data-stu-id="23479-123">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="23479-124">El identificador de actividad usado para poner en correlación un evento `MessageSentToTransport` de un servicio o cliente con su `MessageReceivedFromTransport` correspondiente en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="23479-124">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="23479-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="23479-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="23479-126">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="23479-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="23479-127">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="23479-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="23479-128">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="23479-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="23479-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="23479-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="23479-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="23479-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
