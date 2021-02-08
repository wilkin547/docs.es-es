---
description: 'Más información acerca de: 218-ClientOperationCompleted'
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: 3719b77ce653c5177cf7b92901ecd51982504b83
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794343"
---
# <a name="218---clientoperationcompleted"></a><span data-ttu-id="b6263-103">218 - ClientOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="b6263-103">218 - ClientOperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="b6263-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b6263-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6263-105">Id.</span><span class="sxs-lookup"><span data-stu-id="b6263-105">ID</span></span>|<span data-ttu-id="b6263-106">218</span><span class="sxs-lookup"><span data-stu-id="b6263-106">218</span></span>|  
|<span data-ttu-id="b6263-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b6263-107">Keywords</span></span>|<span data-ttu-id="b6263-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b6263-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b6263-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="b6263-109">Level</span></span>|<span data-ttu-id="b6263-110">Información</span><span class="sxs-lookup"><span data-stu-id="b6263-110">Information</span></span>|  
|<span data-ttu-id="b6263-111">Canal</span><span class="sxs-lookup"><span data-stu-id="b6263-111">Channel</span></span>|<span data-ttu-id="b6263-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b6263-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b6263-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6263-113">Description</span></span>  

 <span data-ttu-id="b6263-114">Los clientes emiten este evento justo después de finalizar una operación.</span><span class="sxs-lookup"><span data-stu-id="b6263-114">This event is emitted by clients just after an operation completes.</span></span> <span data-ttu-id="b6263-115">Para las operaciones unidireccionales, esto es en cuanto se haya enviado correctamente el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b6263-115">For one-way operations, this is just after the message is sent successfully.</span></span> <span data-ttu-id="b6263-116">Para las operaciones de solicitud-respuesta, esto es una vez recibida la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b6263-116">For request-response operations this is after the response is received.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b6263-117">Message</span><span class="sxs-lookup"><span data-stu-id="b6263-117">Message</span></span>  

 <span data-ttu-id="b6263-118">El cliente ha terminado de ejecutar la acción '%1' asociada al contrato '%2'.</span><span class="sxs-lookup"><span data-stu-id="b6263-118">The Client completed executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="b6263-119">El mensaje se envió a '%3'.</span><span class="sxs-lookup"><span data-stu-id="b6263-119">The message was sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b6263-120">Detalles</span><span class="sxs-lookup"><span data-stu-id="b6263-120">Details</span></span>  
  
|<span data-ttu-id="b6263-121">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b6263-121">Data Item Name</span></span>|<span data-ttu-id="b6263-122">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b6263-122">Data Item Type</span></span>|<span data-ttu-id="b6263-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6263-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b6263-124">Acción</span><span class="sxs-lookup"><span data-stu-id="b6263-124">Action</span></span>|<span data-ttu-id="b6263-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6263-125">xs:string</span></span>|<span data-ttu-id="b6263-126">El encabezado de acción de SOAP del mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="b6263-126">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="b6263-127">Contract Name</span><span class="sxs-lookup"><span data-stu-id="b6263-127">Contract Name</span></span>|`xs:string`|<span data-ttu-id="b6263-128">El nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="b6263-128">The name of the contract.</span></span> <span data-ttu-id="b6263-129">Ejemplo: ICalculadora.</span><span class="sxs-lookup"><span data-stu-id="b6263-129">Example: ICalculator.</span></span>|  
|<span data-ttu-id="b6263-130">Destination</span><span class="sxs-lookup"><span data-stu-id="b6263-130">Destination</span></span>|`xs:string`|<span data-ttu-id="b6263-131">La dirección del punto de conexión de servicio a la que se ha enviado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b6263-131">The address of the service endpoint that the message was sent to.</span></span>|  
|<span data-ttu-id="b6263-132">HostReference</span><span class="sxs-lookup"><span data-stu-id="b6263-132">HostReference</span></span>|`xs:string`|<span data-ttu-id="b6263-133">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="b6263-133">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b6263-134">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="b6263-134">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b6263-135">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="b6263-135">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b6263-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b6263-136">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b6263-137">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b6263-137">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
