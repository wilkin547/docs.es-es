---
title: 216 - MessageSentByTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b35f46ae7a214ab45e4062928de82c4da6541a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="54e70-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="54e70-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="54e70-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="54e70-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54e70-104">Id.</span><span class="sxs-lookup"><span data-stu-id="54e70-104">ID</span></span>|<span data-ttu-id="54e70-105">216</span><span class="sxs-lookup"><span data-stu-id="54e70-105">216</span></span>|  
|<span data-ttu-id="54e70-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="54e70-106">Keywords</span></span>|<span data-ttu-id="54e70-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="54e70-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="54e70-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="54e70-108">Level</span></span>|<span data-ttu-id="54e70-109">Información</span><span class="sxs-lookup"><span data-stu-id="54e70-109">Information</span></span>|  
|<span data-ttu-id="54e70-110">Canal</span><span class="sxs-lookup"><span data-stu-id="54e70-110">Channel</span></span>|<span data-ttu-id="54e70-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="54e70-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="54e70-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="54e70-112">Description</span></span>  
 <span data-ttu-id="54e70-113">Este evento se produce cuando un transporte basado en TCP envía un mensaje.</span><span class="sxs-lookup"><span data-stu-id="54e70-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="54e70-114">Observe que, en el nivel de transporte, pueden intercambiarse múltiples mensajes entre los clientes y servicios para una única operación.</span><span class="sxs-lookup"><span data-stu-id="54e70-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="54e70-115">Esto puede deberse al comportamiento de la infraestructura, siendo la seguridad un buen ejemplo.</span><span class="sxs-lookup"><span data-stu-id="54e70-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="54e70-116">Por lo tanto, el número de **MessageSentByTransport** eventos que se emiten varían dependiendo del enlace del servicio y su configuración.</span><span class="sxs-lookup"><span data-stu-id="54e70-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="54e70-117">Mensaje</span><span class="sxs-lookup"><span data-stu-id="54e70-117">Message</span></span>  
 <span data-ttu-id="54e70-118">El transporte ha enviado un mensaje a '%1'.</span><span class="sxs-lookup"><span data-stu-id="54e70-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="54e70-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="54e70-119">Details</span></span>  
  
|<span data-ttu-id="54e70-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="54e70-120">Data Item Name</span></span>|<span data-ttu-id="54e70-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="54e70-121">Data Item Type</span></span>|<span data-ttu-id="54e70-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="54e70-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="54e70-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="54e70-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="54e70-124">La dirección a la que se ha enviado el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="54e70-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="54e70-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="54e70-125">HostReference</span></span>|<span data-ttu-id="54e70-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="54e70-126">xs:string</span></span>|<span data-ttu-id="54e70-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="54e70-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="54e70-128">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="54e70-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="54e70-129">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="54e70-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="54e70-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="54e70-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="54e70-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="54e70-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
