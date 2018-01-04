---
title: 303 - UserDefinedInformationEventOccured
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bd4d94d457793eb036f037cc6dc22bff6d26ee2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="d1bfb-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="d1bfb-102">303 - UserDefinedInformationEventOccured</span></span>
## <a name="properties"></a><span data-ttu-id="d1bfb-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d1bfb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1bfb-104">Id.</span><span class="sxs-lookup"><span data-stu-id="d1bfb-104">ID</span></span>|<span data-ttu-id="d1bfb-105">303</span><span class="sxs-lookup"><span data-stu-id="d1bfb-105">303</span></span>|  
|<span data-ttu-id="d1bfb-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d1bfb-106">Keywords</span></span>|<span data-ttu-id="d1bfb-107">Solución de problemas, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="d1bfb-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="d1bfb-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d1bfb-108">Level</span></span>|<span data-ttu-id="d1bfb-109">Información</span><span class="sxs-lookup"><span data-stu-id="d1bfb-109">Information</span></span>|  
|<span data-ttu-id="d1bfb-110">Canal</span><span class="sxs-lookup"><span data-stu-id="d1bfb-110">Channel</span></span>|<span data-ttu-id="d1bfb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d1bfb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d1bfb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1bfb-112">Description</span></span>  
 <span data-ttu-id="d1bfb-113">Este evento se emite desde el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="d1bfb-113">This event is emitted from user code.</span></span> <span data-ttu-id="d1bfb-114">Los desarrolladores pueden emitir este evento cuando se produce un evento informativo definido por el usuario en su servicio.</span><span class="sxs-lookup"><span data-stu-id="d1bfb-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="d1bfb-115">Esto se puede llevar a cabo mediante las API de <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="d1bfb-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="d1bfb-116">Además, hay un ejemplo de WCF que ajusta esa API y muestra cómo emitir este evento correctamente.</span><span class="sxs-lookup"><span data-stu-id="d1bfb-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d1bfb-117">Mensaje</span><span class="sxs-lookup"><span data-stu-id="d1bfb-117">Message</span></span>  
 <span data-ttu-id="d1bfb-118">Nombre: '%1', referencia: '%2', carga:%3</span><span class="sxs-lookup"><span data-stu-id="d1bfb-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="d1bfb-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="d1bfb-119">Details</span></span>  
  
|<span data-ttu-id="d1bfb-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d1bfb-120">Data Item Name</span></span>|<span data-ttu-id="d1bfb-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d1bfb-121">Data Item Type</span></span>|<span data-ttu-id="d1bfb-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1bfb-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d1bfb-123">nombre</span><span class="sxs-lookup"><span data-stu-id="d1bfb-123">Name</span></span>|`xs:string`|<span data-ttu-id="d1bfb-124">El nombre del evento definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d1bfb-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="d1bfb-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="d1bfb-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="d1bfb-126">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="d1bfb-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d1bfb-127">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="d1bfb-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d1bfb-128">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="d1bfb-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d1bfb-129">Payload</span><span class="sxs-lookup"><span data-stu-id="d1bfb-129">Payload</span></span>|`xs:string`|<span data-ttu-id="d1bfb-130">La carga del evento definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d1bfb-130">The user-defined payload of the event.</span></span>|
