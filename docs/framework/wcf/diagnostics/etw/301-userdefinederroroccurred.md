---
title: 301 - UserDefinedErrorOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: df75fdfa68e11a4a017dffa54e1bb4d628940968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="301---userdefinederroroccurred"></a><span data-ttu-id="ade45-102">301 - UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="ade45-102">301 - UserDefinedErrorOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="ade45-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ade45-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ade45-104">Id.</span><span class="sxs-lookup"><span data-stu-id="ade45-104">ID</span></span>|<span data-ttu-id="ade45-105">301</span><span class="sxs-lookup"><span data-stu-id="ade45-105">301</span></span>|  
|<span data-ttu-id="ade45-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ade45-106">Keywords</span></span>|<span data-ttu-id="ade45-107">Solución de problemas, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="ade45-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="ade45-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ade45-108">Level</span></span>|<span data-ttu-id="ade45-109">Error</span><span class="sxs-lookup"><span data-stu-id="ade45-109">Error</span></span>|  
|<span data-ttu-id="ade45-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ade45-110">Channel</span></span>|<span data-ttu-id="ade45-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ade45-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ade45-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ade45-112">Description</span></span>  
 <span data-ttu-id="ade45-113">Este evento se emite desde el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="ade45-113">This event is emitted from user code.</span></span> <span data-ttu-id="ade45-114">Los desarrolladores pueden emitir este evento cuando se produce un error definido por el usuario en su servicio.</span><span class="sxs-lookup"><span data-stu-id="ade45-114">Developers can emit this event when a custom-defined error occurs in their service.</span></span> <span data-ttu-id="ade45-115">Esto se puede llevar a cabo mediante las API de <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="ade45-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="ade45-116">Además, hay un ejemplo de WCF que ajusta esa API y muestra cómo emitir este evento correctamente.</span><span class="sxs-lookup"><span data-stu-id="ade45-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ade45-117">Mensaje</span><span class="sxs-lookup"><span data-stu-id="ade45-117">Message</span></span>  
 <span data-ttu-id="ade45-118">Nombre: '%1', referencia: '%2', carga:%3</span><span class="sxs-lookup"><span data-stu-id="ade45-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="ade45-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="ade45-119">Details</span></span>  
  
|<span data-ttu-id="ade45-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ade45-120">Data Item Name</span></span>|<span data-ttu-id="ade45-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ade45-121">Data Item Type</span></span>|<span data-ttu-id="ade45-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="ade45-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ade45-123">Name</span><span class="sxs-lookup"><span data-stu-id="ade45-123">Name</span></span>|`xs:string`|<span data-ttu-id="ade45-124">El nombre del evento definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ade45-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="ade45-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="ade45-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="ade45-126">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="ade45-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ade45-127">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="ade45-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ade45-128">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="ade45-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ade45-129">Payload</span><span class="sxs-lookup"><span data-stu-id="ade45-129">Payload</span></span>|`xs:string`|<span data-ttu-id="ade45-130">La carga del evento definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ade45-130">The user-defined payload of the event.</span></span>|
