---
title: 214 - OperationCompleted
ms.date: 03/30/2017
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
ms.openlocfilehash: 6147c70448efb122cb43a2b42a1e9b59980fab29
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278952"
---
# <a name="214---operationcompleted"></a><span data-ttu-id="332ab-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="332ab-102">214 - OperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="332ab-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="332ab-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="332ab-104">ID</span><span class="sxs-lookup"><span data-stu-id="332ab-104">ID</span></span>|<span data-ttu-id="332ab-105">214</span><span class="sxs-lookup"><span data-stu-id="332ab-105">214</span></span>|  
|<span data-ttu-id="332ab-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="332ab-106">Keywords</span></span>|<span data-ttu-id="332ab-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="332ab-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="332ab-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="332ab-108">Level</span></span>|<span data-ttu-id="332ab-109">Información</span><span class="sxs-lookup"><span data-stu-id="332ab-109">Information</span></span>|  
|<span data-ttu-id="332ab-110">Canal</span><span class="sxs-lookup"><span data-stu-id="332ab-110">Channel</span></span>|<span data-ttu-id="332ab-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="332ab-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="332ab-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="332ab-112">Description</span></span>  

 <span data-ttu-id="332ab-113">Este evento se emite cuando `OperationInvoker` predeterminado del modelo de servicio ha finalizado una llamada a un método sin que dicho método haya generado una excepción.</span><span class="sxs-lookup"><span data-stu-id="332ab-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="332ab-114">Message</span><span class="sxs-lookup"><span data-stu-id="332ab-114">Message</span></span>  

 <span data-ttu-id="332ab-115">Un OperationInvoker completó la llamada al método '%1'.</span><span class="sxs-lookup"><span data-stu-id="332ab-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="332ab-116">La duración de la llamada al método fue de '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="332ab-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="332ab-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="332ab-117">Details</span></span>  
  
|<span data-ttu-id="332ab-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="332ab-118">Data Item Name</span></span>|<span data-ttu-id="332ab-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="332ab-119">Data Item Type</span></span>|<span data-ttu-id="332ab-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="332ab-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="332ab-121">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="332ab-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="332ab-122">El nombre de CLR del método invocado por `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="332ab-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="332ab-123">Duration</span><span class="sxs-lookup"><span data-stu-id="332ab-123">Duration</span></span>|`xs:long`|<span data-ttu-id="332ab-124">El tiempo, en milisegundos, que tardó `OperationInvoker` en invocar el método.</span><span class="sxs-lookup"><span data-stu-id="332ab-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="332ab-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="332ab-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="332ab-126">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="332ab-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="332ab-127">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="332ab-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="332ab-128">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="332ab-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="332ab-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="332ab-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="332ab-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="332ab-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
