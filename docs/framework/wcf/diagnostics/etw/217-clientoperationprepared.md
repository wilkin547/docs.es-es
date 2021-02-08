---
description: 'Más información acerca de: 217-ClientOperationPrepared'
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: eab6a9a654e6e48a8831f238cdf3a3bf7a9f62d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794356"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="33afa-103">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="33afa-103">217 - ClientOperationPrepared</span></span>

## <a name="properties"></a><span data-ttu-id="33afa-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="33afa-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33afa-105">Id.</span><span class="sxs-lookup"><span data-stu-id="33afa-105">ID</span></span>|<span data-ttu-id="33afa-106">217</span><span class="sxs-lookup"><span data-stu-id="33afa-106">217</span></span>|  
|<span data-ttu-id="33afa-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="33afa-107">Keywords</span></span>|<span data-ttu-id="33afa-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="33afa-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="33afa-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="33afa-109">Level</span></span>|<span data-ttu-id="33afa-110">Información</span><span class="sxs-lookup"><span data-stu-id="33afa-110">Information</span></span>|  
|<span data-ttu-id="33afa-111">Canal</span><span class="sxs-lookup"><span data-stu-id="33afa-111">Channel</span></span>|<span data-ttu-id="33afa-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="33afa-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="33afa-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="33afa-113">Description</span></span>  

 <span data-ttu-id="33afa-114">Los clientes emiten este evento solo antes de que se envíe una operación al servicio.</span><span class="sxs-lookup"><span data-stu-id="33afa-114">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="33afa-115">Message</span><span class="sxs-lookup"><span data-stu-id="33afa-115">Message</span></span>  

 <span data-ttu-id="33afa-116">El cliente ejecuta la acción '%1' asociada al contrato '%2'.</span><span class="sxs-lookup"><span data-stu-id="33afa-116">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="33afa-117">El mensaje se enviará a '%3'.</span><span class="sxs-lookup"><span data-stu-id="33afa-117">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="33afa-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="33afa-118">Details</span></span>  
  
|<span data-ttu-id="33afa-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="33afa-119">Data Item Name</span></span>|<span data-ttu-id="33afa-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="33afa-120">Data Item Type</span></span>|<span data-ttu-id="33afa-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="33afa-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="33afa-122">Acción</span><span class="sxs-lookup"><span data-stu-id="33afa-122">Action</span></span>|`xs:string`|<span data-ttu-id="33afa-123">El encabezado de acción de SOAP del mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="33afa-123">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="33afa-124">Contract Name</span><span class="sxs-lookup"><span data-stu-id="33afa-124">Contract Name</span></span>|`xs:string`|<span data-ttu-id="33afa-125">El nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="33afa-125">The name of the contract.</span></span> <span data-ttu-id="33afa-126">Ejemplo: ICalculadora.</span><span class="sxs-lookup"><span data-stu-id="33afa-126">Example: ICalculator.</span></span>|  
|<span data-ttu-id="33afa-127">Destination</span><span class="sxs-lookup"><span data-stu-id="33afa-127">Destination</span></span>|`xs:string`|<span data-ttu-id="33afa-128">La dirección del extremo de servicio a la que se ha enviado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="33afa-128">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="33afa-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="33afa-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="33afa-130">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="33afa-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="33afa-131">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="33afa-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="33afa-132">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="33afa-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="33afa-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="33afa-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="33afa-134">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="33afa-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
