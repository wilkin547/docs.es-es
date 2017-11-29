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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e786691ef3a6ee2a860461562c9de0f627fc907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="499---transferemitted"></a><span data-ttu-id="831d8-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="831d8-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="831d8-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="831d8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="831d8-104">Id.</span><span class="sxs-lookup"><span data-stu-id="831d8-104">ID</span></span>|<span data-ttu-id="831d8-105">499</span><span class="sxs-lookup"><span data-stu-id="831d8-105">499</span></span>|  
|<span data-ttu-id="831d8-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="831d8-106">Keywords</span></span>|<span data-ttu-id="831d8-107">Solución de problemas, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="831d8-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="831d8-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="831d8-108">Level</span></span>|<span data-ttu-id="831d8-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="831d8-109">LogAlways</span></span>|  
|<span data-ttu-id="831d8-110">Canal</span><span class="sxs-lookup"><span data-stu-id="831d8-110">Channel</span></span>|<span data-ttu-id="831d8-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="831d8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="831d8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="831d8-112">Description</span></span>  
 <span data-ttu-id="831d8-113">Se emite este evento cuando tiene lugar el evento de transferencia.</span><span class="sxs-lookup"><span data-stu-id="831d8-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="831d8-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="831d8-114">Message</span></span>  
 <span data-ttu-id="831d8-115">Evento de transferencia emitido.</span><span class="sxs-lookup"><span data-stu-id="831d8-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="831d8-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="831d8-116">Details</span></span>  
  
|<span data-ttu-id="831d8-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="831d8-117">Data Item Name</span></span>|<span data-ttu-id="831d8-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="831d8-118">Data Item Type</span></span>|<span data-ttu-id="831d8-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="831d8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="831d8-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="831d8-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="831d8-121">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="831d8-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="831d8-122">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="831d8-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="831d8-123">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="831d8-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="831d8-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="831d8-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="831d8-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="831d8-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
