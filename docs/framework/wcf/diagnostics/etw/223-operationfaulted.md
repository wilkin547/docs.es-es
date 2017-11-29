---
title: 223 - OperationFaulted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a04ed11db97d02a90e016ee1825b303375a23412
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="223---operationfaulted"></a><span data-ttu-id="b5b93-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="b5b93-102">223 - OperationFaulted</span></span>
## <a name="properties"></a><span data-ttu-id="b5b93-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b5b93-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5b93-104">Id.</span><span class="sxs-lookup"><span data-stu-id="b5b93-104">ID</span></span>|<span data-ttu-id="b5b93-105">223</span><span class="sxs-lookup"><span data-stu-id="b5b93-105">223</span></span>|  
|<span data-ttu-id="b5b93-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b5b93-106">Keywords</span></span>|<span data-ttu-id="b5b93-107">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b5b93-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b5b93-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b5b93-108">Level</span></span>|<span data-ttu-id="b5b93-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="b5b93-109">Warning</span></span>|  
|<span data-ttu-id="b5b93-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b5b93-110">Channel</span></span>|<span data-ttu-id="b5b93-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b5b93-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b5b93-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5b93-112">Description</span></span>  
 <span data-ttu-id="b5b93-113">Este evento se emite cuando `OperationInvoker` predeterminado del modelo de servicio detecta una excepción que deriva de `FaultException` al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="b5b93-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b5b93-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b5b93-114">Message</span></span>  
 <span data-ttu-id="b5b93-115">El método '% 1' produjo una FaultException al invocarse por OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="b5b93-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="b5b93-116">La duración de la llamada al método fue de '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="b5b93-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b5b93-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="b5b93-117">Details</span></span>  
  
|<span data-ttu-id="b5b93-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b5b93-118">Data Item Name</span></span>|<span data-ttu-id="b5b93-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b5b93-119">Data Item Type</span></span>|<span data-ttu-id="b5b93-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5b93-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b5b93-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="b5b93-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="b5b93-122">El nombre de CLR del método invocado por `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="b5b93-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="b5b93-123">Duración</span><span class="sxs-lookup"><span data-stu-id="b5b93-123">Duration</span></span>|`xs:long`|<span data-ttu-id="b5b93-124">El tiempo, en milisegundos, que tardó `OperationInvoker` en invocar el método.</span><span class="sxs-lookup"><span data-stu-id="b5b93-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="b5b93-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="b5b93-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="b5b93-126">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="b5b93-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b5b93-127">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="b5b93-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b5b93-128">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="b5b93-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b5b93-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b5b93-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b5b93-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b5b93-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
