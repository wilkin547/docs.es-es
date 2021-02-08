---
description: 'Más información acerca de: 215-MessageReceivedByTransport'
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: e9645cfc8c4013f8891cb645db7df35477a57412
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794369"
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="b3094-103">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="b3094-103">215 - MessageReceivedByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="b3094-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b3094-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b3094-105">Id.</span><span class="sxs-lookup"><span data-stu-id="b3094-105">ID</span></span>|<span data-ttu-id="b3094-106">215</span><span class="sxs-lookup"><span data-stu-id="b3094-106">215</span></span>|  
|<span data-ttu-id="b3094-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b3094-107">Keywords</span></span>|<span data-ttu-id="b3094-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b3094-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b3094-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="b3094-109">Level</span></span>|<span data-ttu-id="b3094-110">Información</span><span class="sxs-lookup"><span data-stu-id="b3094-110">Information</span></span>|  
|<span data-ttu-id="b3094-111">Canal</span><span class="sxs-lookup"><span data-stu-id="b3094-111">Channel</span></span>|<span data-ttu-id="b3094-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b3094-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b3094-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3094-113">Description</span></span>  

 <span data-ttu-id="b3094-114">Este evento se produce cuando un transporte basado en TCP recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="b3094-114">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="b3094-115">Observe que, en el nivel de transporte, pueden intercambiarse múltiples mensajes entre los clientes y servicios para una única operación.</span><span class="sxs-lookup"><span data-stu-id="b3094-115">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="b3094-116">Esto puede deberse al comportamiento de la infraestructura, y la seguridad es un buen ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b3094-116">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="b3094-117">Por lo tanto, el número de eventos `MessageReceivedByTransport` que se emiten varía según el enlace del servicio y su configuración.</span><span class="sxs-lookup"><span data-stu-id="b3094-117">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3094-118">Este evento no se emite para transportes unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="b3094-118">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b3094-119">Message</span><span class="sxs-lookup"><span data-stu-id="b3094-119">Message</span></span>  

 <span data-ttu-id="b3094-120">El transporte ha recibido un mensaje de '%1'.</span><span class="sxs-lookup"><span data-stu-id="b3094-120">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b3094-121">Detalles</span><span class="sxs-lookup"><span data-stu-id="b3094-121">Details</span></span>  
  
|<span data-ttu-id="b3094-122">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b3094-122">Data Item Name</span></span>|<span data-ttu-id="b3094-123">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b3094-123">Data Item Type</span></span>|<span data-ttu-id="b3094-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3094-124">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b3094-125">Listen Address</span><span class="sxs-lookup"><span data-stu-id="b3094-125">Listen Address</span></span>|`xs:string`|<span data-ttu-id="b3094-126">La dirección que recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b3094-126">The address that received the message.</span></span>|  
|<span data-ttu-id="b3094-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="b3094-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="b3094-128">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="b3094-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b3094-129">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="b3094-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b3094-130">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="b3094-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b3094-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b3094-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b3094-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b3094-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
