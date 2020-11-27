---
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: 310e91320d27dd9817302fc14ef088d180152b73
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263079"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="b4047-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="b4047-102">223 - OperationFaulted</span></span>

## <a name="properties"></a><span data-ttu-id="b4047-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b4047-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4047-104">ID</span><span class="sxs-lookup"><span data-stu-id="b4047-104">ID</span></span>|<span data-ttu-id="b4047-105">223</span><span class="sxs-lookup"><span data-stu-id="b4047-105">223</span></span>|  
|<span data-ttu-id="b4047-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b4047-106">Keywords</span></span>|<span data-ttu-id="b4047-107">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b4047-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b4047-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b4047-108">Level</span></span>|<span data-ttu-id="b4047-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="b4047-109">Warning</span></span>|  
|<span data-ttu-id="b4047-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b4047-110">Channel</span></span>|<span data-ttu-id="b4047-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b4047-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b4047-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4047-112">Description</span></span>  

 <span data-ttu-id="b4047-113">Este evento se emite cuando `OperationInvoker` predeterminado del modelo de servicio detecta una excepción que deriva de `FaultException` al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="b4047-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b4047-114">Message</span><span class="sxs-lookup"><span data-stu-id="b4047-114">Message</span></span>  

 <span data-ttu-id="b4047-115">El método '% 1' produjo una FaultException al invocarse por OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="b4047-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="b4047-116">La duración de la llamada al método fue de '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="b4047-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b4047-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="b4047-117">Details</span></span>  
  
|<span data-ttu-id="b4047-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b4047-118">Data Item Name</span></span>|<span data-ttu-id="b4047-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b4047-119">Data Item Type</span></span>|<span data-ttu-id="b4047-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4047-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b4047-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="b4047-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="b4047-122">El nombre de CLR del método invocado por `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="b4047-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="b4047-123">Duration</span><span class="sxs-lookup"><span data-stu-id="b4047-123">Duration</span></span>|`xs:long`|<span data-ttu-id="b4047-124">El tiempo, en milisegundos, que tardó `OperationInvoker` en invocar el método.</span><span class="sxs-lookup"><span data-stu-id="b4047-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="b4047-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="b4047-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="b4047-126">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="b4047-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b4047-127">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="b4047-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b4047-128">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="b4047-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b4047-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b4047-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b4047-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b4047-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
