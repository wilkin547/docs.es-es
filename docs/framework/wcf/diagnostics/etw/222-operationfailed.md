---
description: 'Más información acerca de: 222-OperationFailed'
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: ea07dbabb651413f213db6789f2af8059d2595c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794304"
---
# <a name="222---operationfailed"></a><span data-ttu-id="b0bb1-103">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="b0bb1-103">222 - OperationFailed</span></span>

## <a name="properties"></a><span data-ttu-id="b0bb1-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b0bb1-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b0bb1-105">Id.</span><span class="sxs-lookup"><span data-stu-id="b0bb1-105">ID</span></span>|<span data-ttu-id="b0bb1-106">222</span><span class="sxs-lookup"><span data-stu-id="b0bb1-106">222</span></span>|  
|<span data-ttu-id="b0bb1-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b0bb1-107">Keywords</span></span>|<span data-ttu-id="b0bb1-108">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b0bb1-108">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b0bb1-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0bb1-109">Level</span></span>|<span data-ttu-id="b0bb1-110">Advertencia</span><span class="sxs-lookup"><span data-stu-id="b0bb1-110">Warning</span></span>|  
|<span data-ttu-id="b0bb1-111">Canal</span><span class="sxs-lookup"><span data-stu-id="b0bb1-111">Channel</span></span>|<span data-ttu-id="b0bb1-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b0bb1-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b0bb1-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0bb1-113">Description</span></span>  

 <span data-ttu-id="b0bb1-114">Este evento se emite cuando `OperationInvoker` predeterminado del modelo de servicio detecta una excepción al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="b0bb1-114">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="b0bb1-115">Tenga en cuenta que las excepciones que derivan de `FaultException` hacen que este evento no se emita.</span><span class="sxs-lookup"><span data-stu-id="b0bb1-115">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b0bb1-116">Message</span><span class="sxs-lookup"><span data-stu-id="b0bb1-116">Message</span></span>  

 <span data-ttu-id="b0bb1-117">El método '%1' produjo una excepción no controlada al invocarse por OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="b0bb1-117">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="b0bb1-118">La duración de la llamada al método fue de '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="b0bb1-118">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b0bb1-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="b0bb1-119">Details</span></span>  
  
|<span data-ttu-id="b0bb1-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b0bb1-120">Data Item Name</span></span>|<span data-ttu-id="b0bb1-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b0bb1-121">Data Item Type</span></span>|<span data-ttu-id="b0bb1-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0bb1-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b0bb1-123">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="b0bb1-123">Method Name</span></span>|`xs:string`|<span data-ttu-id="b0bb1-124">El nombre de CLR del método invocado por `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="b0bb1-124">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="b0bb1-125">Duration</span><span class="sxs-lookup"><span data-stu-id="b0bb1-125">Duration</span></span>|`xs:long`|<span data-ttu-id="b0bb1-126">El tiempo, en milisegundos, que tardó `OperationInvoker` en invocar el método.</span><span class="sxs-lookup"><span data-stu-id="b0bb1-126">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="b0bb1-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="b0bb1-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="b0bb1-128">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="b0bb1-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b0bb1-129">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="b0bb1-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b0bb1-130">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="b0bb1-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b0bb1-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b0bb1-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b0bb1-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b0bb1-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
