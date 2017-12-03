---
title: 499 - TransferEmitted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a0bbe31095a59be4b091de6974ae0173753e240
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="499---transferemitted"></a><span data-ttu-id="9fd76-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="9fd76-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="9fd76-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9fd76-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9fd76-104">Id.</span><span class="sxs-lookup"><span data-stu-id="9fd76-104">ID</span></span>|<span data-ttu-id="9fd76-105">499</span><span class="sxs-lookup"><span data-stu-id="9fd76-105">499</span></span>|  
|<span data-ttu-id="9fd76-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9fd76-106">Keywords</span></span>|<span data-ttu-id="9fd76-107">Solución de problemas, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="9fd76-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="9fd76-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="9fd76-108">Level</span></span>|<span data-ttu-id="9fd76-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="9fd76-109">LogAlways</span></span>|  
|<span data-ttu-id="9fd76-110">Canal</span><span class="sxs-lookup"><span data-stu-id="9fd76-110">Channel</span></span>|<span data-ttu-id="9fd76-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9fd76-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9fd76-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fd76-112">Description</span></span>  
 <span data-ttu-id="9fd76-113">Se emite este evento cuando tiene lugar el evento de transferencia.</span><span class="sxs-lookup"><span data-stu-id="9fd76-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9fd76-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="9fd76-114">Message</span></span>  
 <span data-ttu-id="9fd76-115">Evento de transferencia emitido.</span><span class="sxs-lookup"><span data-stu-id="9fd76-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9fd76-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="9fd76-116">Details</span></span>  
  
|<span data-ttu-id="9fd76-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9fd76-117">Data Item Name</span></span>|<span data-ttu-id="9fd76-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9fd76-118">Data Item Type</span></span>|<span data-ttu-id="9fd76-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fd76-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9fd76-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="9fd76-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="9fd76-121">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="9fd76-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9fd76-122">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="9fd76-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9fd76-123">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="9fd76-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9fd76-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9fd76-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9fd76-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9fd76-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
