---
description: 'Más información acerca de: 223-OperationFaulted'
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: e4155516e07568d4ee4ca76d63754ec4171e1064
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794291"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="b483c-103">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="b483c-103">223 - OperationFaulted</span></span>

## <a name="properties"></a><span data-ttu-id="b483c-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b483c-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b483c-105">Id.</span><span class="sxs-lookup"><span data-stu-id="b483c-105">ID</span></span>|<span data-ttu-id="b483c-106">223</span><span class="sxs-lookup"><span data-stu-id="b483c-106">223</span></span>|  
|<span data-ttu-id="b483c-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b483c-107">Keywords</span></span>|<span data-ttu-id="b483c-108">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b483c-108">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b483c-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="b483c-109">Level</span></span>|<span data-ttu-id="b483c-110">Advertencia</span><span class="sxs-lookup"><span data-stu-id="b483c-110">Warning</span></span>|  
|<span data-ttu-id="b483c-111">Canal</span><span class="sxs-lookup"><span data-stu-id="b483c-111">Channel</span></span>|<span data-ttu-id="b483c-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b483c-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b483c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b483c-113">Description</span></span>  

 <span data-ttu-id="b483c-114">Este evento se emite cuando `OperationInvoker` predeterminado del modelo de servicio detecta una excepción que deriva de `FaultException` al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="b483c-114">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b483c-115">Message</span><span class="sxs-lookup"><span data-stu-id="b483c-115">Message</span></span>  

 <span data-ttu-id="b483c-116">El método '% 1' produjo una FaultException al invocarse por OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="b483c-116">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="b483c-117">La duración de la llamada al método fue de '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="b483c-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b483c-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="b483c-118">Details</span></span>  
  
|<span data-ttu-id="b483c-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b483c-119">Data Item Name</span></span>|<span data-ttu-id="b483c-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b483c-120">Data Item Type</span></span>|<span data-ttu-id="b483c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="b483c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b483c-122">MethodName</span><span class="sxs-lookup"><span data-stu-id="b483c-122">MethodName</span></span>|`xs:string`|<span data-ttu-id="b483c-123">El nombre de CLR del método invocado por `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="b483c-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="b483c-124">Duration</span><span class="sxs-lookup"><span data-stu-id="b483c-124">Duration</span></span>|`xs:long`|<span data-ttu-id="b483c-125">El tiempo, en milisegundos, que tardó `OperationInvoker` en invocar el método.</span><span class="sxs-lookup"><span data-stu-id="b483c-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="b483c-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="b483c-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="b483c-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="b483c-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b483c-128">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="b483c-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b483c-129">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="b483c-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b483c-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b483c-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b483c-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b483c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
