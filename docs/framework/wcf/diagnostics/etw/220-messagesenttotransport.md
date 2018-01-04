---
title: 220 - MessageSentToTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d391d7bb8276f4b20d831acd59aa8a78db38995c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="6adf8-102">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="6adf8-102">220 - MessageSentToTransport</span></span>
## <a name="properties"></a><span data-ttu-id="6adf8-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6adf8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6adf8-104">Id.</span><span class="sxs-lookup"><span data-stu-id="6adf8-104">Id</span></span>|<span data-ttu-id="6adf8-105">220</span><span class="sxs-lookup"><span data-stu-id="6adf8-105">220</span></span>|  
|<span data-ttu-id="6adf8-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6adf8-106">Keywords</span></span>|<span data-ttu-id="6adf8-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6adf8-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="6adf8-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="6adf8-108">Level</span></span>|<span data-ttu-id="6adf8-109">Información</span><span class="sxs-lookup"><span data-stu-id="6adf8-109">Information</span></span>|  
|<span data-ttu-id="6adf8-110">Canal</span><span class="sxs-lookup"><span data-stu-id="6adf8-110">Channel</span></span>|<span data-ttu-id="6adf8-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6adf8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6adf8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6adf8-112">Description</span></span>  
 <span data-ttu-id="6adf8-113">Este evento se emite cuando el modelo de servicio envía un mensaje al transporte.</span><span class="sxs-lookup"><span data-stu-id="6adf8-113">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6adf8-114">Este evento no se emitirá para transportes unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="6adf8-114">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6adf8-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="6adf8-115">Message</span></span>  
 <span data-ttu-id="6adf8-116">El distribuidor envió un mensaje al transporte.</span><span class="sxs-lookup"><span data-stu-id="6adf8-116">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="6adf8-117">Id. de correlación == '%1'.</span><span class="sxs-lookup"><span data-stu-id="6adf8-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6adf8-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="6adf8-118">Details</span></span>  
  
|<span data-ttu-id="6adf8-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6adf8-119">Data Item Name</span></span>|<span data-ttu-id="6adf8-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6adf8-120">Data Item Type</span></span>|<span data-ttu-id="6adf8-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="6adf8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6adf8-122">Correlation ID</span><span class="sxs-lookup"><span data-stu-id="6adf8-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="6adf8-123">El identificador de actividad usado para poner en correlación un evento `MessageSentToTransport` de un servicio o cliente con su `MessageReceivedFromTransport` correspondiente en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="6adf8-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="6adf8-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="6adf8-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="6adf8-125">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="6adf8-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="6adf8-126">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="6adf8-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="6adf8-127">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="6adf8-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="6adf8-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6adf8-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6adf8-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6adf8-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
