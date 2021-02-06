---
description: 'Más información acerca de: 205-OperationInvoked'
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: 09afe4c29c5f56b06bbf524dd13d88ddf2319063
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644975"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="75cde-103">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="75cde-103">205 - OperationInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="75cde-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="75cde-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75cde-105">Id.</span><span class="sxs-lookup"><span data-stu-id="75cde-105">ID</span></span>|<span data-ttu-id="75cde-106">205</span><span class="sxs-lookup"><span data-stu-id="75cde-106">205</span></span>|  
|<span data-ttu-id="75cde-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="75cde-107">Keywords</span></span>|<span data-ttu-id="75cde-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="75cde-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="75cde-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="75cde-109">Level</span></span>|<span data-ttu-id="75cde-110">Información</span><span class="sxs-lookup"><span data-stu-id="75cde-110">Information</span></span>|  
|<span data-ttu-id="75cde-111">Canal</span><span class="sxs-lookup"><span data-stu-id="75cde-111">Channel</span></span>|<span data-ttu-id="75cde-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="75cde-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="75cde-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="75cde-113">Description</span></span>  

 <span data-ttu-id="75cde-114">Este evento se emite justo antes de que el `OperationInvoker` predeterminado del modelo de servicio inicie una llamada a un método.</span><span class="sxs-lookup"><span data-stu-id="75cde-114">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="75cde-115">Message</span><span class="sxs-lookup"><span data-stu-id="75cde-115">Message</span></span>  

 <span data-ttu-id="75cde-116">Un OperationInvoker invocó el método '%1'.</span><span class="sxs-lookup"><span data-stu-id="75cde-116">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="75cde-117">Información del autor de la llamada: '%2'.</span><span class="sxs-lookup"><span data-stu-id="75cde-117">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="75cde-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="75cde-118">Details</span></span>  
  
|<span data-ttu-id="75cde-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="75cde-119">Data Item Name</span></span>|<span data-ttu-id="75cde-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="75cde-120">Data Item Type</span></span>|<span data-ttu-id="75cde-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="75cde-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="75cde-122">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="75cde-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="75cde-123">El nombre de CLR del método invocado por `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="75cde-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="75cde-124">Información del llamador</span><span class="sxs-lookup"><span data-stu-id="75cde-124">Caller Information</span></span>|`xs:string`|<span data-ttu-id="75cde-125">La dirección IP y el número de puerto del cliente en el formato 'IPAddress:PortNumber'.</span><span class="sxs-lookup"><span data-stu-id="75cde-125">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="75cde-126">Los dos valores se recuperan de la propiedad de mensaje 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' en el contexto de la operación.</span><span class="sxs-lookup"><span data-stu-id="75cde-126">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="75cde-127">Tenga en cuenta que, para los enlaces que no son de TCP, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="75cde-127">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="75cde-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="75cde-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="75cde-129">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="75cde-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="75cde-130">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="75cde-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="75cde-131">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="75cde-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="75cde-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="75cde-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="75cde-133">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="75cde-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
