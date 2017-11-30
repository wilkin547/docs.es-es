---
title: 218 - ClientOperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ea826aa99e847f74c5a44113f2ae16d7322873f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="218---clientoperationcompleted"></a><span data-ttu-id="a21f7-102">218 - ClientOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="a21f7-102">218 - ClientOperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="a21f7-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a21f7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a21f7-104">Id.</span><span class="sxs-lookup"><span data-stu-id="a21f7-104">ID</span></span>|<span data-ttu-id="a21f7-105">218</span><span class="sxs-lookup"><span data-stu-id="a21f7-105">218</span></span>|  
|<span data-ttu-id="a21f7-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a21f7-106">Keywords</span></span>|<span data-ttu-id="a21f7-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a21f7-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a21f7-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a21f7-108">Level</span></span>|<span data-ttu-id="a21f7-109">Información</span><span class="sxs-lookup"><span data-stu-id="a21f7-109">Information</span></span>|  
|<span data-ttu-id="a21f7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a21f7-110">Channel</span></span>|<span data-ttu-id="a21f7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a21f7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a21f7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a21f7-112">Description</span></span>  
 <span data-ttu-id="a21f7-113">Los clientes emiten este evento justo después de finalizar una operación.</span><span class="sxs-lookup"><span data-stu-id="a21f7-113">This event is emitted by clients just after an operation completes.</span></span> <span data-ttu-id="a21f7-114">Para las operaciones unidireccionales, esto es en cuanto se haya enviado correctamente el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a21f7-114">For one-way operations, this is just after the message is sent successfully.</span></span> <span data-ttu-id="a21f7-115">Para las operaciones de solicitud-respuesta, esto es una vez recibida la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a21f7-115">For request-response operations this is after the response is received.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a21f7-116">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a21f7-116">Message</span></span>  
 <span data-ttu-id="a21f7-117">El cliente ha terminado de ejecutar la acción '%1' asociada al contrato '%2'.</span><span class="sxs-lookup"><span data-stu-id="a21f7-117">The Client completed executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="a21f7-118">El mensaje se envió a '%3'.</span><span class="sxs-lookup"><span data-stu-id="a21f7-118">The message was sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a21f7-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="a21f7-119">Details</span></span>  
  
|<span data-ttu-id="a21f7-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a21f7-120">Data Item Name</span></span>|<span data-ttu-id="a21f7-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a21f7-121">Data Item Type</span></span>|<span data-ttu-id="a21f7-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="a21f7-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a21f7-123">Acción</span><span class="sxs-lookup"><span data-stu-id="a21f7-123">Action</span></span>|<span data-ttu-id="a21f7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a21f7-124">xs:string</span></span>|<span data-ttu-id="a21f7-125">El encabezado de acción de SOAP del mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="a21f7-125">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="a21f7-126">Contract Name</span><span class="sxs-lookup"><span data-stu-id="a21f7-126">Contract Name</span></span>|`xs:string`|<span data-ttu-id="a21f7-127">El nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="a21f7-127">The name of the contract.</span></span> <span data-ttu-id="a21f7-128">Ejemplo: ICalculadora.</span><span class="sxs-lookup"><span data-stu-id="a21f7-128">Example: ICalculator.</span></span>|  
|<span data-ttu-id="a21f7-129">Destino</span><span class="sxs-lookup"><span data-stu-id="a21f7-129">Destination</span></span>|`xs:string`|<span data-ttu-id="a21f7-130">La dirección del punto de conexión de servicio a la que se ha enviado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a21f7-130">The address of the service endpoint that the message was sent to.</span></span>|  
|<span data-ttu-id="a21f7-131">HostReference</span><span class="sxs-lookup"><span data-stu-id="a21f7-131">HostReference</span></span>|`xs:string`|<span data-ttu-id="a21f7-132">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="a21f7-132">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a21f7-133">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="a21f7-133">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a21f7-134">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="a21f7-134">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a21f7-135">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a21f7-135">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a21f7-136">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a21f7-136">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
