---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: 5979cd8ffe0e05b61af01d2aa98c4a2c63fd432c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781773"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="e0539-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="e0539-102">217 - ClientOperationPrepared</span></span>
## <a name="properties"></a><span data-ttu-id="e0539-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e0539-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0539-104">ID</span><span class="sxs-lookup"><span data-stu-id="e0539-104">ID</span></span>|<span data-ttu-id="e0539-105">217</span><span class="sxs-lookup"><span data-stu-id="e0539-105">217</span></span>|  
|<span data-ttu-id="e0539-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e0539-106">Keywords</span></span>|<span data-ttu-id="e0539-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e0539-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e0539-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="e0539-108">Level</span></span>|<span data-ttu-id="e0539-109">Información</span><span class="sxs-lookup"><span data-stu-id="e0539-109">Information</span></span>|  
|<span data-ttu-id="e0539-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e0539-110">Channel</span></span>|<span data-ttu-id="e0539-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e0539-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e0539-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0539-112">Description</span></span>  
 <span data-ttu-id="e0539-113">Los clientes emiten este evento solo antes de que se envíe una operación al servicio.</span><span class="sxs-lookup"><span data-stu-id="e0539-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e0539-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="e0539-114">Message</span></span>  
 <span data-ttu-id="e0539-115">El cliente ejecuta la acción '%1' asociada al contrato '%2'.</span><span class="sxs-lookup"><span data-stu-id="e0539-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="e0539-116">El mensaje se enviará a '%3'.</span><span class="sxs-lookup"><span data-stu-id="e0539-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e0539-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="e0539-117">Details</span></span>  
  
|<span data-ttu-id="e0539-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e0539-118">Data Item Name</span></span>|<span data-ttu-id="e0539-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e0539-119">Data Item Type</span></span>|<span data-ttu-id="e0539-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0539-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e0539-121">Acción</span><span class="sxs-lookup"><span data-stu-id="e0539-121">Action</span></span>|`xs:string`|<span data-ttu-id="e0539-122">El encabezado de acción de SOAP del mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="e0539-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="e0539-123">Contract Name</span><span class="sxs-lookup"><span data-stu-id="e0539-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="e0539-124">El nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="e0539-124">The name of the contract.</span></span> <span data-ttu-id="e0539-125">Ejemplo: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="e0539-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="e0539-126">Destino</span><span class="sxs-lookup"><span data-stu-id="e0539-126">Destination</span></span>|`xs:string`|<span data-ttu-id="e0539-127">La dirección del extremo de servicio a la que se ha enviado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e0539-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="e0539-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="e0539-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="e0539-129">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="e0539-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e0539-130">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="e0539-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e0539-131">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="e0539-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e0539-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e0539-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e0539-133">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e0539-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
