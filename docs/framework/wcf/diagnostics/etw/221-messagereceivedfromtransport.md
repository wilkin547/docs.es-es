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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4f977f938844f48182be6662f489506e8119fe67
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="cc1b0-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="cc1b0-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="cc1b0-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="cc1b0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc1b0-104">Id.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-104">ID</span></span>|<span data-ttu-id="cc1b0-105">221</span><span class="sxs-lookup"><span data-stu-id="cc1b0-105">221</span></span>|  
|<span data-ttu-id="cc1b0-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="cc1b0-106">Keywords</span></span>|<span data-ttu-id="cc1b0-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cc1b0-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="cc1b0-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc1b0-108">Level</span></span>|<span data-ttu-id="cc1b0-109">Información</span><span class="sxs-lookup"><span data-stu-id="cc1b0-109">Information</span></span>|  
|<span data-ttu-id="cc1b0-110">Canal</span><span class="sxs-lookup"><span data-stu-id="cc1b0-110">Channel</span></span>|<span data-ttu-id="cc1b0-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="cc1b0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cc1b0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc1b0-112">Description</span></span>  
 <span data-ttu-id="cc1b0-113">Este evento se emite cuando el modelo de servicio recibe un mensaje del transporte.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cc1b0-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="cc1b0-114">Message</span></span>  
 <span data-ttu-id="cc1b0-115">El distribuidor recibió un mensaje del transporte.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="cc1b0-116">Id. de correlación == '%1'.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cc1b0-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="cc1b0-117">Details</span></span>  
  
|<span data-ttu-id="cc1b0-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cc1b0-118">Data Item Name</span></span>|<span data-ttu-id="cc1b0-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cc1b0-119">Data Item Type</span></span>|<span data-ttu-id="cc1b0-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc1b0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cc1b0-121">Correlation ID</span><span class="sxs-lookup"><span data-stu-id="cc1b0-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="cc1b0-122">El identificador de actividad usado para poner en correlación un evento `MessageSentToTransport` de un servicio o cliente con su `MessageReceivedFromTransport` correspondiente en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="cc1b0-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="cc1b0-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="cc1b0-124">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="cc1b0-125">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="cc1b0-126">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="cc1b0-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cc1b0-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cc1b0-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
