---
title: 222 - OperationFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21ed3dc21d5caecd64cc3740e2a9a6e8a699bbd2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="222---operationfailed"></a><span data-ttu-id="35c8d-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="35c8d-102">222 - OperationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="35c8d-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="35c8d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35c8d-104">Id.</span><span class="sxs-lookup"><span data-stu-id="35c8d-104">ID</span></span>|<span data-ttu-id="35c8d-105">222</span><span class="sxs-lookup"><span data-stu-id="35c8d-105">222</span></span>|  
|<span data-ttu-id="35c8d-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="35c8d-106">Keywords</span></span>|<span data-ttu-id="35c8d-107">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="35c8d-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="35c8d-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="35c8d-108">Level</span></span>|<span data-ttu-id="35c8d-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="35c8d-109">Warning</span></span>|  
|<span data-ttu-id="35c8d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="35c8d-110">Channel</span></span>|<span data-ttu-id="35c8d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="35c8d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="35c8d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="35c8d-112">Description</span></span>  
 <span data-ttu-id="35c8d-113">Este evento se emite cuando `OperationInvoker` predeterminado del modelo de servicio detecta una excepción al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="35c8d-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="35c8d-114">Tenga en cuenta que las excepciones que derivan de `FaultException` hacen que este evento no se emita.</span><span class="sxs-lookup"><span data-stu-id="35c8d-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="35c8d-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="35c8d-115">Message</span></span>  
 <span data-ttu-id="35c8d-116">El método '%1' produjo una excepción no controlada al invocarse por OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="35c8d-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="35c8d-117">La duración de la llamada al método fue de '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="35c8d-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="35c8d-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="35c8d-118">Details</span></span>  
  
|<span data-ttu-id="35c8d-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="35c8d-119">Data Item Name</span></span>|<span data-ttu-id="35c8d-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="35c8d-120">Data Item Type</span></span>|<span data-ttu-id="35c8d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="35c8d-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="35c8d-122">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="35c8d-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="35c8d-123">El nombre de CLR del método invocado por `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="35c8d-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="35c8d-124">Duración</span><span class="sxs-lookup"><span data-stu-id="35c8d-124">Duration</span></span>|`xs:long`|<span data-ttu-id="35c8d-125">El tiempo, en milisegundos, que tardó `OperationInvoker` en invocar el método.</span><span class="sxs-lookup"><span data-stu-id="35c8d-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="35c8d-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="35c8d-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="35c8d-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="35c8d-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="35c8d-128">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="35c8d-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="35c8d-129">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="35c8d-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="35c8d-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="35c8d-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="35c8d-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="35c8d-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
