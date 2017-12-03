---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cb6d243177700daa1e653c394e027a6f5428371
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="ff748-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="ff748-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="ff748-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff748-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff748-104">Id.</span><span class="sxs-lookup"><span data-stu-id="ff748-104">ID</span></span>|<span data-ttu-id="ff748-105">201</span><span class="sxs-lookup"><span data-stu-id="ff748-105">201</span></span>|  
|<span data-ttu-id="ff748-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ff748-106">Keywords</span></span>|<span data-ttu-id="ff748-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ff748-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ff748-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ff748-108">Level</span></span>|<span data-ttu-id="ff748-109">Información</span><span class="sxs-lookup"><span data-stu-id="ff748-109">Information</span></span>|  
|<span data-ttu-id="ff748-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ff748-110">Channel</span></span>|<span data-ttu-id="ff748-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ff748-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ff748-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff748-112">Description</span></span>  
 <span data-ttu-id="ff748-113">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterReceiveReply` en un inspector de mensaje de cliente.</span><span class="sxs-lookup"><span data-stu-id="ff748-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ff748-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="ff748-114">Message</span></span>  
 <span data-ttu-id="ff748-115">El distribuidor invocó 'AfterReceiveReply' en un ClientMessageInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="ff748-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ff748-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="ff748-116">Details</span></span>  
  
|<span data-ttu-id="ff748-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ff748-117">Data Item Name</span></span>|<span data-ttu-id="ff748-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ff748-118">Data Item Type</span></span>|<span data-ttu-id="ff748-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff748-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ff748-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="ff748-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="ff748-121">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="ff748-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="ff748-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="ff748-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="ff748-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="ff748-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ff748-124">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="ff748-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ff748-125">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="ff748-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ff748-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ff748-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ff748-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ff748-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
