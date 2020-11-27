---
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: d74aa77aff7b45b50f6891c999889011d9e03381
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278861"
---
# <a name="218---clientoperationcompleted"></a><span data-ttu-id="c14c1-102">218 - ClientOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="c14c1-102">218 - ClientOperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="c14c1-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c14c1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c14c1-104">ID</span><span class="sxs-lookup"><span data-stu-id="c14c1-104">ID</span></span>|<span data-ttu-id="c14c1-105">218</span><span class="sxs-lookup"><span data-stu-id="c14c1-105">218</span></span>|  
|<span data-ttu-id="c14c1-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c14c1-106">Keywords</span></span>|<span data-ttu-id="c14c1-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c14c1-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="c14c1-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="c14c1-108">Level</span></span>|<span data-ttu-id="c14c1-109">Información</span><span class="sxs-lookup"><span data-stu-id="c14c1-109">Information</span></span>|  
|<span data-ttu-id="c14c1-110">Canal</span><span class="sxs-lookup"><span data-stu-id="c14c1-110">Channel</span></span>|<span data-ttu-id="c14c1-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c14c1-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c14c1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c14c1-112">Description</span></span>  

 <span data-ttu-id="c14c1-113">Los clientes emiten este evento justo después de finalizar una operación.</span><span class="sxs-lookup"><span data-stu-id="c14c1-113">This event is emitted by clients just after an operation completes.</span></span> <span data-ttu-id="c14c1-114">Para las operaciones unidireccionales, esto es en cuanto se haya enviado correctamente el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c14c1-114">For one-way operations, this is just after the message is sent successfully.</span></span> <span data-ttu-id="c14c1-115">Para las operaciones de solicitud-respuesta, esto es una vez recibida la respuesta.</span><span class="sxs-lookup"><span data-stu-id="c14c1-115">For request-response operations this is after the response is received.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c14c1-116">Message</span><span class="sxs-lookup"><span data-stu-id="c14c1-116">Message</span></span>  

 <span data-ttu-id="c14c1-117">El cliente ha terminado de ejecutar la acción '%1' asociada al contrato '%2'.</span><span class="sxs-lookup"><span data-stu-id="c14c1-117">The Client completed executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="c14c1-118">El mensaje se envió a '%3'.</span><span class="sxs-lookup"><span data-stu-id="c14c1-118">The message was sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c14c1-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="c14c1-119">Details</span></span>  
  
|<span data-ttu-id="c14c1-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c14c1-120">Data Item Name</span></span>|<span data-ttu-id="c14c1-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c14c1-121">Data Item Type</span></span>|<span data-ttu-id="c14c1-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="c14c1-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c14c1-123">Acción</span><span class="sxs-lookup"><span data-stu-id="c14c1-123">Action</span></span>|<span data-ttu-id="c14c1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c14c1-124">xs:string</span></span>|<span data-ttu-id="c14c1-125">El encabezado de acción de SOAP del mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="c14c1-125">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="c14c1-126">Contract Name</span><span class="sxs-lookup"><span data-stu-id="c14c1-126">Contract Name</span></span>|`xs:string`|<span data-ttu-id="c14c1-127">El nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="c14c1-127">The name of the contract.</span></span> <span data-ttu-id="c14c1-128">Ejemplo: ICalculadora.</span><span class="sxs-lookup"><span data-stu-id="c14c1-128">Example: ICalculator.</span></span>|  
|<span data-ttu-id="c14c1-129">Destination</span><span class="sxs-lookup"><span data-stu-id="c14c1-129">Destination</span></span>|`xs:string`|<span data-ttu-id="c14c1-130">La dirección del punto de conexión de servicio a la que se ha enviado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c14c1-130">The address of the service endpoint that the message was sent to.</span></span>|  
|<span data-ttu-id="c14c1-131">HostReference</span><span class="sxs-lookup"><span data-stu-id="c14c1-131">HostReference</span></span>|`xs:string`|<span data-ttu-id="c14c1-132">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="c14c1-132">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="c14c1-133">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="c14c1-133">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="c14c1-134">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="c14c1-134">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="c14c1-135">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c14c1-135">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c14c1-136">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c14c1-136">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
