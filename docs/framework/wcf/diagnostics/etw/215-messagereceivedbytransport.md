---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: a8ba90b88ef8dbe3c8651bc565da61aae16a0a4a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781841"
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="f0adf-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="f0adf-102">215 - MessageReceivedByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="f0adf-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f0adf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0adf-104">ID</span><span class="sxs-lookup"><span data-stu-id="f0adf-104">ID</span></span>|<span data-ttu-id="f0adf-105">215</span><span class="sxs-lookup"><span data-stu-id="f0adf-105">215</span></span>|  
|<span data-ttu-id="f0adf-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0adf-106">Keywords</span></span>|<span data-ttu-id="f0adf-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f0adf-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f0adf-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f0adf-108">Level</span></span>|<span data-ttu-id="f0adf-109">Información</span><span class="sxs-lookup"><span data-stu-id="f0adf-109">Information</span></span>|  
|<span data-ttu-id="f0adf-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f0adf-110">Channel</span></span>|<span data-ttu-id="f0adf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f0adf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f0adf-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0adf-112">Description</span></span>  
 <span data-ttu-id="f0adf-113">Este evento se produce cuando un transporte basado en TCP recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f0adf-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="f0adf-114">Observe que, en el nivel de transporte, pueden intercambiarse múltiples mensajes entre los clientes y servicios para una única operación.</span><span class="sxs-lookup"><span data-stu-id="f0adf-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="f0adf-115">Esto puede deberse al comportamiento de la infraestructura, y la seguridad es un buen ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f0adf-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="f0adf-116">Por lo tanto, el número de eventos `MessageReceivedByTransport` que se emiten varía según el enlace del servicio y su configuración.</span><span class="sxs-lookup"><span data-stu-id="f0adf-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0adf-117">Este evento no se emite para transportes unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="f0adf-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f0adf-118">Mensaje</span><span class="sxs-lookup"><span data-stu-id="f0adf-118">Message</span></span>  
 <span data-ttu-id="f0adf-119">El transporte ha recibido un mensaje de '%1'.</span><span class="sxs-lookup"><span data-stu-id="f0adf-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f0adf-120">Detalles</span><span class="sxs-lookup"><span data-stu-id="f0adf-120">Details</span></span>  
  
|<span data-ttu-id="f0adf-121">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f0adf-121">Data Item Name</span></span>|<span data-ttu-id="f0adf-122">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f0adf-122">Data Item Type</span></span>|<span data-ttu-id="f0adf-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0adf-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f0adf-124">Listen Address</span><span class="sxs-lookup"><span data-stu-id="f0adf-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="f0adf-125">La dirección que recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f0adf-125">The address that received the message.</span></span>|  
|<span data-ttu-id="f0adf-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="f0adf-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="f0adf-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="f0adf-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f0adf-128">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="f0adf-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f0adf-129">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="f0adf-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f0adf-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f0adf-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f0adf-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f0adf-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
