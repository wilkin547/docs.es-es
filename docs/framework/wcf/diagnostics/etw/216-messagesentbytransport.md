---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: b3e9e1a48951ad5a2e5e7820dc1828c20e310635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278913"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="cc4cd-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="cc4cd-102">216 - MessageSentByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="cc4cd-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="cc4cd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc4cd-104">ID</span><span class="sxs-lookup"><span data-stu-id="cc4cd-104">ID</span></span>|<span data-ttu-id="cc4cd-105">216</span><span class="sxs-lookup"><span data-stu-id="cc4cd-105">216</span></span>|  
|<span data-ttu-id="cc4cd-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="cc4cd-106">Keywords</span></span>|<span data-ttu-id="cc4cd-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cc4cd-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="cc4cd-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc4cd-108">Level</span></span>|<span data-ttu-id="cc4cd-109">Información</span><span class="sxs-lookup"><span data-stu-id="cc4cd-109">Information</span></span>|  
|<span data-ttu-id="cc4cd-110">Canal</span><span class="sxs-lookup"><span data-stu-id="cc4cd-110">Channel</span></span>|<span data-ttu-id="cc4cd-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="cc4cd-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cc4cd-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc4cd-112">Description</span></span>  

 <span data-ttu-id="cc4cd-113">Este evento se produce cuando un transporte basado en TCP envía un mensaje.</span><span class="sxs-lookup"><span data-stu-id="cc4cd-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="cc4cd-114">Observe que, en el nivel de transporte, pueden intercambiarse múltiples mensajes entre los clientes y servicios para una única operación.</span><span class="sxs-lookup"><span data-stu-id="cc4cd-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="cc4cd-115">Esto puede deberse al comportamiento de la infraestructura, siendo la seguridad un buen ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cc4cd-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="cc4cd-116">Por lo tanto, el número de eventos **MessageSentByTransport** que se emiten varía en función del enlace del servicio y su configuración.</span><span class="sxs-lookup"><span data-stu-id="cc4cd-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cc4cd-117">Message</span><span class="sxs-lookup"><span data-stu-id="cc4cd-117">Message</span></span>  

 <span data-ttu-id="cc4cd-118">El transporte ha enviado un mensaje a '%1'.</span><span class="sxs-lookup"><span data-stu-id="cc4cd-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cc4cd-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="cc4cd-119">Details</span></span>  
  
|<span data-ttu-id="cc4cd-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cc4cd-120">Data Item Name</span></span>|<span data-ttu-id="cc4cd-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cc4cd-121">Data Item Type</span></span>|<span data-ttu-id="cc4cd-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc4cd-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cc4cd-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="cc4cd-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="cc4cd-124">La dirección a la que se ha enviado el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="cc4cd-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="cc4cd-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="cc4cd-125">HostReference</span></span>|<span data-ttu-id="cc4cd-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="cc4cd-126">xs:string</span></span>|<span data-ttu-id="cc4cd-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="cc4cd-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="cc4cd-128">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="cc4cd-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="cc4cd-129">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="cc4cd-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="cc4cd-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cc4cd-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cc4cd-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cc4cd-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
