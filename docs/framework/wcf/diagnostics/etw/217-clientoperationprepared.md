---
title: 217 - ClientOperationPrepared
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3e1b4e3aab6a6a7f94bfb3783c9e32f83557db19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="0b490-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="0b490-102">217 - ClientOperationPrepared</span></span>
## <a name="properties"></a><span data-ttu-id="0b490-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0b490-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b490-104">Id.</span><span class="sxs-lookup"><span data-stu-id="0b490-104">ID</span></span>|<span data-ttu-id="0b490-105">217</span><span class="sxs-lookup"><span data-stu-id="0b490-105">217</span></span>|  
|<span data-ttu-id="0b490-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0b490-106">Keywords</span></span>|<span data-ttu-id="0b490-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0b490-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0b490-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="0b490-108">Level</span></span>|<span data-ttu-id="0b490-109">Información</span><span class="sxs-lookup"><span data-stu-id="0b490-109">Information</span></span>|  
|<span data-ttu-id="0b490-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0b490-110">Channel</span></span>|<span data-ttu-id="0b490-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="0b490-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0b490-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b490-112">Description</span></span>  
 <span data-ttu-id="0b490-113">Los clientes emiten este evento solo antes de que se envíe una operación al servicio.</span><span class="sxs-lookup"><span data-stu-id="0b490-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0b490-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0b490-114">Message</span></span>  
 <span data-ttu-id="0b490-115">El cliente ejecuta la acción '%1' asociada al contrato '%2'.</span><span class="sxs-lookup"><span data-stu-id="0b490-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="0b490-116">El mensaje se enviará a '%3'.</span><span class="sxs-lookup"><span data-stu-id="0b490-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0b490-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="0b490-117">Details</span></span>  
  
|<span data-ttu-id="0b490-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0b490-118">Data Item Name</span></span>|<span data-ttu-id="0b490-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0b490-119">Data Item Type</span></span>|<span data-ttu-id="0b490-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b490-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0b490-121">Acción</span><span class="sxs-lookup"><span data-stu-id="0b490-121">Action</span></span>|`xs:string`|<span data-ttu-id="0b490-122">El encabezado de acción de SOAP del mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="0b490-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="0b490-123">Contract Name</span><span class="sxs-lookup"><span data-stu-id="0b490-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="0b490-124">El nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="0b490-124">The name of the contract.</span></span> <span data-ttu-id="0b490-125">Ejemplo: ICalculadora.</span><span class="sxs-lookup"><span data-stu-id="0b490-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="0b490-126">Destino</span><span class="sxs-lookup"><span data-stu-id="0b490-126">Destination</span></span>|`xs:string`|<span data-ttu-id="0b490-127">La dirección del punto de conexión de servicio a la que se ha enviado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0b490-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="0b490-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="0b490-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="0b490-129">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="0b490-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0b490-130">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="0b490-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0b490-131">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="0b490-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0b490-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0b490-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0b490-133">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0b490-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
