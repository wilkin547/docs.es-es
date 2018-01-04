---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6d737a7334098961cccb73a114be9be5bb71727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="a93e2-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="a93e2-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="a93e2-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a93e2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a93e2-104">Id.</span><span class="sxs-lookup"><span data-stu-id="a93e2-104">ID</span></span>|<span data-ttu-id="a93e2-105">202</span><span class="sxs-lookup"><span data-stu-id="a93e2-105">202</span></span>|  
|<span data-ttu-id="a93e2-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a93e2-106">Keywords</span></span>|<span data-ttu-id="a93e2-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a93e2-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a93e2-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a93e2-108">Level</span></span>|<span data-ttu-id="a93e2-109">Información</span><span class="sxs-lookup"><span data-stu-id="a93e2-109">Information</span></span>|  
|<span data-ttu-id="a93e2-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a93e2-110">Channel</span></span>|<span data-ttu-id="a93e2-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a93e2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a93e2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a93e2-112">Description</span></span>  
 <span data-ttu-id="a93e2-113">Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeSendRequest` en un inspector de mensaje de cliente.</span><span class="sxs-lookup"><span data-stu-id="a93e2-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a93e2-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a93e2-114">Message</span></span>  
 <span data-ttu-id="a93e2-115">El distribuidor invocó 'BeforeSendRequest' en un ClientMessageInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="a93e2-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a93e2-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="a93e2-116">Details</span></span>  
  
|<span data-ttu-id="a93e2-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a93e2-117">Data Item Name</span></span>|<span data-ttu-id="a93e2-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a93e2-118">Data Item Type</span></span>|<span data-ttu-id="a93e2-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a93e2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a93e2-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="a93e2-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="a93e2-121">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="a93e2-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="a93e2-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="a93e2-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="a93e2-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="a93e2-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a93e2-124">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="a93e2-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a93e2-125">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="a93e2-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a93e2-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a93e2-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a93e2-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a93e2-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
