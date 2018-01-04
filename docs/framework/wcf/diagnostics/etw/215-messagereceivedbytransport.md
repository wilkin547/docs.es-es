---
title: 215 - MessageReceivedByTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8bf2336d1b5c9dda1dac2b38305d944a822bd253
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="79e77-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="79e77-102">215 - MessageReceivedByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="79e77-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="79e77-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79e77-104">Id.</span><span class="sxs-lookup"><span data-stu-id="79e77-104">ID</span></span>|<span data-ttu-id="79e77-105">215</span><span class="sxs-lookup"><span data-stu-id="79e77-105">215</span></span>|  
|<span data-ttu-id="79e77-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="79e77-106">Keywords</span></span>|<span data-ttu-id="79e77-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="79e77-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="79e77-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="79e77-108">Level</span></span>|<span data-ttu-id="79e77-109">Información</span><span class="sxs-lookup"><span data-stu-id="79e77-109">Information</span></span>|  
|<span data-ttu-id="79e77-110">Canal</span><span class="sxs-lookup"><span data-stu-id="79e77-110">Channel</span></span>|<span data-ttu-id="79e77-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="79e77-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="79e77-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="79e77-112">Description</span></span>  
 <span data-ttu-id="79e77-113">Este evento se produce cuando un transporte basado en TCP recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="79e77-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="79e77-114">Observe que, en el nivel de transporte, pueden intercambiarse múltiples mensajes entre los clientes y servicios para una única operación.</span><span class="sxs-lookup"><span data-stu-id="79e77-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="79e77-115">Esto puede deberse al comportamiento de la infraestructura, y la seguridad es un buen ejemplo.</span><span class="sxs-lookup"><span data-stu-id="79e77-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="79e77-116">Por lo tanto, el número de eventos `MessageReceivedByTransport` que se emiten varía según el enlace del servicio y su configuración.</span><span class="sxs-lookup"><span data-stu-id="79e77-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79e77-117">Este evento no se emite para transportes unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="79e77-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="79e77-118">Mensaje</span><span class="sxs-lookup"><span data-stu-id="79e77-118">Message</span></span>  
 <span data-ttu-id="79e77-119">El transporte ha recibido un mensaje de '%1'.</span><span class="sxs-lookup"><span data-stu-id="79e77-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="79e77-120">Detalles</span><span class="sxs-lookup"><span data-stu-id="79e77-120">Details</span></span>  
  
|<span data-ttu-id="79e77-121">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="79e77-121">Data Item Name</span></span>|<span data-ttu-id="79e77-122">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="79e77-122">Data Item Type</span></span>|<span data-ttu-id="79e77-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="79e77-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="79e77-124">Listen Address</span><span class="sxs-lookup"><span data-stu-id="79e77-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="79e77-125">La dirección que recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="79e77-125">The address that received the message.</span></span>|  
|<span data-ttu-id="79e77-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="79e77-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="79e77-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="79e77-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="79e77-128">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="79e77-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="79e77-129">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="79e77-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="79e77-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="79e77-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="79e77-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="79e77-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
