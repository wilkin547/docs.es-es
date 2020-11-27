---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: e8aaf65bdff0718e932d07937e052541b7134f11
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278887"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="e5cc2-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="e5cc2-102">217 - ClientOperationPrepared</span></span>

## <a name="properties"></a><span data-ttu-id="e5cc2-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e5cc2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5cc2-104">ID</span><span class="sxs-lookup"><span data-stu-id="e5cc2-104">ID</span></span>|<span data-ttu-id="e5cc2-105">217</span><span class="sxs-lookup"><span data-stu-id="e5cc2-105">217</span></span>|  
|<span data-ttu-id="e5cc2-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e5cc2-106">Keywords</span></span>|<span data-ttu-id="e5cc2-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e5cc2-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e5cc2-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="e5cc2-108">Level</span></span>|<span data-ttu-id="e5cc2-109">Información</span><span class="sxs-lookup"><span data-stu-id="e5cc2-109">Information</span></span>|  
|<span data-ttu-id="e5cc2-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e5cc2-110">Channel</span></span>|<span data-ttu-id="e5cc2-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e5cc2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e5cc2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5cc2-112">Description</span></span>  

 <span data-ttu-id="e5cc2-113">Los clientes emiten este evento solo antes de que se envíe una operación al servicio.</span><span class="sxs-lookup"><span data-stu-id="e5cc2-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e5cc2-114">Message</span><span class="sxs-lookup"><span data-stu-id="e5cc2-114">Message</span></span>  

 <span data-ttu-id="e5cc2-115">El cliente ejecuta la acción '%1' asociada al contrato '%2'.</span><span class="sxs-lookup"><span data-stu-id="e5cc2-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="e5cc2-116">El mensaje se enviará a '%3'.</span><span class="sxs-lookup"><span data-stu-id="e5cc2-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e5cc2-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="e5cc2-117">Details</span></span>  
  
|<span data-ttu-id="e5cc2-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e5cc2-118">Data Item Name</span></span>|<span data-ttu-id="e5cc2-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e5cc2-119">Data Item Type</span></span>|<span data-ttu-id="e5cc2-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5cc2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e5cc2-121">Acción</span><span class="sxs-lookup"><span data-stu-id="e5cc2-121">Action</span></span>|`xs:string`|<span data-ttu-id="e5cc2-122">El encabezado de acción de SOAP del mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="e5cc2-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="e5cc2-123">Contract Name</span><span class="sxs-lookup"><span data-stu-id="e5cc2-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="e5cc2-124">El nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="e5cc2-124">The name of the contract.</span></span> <span data-ttu-id="e5cc2-125">Ejemplo: ICalculadora.</span><span class="sxs-lookup"><span data-stu-id="e5cc2-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="e5cc2-126">Destination</span><span class="sxs-lookup"><span data-stu-id="e5cc2-126">Destination</span></span>|`xs:string`|<span data-ttu-id="e5cc2-127">La dirección del extremo de servicio a la que se ha enviado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5cc2-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="e5cc2-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="e5cc2-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="e5cc2-129">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="e5cc2-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e5cc2-130">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="e5cc2-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e5cc2-131">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="e5cc2-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e5cc2-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e5cc2-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e5cc2-133">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e5cc2-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
