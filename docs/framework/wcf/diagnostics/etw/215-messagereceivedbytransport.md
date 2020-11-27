---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: 2f247e751a0690f13d059eff29d633c6d047775d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279082"
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="4fff8-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="4fff8-102">215 - MessageReceivedByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="4fff8-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4fff8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4fff8-104">ID</span><span class="sxs-lookup"><span data-stu-id="4fff8-104">ID</span></span>|<span data-ttu-id="4fff8-105">215</span><span class="sxs-lookup"><span data-stu-id="4fff8-105">215</span></span>|  
|<span data-ttu-id="4fff8-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4fff8-106">Keywords</span></span>|<span data-ttu-id="4fff8-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4fff8-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="4fff8-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="4fff8-108">Level</span></span>|<span data-ttu-id="4fff8-109">Información</span><span class="sxs-lookup"><span data-stu-id="4fff8-109">Information</span></span>|  
|<span data-ttu-id="4fff8-110">Canal</span><span class="sxs-lookup"><span data-stu-id="4fff8-110">Channel</span></span>|<span data-ttu-id="4fff8-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4fff8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4fff8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fff8-112">Description</span></span>  

 <span data-ttu-id="4fff8-113">Este evento se produce cuando un transporte basado en TCP recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="4fff8-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="4fff8-114">Observe que, en el nivel de transporte, pueden intercambiarse múltiples mensajes entre los clientes y servicios para una única operación.</span><span class="sxs-lookup"><span data-stu-id="4fff8-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="4fff8-115">Esto puede deberse al comportamiento de la infraestructura, y la seguridad es un buen ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4fff8-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="4fff8-116">Por lo tanto, el número de eventos `MessageReceivedByTransport` que se emiten varía según el enlace del servicio y su configuración.</span><span class="sxs-lookup"><span data-stu-id="4fff8-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4fff8-117">Este evento no se emite para transportes unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="4fff8-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4fff8-118">Message</span><span class="sxs-lookup"><span data-stu-id="4fff8-118">Message</span></span>  

 <span data-ttu-id="4fff8-119">El transporte ha recibido un mensaje de '%1'.</span><span class="sxs-lookup"><span data-stu-id="4fff8-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4fff8-120">Detalles</span><span class="sxs-lookup"><span data-stu-id="4fff8-120">Details</span></span>  
  
|<span data-ttu-id="4fff8-121">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4fff8-121">Data Item Name</span></span>|<span data-ttu-id="4fff8-122">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4fff8-122">Data Item Type</span></span>|<span data-ttu-id="4fff8-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fff8-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4fff8-124">Listen Address</span><span class="sxs-lookup"><span data-stu-id="4fff8-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="4fff8-125">La dirección que recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4fff8-125">The address that received the message.</span></span>|  
|<span data-ttu-id="4fff8-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="4fff8-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="4fff8-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="4fff8-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4fff8-128">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="4fff8-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4fff8-129">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="4fff8-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4fff8-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4fff8-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4fff8-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4fff8-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
