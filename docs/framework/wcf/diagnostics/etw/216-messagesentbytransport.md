---
description: 'Más información acerca de: 216-MessageSentByTransport'
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: 34c10fbbf61adde102641cb44db6645ea648a646
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794382"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="f8209-103">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="f8209-103">216 - MessageSentByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="f8209-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f8209-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f8209-105">Id.</span><span class="sxs-lookup"><span data-stu-id="f8209-105">ID</span></span>|<span data-ttu-id="f8209-106">216</span><span class="sxs-lookup"><span data-stu-id="f8209-106">216</span></span>|  
|<span data-ttu-id="f8209-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f8209-107">Keywords</span></span>|<span data-ttu-id="f8209-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f8209-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f8209-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="f8209-109">Level</span></span>|<span data-ttu-id="f8209-110">Información</span><span class="sxs-lookup"><span data-stu-id="f8209-110">Information</span></span>|  
|<span data-ttu-id="f8209-111">Canal</span><span class="sxs-lookup"><span data-stu-id="f8209-111">Channel</span></span>|<span data-ttu-id="f8209-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f8209-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f8209-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8209-113">Description</span></span>  

 <span data-ttu-id="f8209-114">Este evento se produce cuando un transporte basado en TCP envía un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f8209-114">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="f8209-115">Observe que, en el nivel de transporte, pueden intercambiarse múltiples mensajes entre los clientes y servicios para una única operación.</span><span class="sxs-lookup"><span data-stu-id="f8209-115">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="f8209-116">Esto puede deberse al comportamiento de la infraestructura, siendo la seguridad un buen ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f8209-116">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="f8209-117">Por lo tanto, el número de eventos **MessageSentByTransport** que se emiten varía en función del enlace del servicio y su configuración.</span><span class="sxs-lookup"><span data-stu-id="f8209-117">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f8209-118">Message</span><span class="sxs-lookup"><span data-stu-id="f8209-118">Message</span></span>  

 <span data-ttu-id="f8209-119">El transporte ha enviado un mensaje a '%1'.</span><span class="sxs-lookup"><span data-stu-id="f8209-119">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f8209-120">Detalles</span><span class="sxs-lookup"><span data-stu-id="f8209-120">Details</span></span>  
  
|<span data-ttu-id="f8209-121">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f8209-121">Data Item Name</span></span>|<span data-ttu-id="f8209-122">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f8209-122">Data Item Type</span></span>|<span data-ttu-id="f8209-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8209-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f8209-124">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="f8209-124">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="f8209-125">La dirección a la que se ha enviado el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="f8209-125">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="f8209-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="f8209-126">HostReference</span></span>|<span data-ttu-id="f8209-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8209-127">xs:string</span></span>|<span data-ttu-id="f8209-128">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="f8209-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f8209-129">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="f8209-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f8209-130">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="f8209-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f8209-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f8209-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f8209-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f8209-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
