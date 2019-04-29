---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: e95b6923d21307b2ef68d4a5369b3cee86540239
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781984"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="f609a-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="f609a-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="f609a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f609a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f609a-104">ID</span><span class="sxs-lookup"><span data-stu-id="f609a-104">ID</span></span>|<span data-ttu-id="f609a-105">205</span><span class="sxs-lookup"><span data-stu-id="f609a-105">205</span></span>|  
|<span data-ttu-id="f609a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f609a-106">Keywords</span></span>|<span data-ttu-id="f609a-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f609a-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f609a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f609a-108">Level</span></span>|<span data-ttu-id="f609a-109">Información</span><span class="sxs-lookup"><span data-stu-id="f609a-109">Information</span></span>|  
|<span data-ttu-id="f609a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f609a-110">Channel</span></span>|<span data-ttu-id="f609a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f609a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f609a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f609a-112">Description</span></span>  
 <span data-ttu-id="f609a-113">Este evento se emite justo antes de que el `OperationInvoker` predeterminado del modelo de servicio inicie una llamada a un método.</span><span class="sxs-lookup"><span data-stu-id="f609a-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f609a-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="f609a-114">Message</span></span>  
 <span data-ttu-id="f609a-115">Un OperationInvoker invocó el método '%1'.</span><span class="sxs-lookup"><span data-stu-id="f609a-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="f609a-116">Información del autor de la llamada: '%2'.</span><span class="sxs-lookup"><span data-stu-id="f609a-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f609a-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="f609a-117">Details</span></span>  
  
|<span data-ttu-id="f609a-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f609a-118">Data Item Name</span></span>|<span data-ttu-id="f609a-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f609a-119">Data Item Type</span></span>|<span data-ttu-id="f609a-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f609a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f609a-121">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="f609a-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="f609a-122">El nombre de CLR del método invocado por `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="f609a-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="f609a-123">Información del llamador</span><span class="sxs-lookup"><span data-stu-id="f609a-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="f609a-124">La dirección IP y el número de puerto del cliente en el formato 'IPAddress:PortNumber'.</span><span class="sxs-lookup"><span data-stu-id="f609a-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="f609a-125">Los dos valores se recuperan de la propiedad de mensaje 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' en el contexto de la operación.</span><span class="sxs-lookup"><span data-stu-id="f609a-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="f609a-126">Tenga en cuenta que, para los enlaces que no son de TCP, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="f609a-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="f609a-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="f609a-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="f609a-128">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="f609a-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f609a-129">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="f609a-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f609a-130">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="f609a-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f609a-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f609a-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f609a-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f609a-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
