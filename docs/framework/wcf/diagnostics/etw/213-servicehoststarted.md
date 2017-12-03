---
title: 213 - ServiceHostStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc12626263e21f5fd7310157dcdafe327e6d17a8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="78f56-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="78f56-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="78f56-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="78f56-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78f56-104">Id.</span><span class="sxs-lookup"><span data-stu-id="78f56-104">ID</span></span>|<span data-ttu-id="78f56-105">213</span><span class="sxs-lookup"><span data-stu-id="78f56-105">213</span></span>|  
|<span data-ttu-id="78f56-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="78f56-106">Keywords</span></span>|<span data-ttu-id="78f56-107">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="78f56-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="78f56-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="78f56-108">Level</span></span>|<span data-ttu-id="78f56-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="78f56-109">LogAlways</span></span>|  
|<span data-ttu-id="78f56-110">Canal</span><span class="sxs-lookup"><span data-stu-id="78f56-110">Channel</span></span>|<span data-ttu-id="78f56-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="78f56-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="78f56-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="78f56-112">Description</span></span>  
 <span data-ttu-id="78f56-113">Este evento se emite cuando se inicia un host de servicio hospedado en web.</span><span class="sxs-lookup"><span data-stu-id="78f56-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="78f56-114">Esto suele ocurrir cuando un mensaje activa el servicio.</span><span class="sxs-lookup"><span data-stu-id="78f56-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="78f56-115">También puede pasar si el servicio se configura para iniciarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="78f56-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="78f56-116">Mensaje</span><span class="sxs-lookup"><span data-stu-id="78f56-116">Message</span></span>  
 <span data-ttu-id="78f56-117">ServiceHost iniciado: '%1'.</span><span class="sxs-lookup"><span data-stu-id="78f56-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="78f56-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="78f56-118">Details</span></span>  
  
|<span data-ttu-id="78f56-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="78f56-119">Data Item Name</span></span>|<span data-ttu-id="78f56-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="78f56-120">Data Item Type</span></span>|<span data-ttu-id="78f56-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="78f56-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="78f56-122">Service Type Name</span><span class="sxs-lookup"><span data-stu-id="78f56-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="78f56-123">El nombre completo (FullName) de CLR del tipo de implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="78f56-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="78f56-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="78f56-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="78f56-125">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="78f56-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="78f56-126">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="78f56-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="78f56-127">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="78f56-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="78f56-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="78f56-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="78f56-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="78f56-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
