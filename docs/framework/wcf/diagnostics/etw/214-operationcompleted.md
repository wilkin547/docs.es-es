---
description: 'Más información acerca de: 214-OperationCompleted'
title: 214 - OperationCompleted
ms.date: 03/30/2017
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
ms.openlocfilehash: aad1ac49667a2ebbf172b5132507584e05d0f03e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794395"
---
# <a name="214---operationcompleted"></a><span data-ttu-id="e1a8b-103">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="e1a8b-103">214 - OperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="e1a8b-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e1a8b-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1a8b-105">Id.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-105">ID</span></span>|<span data-ttu-id="e1a8b-106">214</span><span class="sxs-lookup"><span data-stu-id="e1a8b-106">214</span></span>|  
|<span data-ttu-id="e1a8b-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e1a8b-107">Keywords</span></span>|<span data-ttu-id="e1a8b-108">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e1a8b-108">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e1a8b-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="e1a8b-109">Level</span></span>|<span data-ttu-id="e1a8b-110">Información</span><span class="sxs-lookup"><span data-stu-id="e1a8b-110">Information</span></span>|  
|<span data-ttu-id="e1a8b-111">Canal</span><span class="sxs-lookup"><span data-stu-id="e1a8b-111">Channel</span></span>|<span data-ttu-id="e1a8b-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e1a8b-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e1a8b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1a8b-113">Description</span></span>  

 <span data-ttu-id="e1a8b-114">Este evento se emite cuando `OperationInvoker` predeterminado del modelo de servicio ha finalizado una llamada a un método sin que dicho método haya generado una excepción.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-114">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e1a8b-115">Message</span><span class="sxs-lookup"><span data-stu-id="e1a8b-115">Message</span></span>  

 <span data-ttu-id="e1a8b-116">Un OperationInvoker completó la llamada al método '%1'.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-116">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="e1a8b-117">La duración de la llamada al método fue de '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e1a8b-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="e1a8b-118">Details</span></span>  
  
|<span data-ttu-id="e1a8b-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e1a8b-119">Data Item Name</span></span>|<span data-ttu-id="e1a8b-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e1a8b-120">Data Item Type</span></span>|<span data-ttu-id="e1a8b-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1a8b-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e1a8b-122">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="e1a8b-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="e1a8b-123">El nombre de CLR del método invocado por `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="e1a8b-124">Duration</span><span class="sxs-lookup"><span data-stu-id="e1a8b-124">Duration</span></span>|`xs:long`|<span data-ttu-id="e1a8b-125">El tiempo, en milisegundos, que tardó `OperationInvoker` en invocar el método.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="e1a8b-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="e1a8b-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="e1a8b-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-127">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e1a8b-128">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e1a8b-129">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e1a8b-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e1a8b-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e1a8b-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
