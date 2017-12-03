---
title: 221 - MessageReceivedFromTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0b286264cee3d9a0c2ef1df1c6f215240148f98
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="deb74-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="deb74-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="deb74-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="deb74-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="deb74-104">Id.</span><span class="sxs-lookup"><span data-stu-id="deb74-104">ID</span></span>|<span data-ttu-id="deb74-105">221</span><span class="sxs-lookup"><span data-stu-id="deb74-105">221</span></span>|  
|<span data-ttu-id="deb74-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="deb74-106">Keywords</span></span>|<span data-ttu-id="deb74-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="deb74-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="deb74-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="deb74-108">Level</span></span>|<span data-ttu-id="deb74-109">Información</span><span class="sxs-lookup"><span data-stu-id="deb74-109">Information</span></span>|  
|<span data-ttu-id="deb74-110">Canal</span><span class="sxs-lookup"><span data-stu-id="deb74-110">Channel</span></span>|<span data-ttu-id="deb74-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="deb74-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="deb74-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="deb74-112">Description</span></span>  
 <span data-ttu-id="deb74-113">Este evento se emite cuando el modelo de servicio recibe un mensaje del transporte.</span><span class="sxs-lookup"><span data-stu-id="deb74-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="deb74-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="deb74-114">Message</span></span>  
 <span data-ttu-id="deb74-115">El distribuidor recibió un mensaje del transporte.</span><span class="sxs-lookup"><span data-stu-id="deb74-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="deb74-116">Id. de correlación == '%1'.</span><span class="sxs-lookup"><span data-stu-id="deb74-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="deb74-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="deb74-117">Details</span></span>  
  
|<span data-ttu-id="deb74-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="deb74-118">Data Item Name</span></span>|<span data-ttu-id="deb74-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="deb74-119">Data Item Type</span></span>|<span data-ttu-id="deb74-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="deb74-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="deb74-121">Correlation ID</span><span class="sxs-lookup"><span data-stu-id="deb74-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="deb74-122">El identificador de actividad usado para poner en correlación un evento `MessageSentToTransport` de un servicio o cliente con su `MessageReceivedFromTransport` correspondiente en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="deb74-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="deb74-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="deb74-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="deb74-124">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="deb74-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="deb74-125">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="deb74-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="deb74-126">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="deb74-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="deb74-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="deb74-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="deb74-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="deb74-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
