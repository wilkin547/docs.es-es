---
title: 209 - MessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8de4338fd9d1d18ab1f689df39b2247a29d2dcf5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="df53a-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="df53a-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="df53a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="df53a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df53a-104">Id.</span><span class="sxs-lookup"><span data-stu-id="df53a-104">ID</span></span>|<span data-ttu-id="df53a-105">209</span><span class="sxs-lookup"><span data-stu-id="df53a-105">209</span></span>|  
|<span data-ttu-id="df53a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="df53a-106">Keywords</span></span>|<span data-ttu-id="df53a-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="df53a-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="df53a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="df53a-108">Level</span></span>|<span data-ttu-id="df53a-109">Información</span><span class="sxs-lookup"><span data-stu-id="df53a-109">Information</span></span>|  
|<span data-ttu-id="df53a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="df53a-110">Channel</span></span>|<span data-ttu-id="df53a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="df53a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="df53a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="df53a-112">Description</span></span>  
 <span data-ttu-id="df53a-113">Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeSend` en un inspector de mensaje.</span><span class="sxs-lookup"><span data-stu-id="df53a-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="df53a-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="df53a-114">Message</span></span>  
 <span data-ttu-id="df53a-115">El distribuidor invocó 'BeforeSendRequest' en un MessageInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="df53a-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="df53a-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="df53a-116">Details</span></span>  
  
|<span data-ttu-id="df53a-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="df53a-117">Data Item Name</span></span>|<span data-ttu-id="df53a-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="df53a-118">Data Item Type</span></span>|<span data-ttu-id="df53a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="df53a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="df53a-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="df53a-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="df53a-121">Nombre completo (FullName) de CLR del tipo del `MessageInspector` invocado.</span><span class="sxs-lookup"><span data-stu-id="df53a-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="df53a-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="df53a-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="df53a-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="df53a-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="df53a-124">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="df53a-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="df53a-125">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="df53a-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="df53a-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="df53a-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="df53a-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="df53a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
