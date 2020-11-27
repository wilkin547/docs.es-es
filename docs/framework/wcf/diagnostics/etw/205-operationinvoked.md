---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: c36294a4a430c3e372e8213246e85dba45ce03c8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286024"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="fcdaa-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="fcdaa-102">205 - OperationInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="fcdaa-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fcdaa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fcdaa-104">ID</span><span class="sxs-lookup"><span data-stu-id="fcdaa-104">ID</span></span>|<span data-ttu-id="fcdaa-105">205</span><span class="sxs-lookup"><span data-stu-id="fcdaa-105">205</span></span>|  
|<span data-ttu-id="fcdaa-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="fcdaa-106">Keywords</span></span>|<span data-ttu-id="fcdaa-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fcdaa-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="fcdaa-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="fcdaa-108">Level</span></span>|<span data-ttu-id="fcdaa-109">Información</span><span class="sxs-lookup"><span data-stu-id="fcdaa-109">Information</span></span>|  
|<span data-ttu-id="fcdaa-110">Canal</span><span class="sxs-lookup"><span data-stu-id="fcdaa-110">Channel</span></span>|<span data-ttu-id="fcdaa-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="fcdaa-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fcdaa-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcdaa-112">Description</span></span>  

 <span data-ttu-id="fcdaa-113">Este evento se emite justo antes de que el `OperationInvoker` predeterminado del modelo de servicio inicie una llamada a un método.</span><span class="sxs-lookup"><span data-stu-id="fcdaa-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fcdaa-114">Message</span><span class="sxs-lookup"><span data-stu-id="fcdaa-114">Message</span></span>  

 <span data-ttu-id="fcdaa-115">Un OperationInvoker invocó el método '%1'.</span><span class="sxs-lookup"><span data-stu-id="fcdaa-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="fcdaa-116">Información del autor de la llamada: '%2'.</span><span class="sxs-lookup"><span data-stu-id="fcdaa-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fcdaa-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="fcdaa-117">Details</span></span>  
  
|<span data-ttu-id="fcdaa-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fcdaa-118">Data Item Name</span></span>|<span data-ttu-id="fcdaa-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fcdaa-119">Data Item Type</span></span>|<span data-ttu-id="fcdaa-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcdaa-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fcdaa-121">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="fcdaa-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="fcdaa-122">El nombre de CLR del método invocado por `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="fcdaa-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="fcdaa-123">Información del llamador</span><span class="sxs-lookup"><span data-stu-id="fcdaa-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="fcdaa-124">La dirección IP y el número de puerto del cliente en el formato 'IPAddress:PortNumber'.</span><span class="sxs-lookup"><span data-stu-id="fcdaa-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="fcdaa-125">Los dos valores se recuperan de la propiedad de mensaje 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' en el contexto de la operación.</span><span class="sxs-lookup"><span data-stu-id="fcdaa-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="fcdaa-126">Tenga en cuenta que, para los enlaces que no son de TCP, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="fcdaa-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="fcdaa-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="fcdaa-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="fcdaa-128">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="fcdaa-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="fcdaa-129">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="fcdaa-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="fcdaa-130">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="fcdaa-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="fcdaa-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fcdaa-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fcdaa-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fcdaa-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
