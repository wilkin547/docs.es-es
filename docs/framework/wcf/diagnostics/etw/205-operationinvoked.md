---
title: 205 - OperationInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b4e101c4e9e5812c32b85029e9c24d983cb5e5d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="205---operationinvoked"></a><span data-ttu-id="7f949-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="7f949-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="7f949-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7f949-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7f949-104">Id.</span><span class="sxs-lookup"><span data-stu-id="7f949-104">ID</span></span>|<span data-ttu-id="7f949-105">205</span><span class="sxs-lookup"><span data-stu-id="7f949-105">205</span></span>|  
|<span data-ttu-id="7f949-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="7f949-106">Keywords</span></span>|<span data-ttu-id="7f949-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7f949-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7f949-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="7f949-108">Level</span></span>|<span data-ttu-id="7f949-109">Información</span><span class="sxs-lookup"><span data-stu-id="7f949-109">Information</span></span>|  
|<span data-ttu-id="7f949-110">Canal</span><span class="sxs-lookup"><span data-stu-id="7f949-110">Channel</span></span>|<span data-ttu-id="7f949-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="7f949-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7f949-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f949-112">Description</span></span>  
 <span data-ttu-id="7f949-113">Este evento se emite justo antes de que el `OperationInvoker` predeterminado del modelo de servicio inicie una llamada a un método.</span><span class="sxs-lookup"><span data-stu-id="7f949-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7f949-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="7f949-114">Message</span></span>  
 <span data-ttu-id="7f949-115">Un OperationInvoker invocó el método '%1'.</span><span class="sxs-lookup"><span data-stu-id="7f949-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="7f949-116">Información del autor de la llamada: '%2'.</span><span class="sxs-lookup"><span data-stu-id="7f949-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7f949-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="7f949-117">Details</span></span>  
  
|<span data-ttu-id="7f949-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7f949-118">Data Item Name</span></span>|<span data-ttu-id="7f949-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7f949-119">Data Item Type</span></span>|<span data-ttu-id="7f949-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f949-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7f949-121">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="7f949-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="7f949-122">El nombre de CLR del método invocado por `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="7f949-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="7f949-123">Información del llamador</span><span class="sxs-lookup"><span data-stu-id="7f949-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="7f949-124">La dirección IP y el número de puerto del cliente en el formato 'IPAddress:PortNumber'.</span><span class="sxs-lookup"><span data-stu-id="7f949-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="7f949-125">Los dos valores se recuperan de la propiedad de mensaje 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' en el contexto de la operación.</span><span class="sxs-lookup"><span data-stu-id="7f949-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="7f949-126">Tenga en cuenta que, para los enlaces que no son de TCP, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="7f949-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="7f949-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="7f949-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="7f949-128">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="7f949-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7f949-129">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="7f949-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7f949-130">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="7f949-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7f949-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7f949-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7f949-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7f949-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
