---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cdb89eb9f2a50db20f6da53a2b3f527aef8c0ed1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="57e10-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="57e10-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="57e10-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="57e10-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57e10-104">Id.</span><span class="sxs-lookup"><span data-stu-id="57e10-104">ID</span></span>|<span data-ttu-id="57e10-105">208</span><span class="sxs-lookup"><span data-stu-id="57e10-105">208</span></span>|  
|<span data-ttu-id="57e10-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="57e10-106">Keywords</span></span>|<span data-ttu-id="57e10-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="57e10-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="57e10-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="57e10-108">Level</span></span>|<span data-ttu-id="57e10-109">Información</span><span class="sxs-lookup"><span data-stu-id="57e10-109">Information</span></span>|  
|<span data-ttu-id="57e10-110">Canal</span><span class="sxs-lookup"><span data-stu-id="57e10-110">Channel</span></span>|<span data-ttu-id="57e10-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="57e10-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="57e10-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="57e10-112">Description</span></span>  
 <span data-ttu-id="57e10-113">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterReceive` en un inspector de mensaje.</span><span class="sxs-lookup"><span data-stu-id="57e10-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="57e10-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="57e10-114">Message</span></span>  
 <span data-ttu-id="57e10-115">El distribuidor invocó 'AfterReceiveReply' en un MessageInspector del tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="57e10-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="57e10-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="57e10-116">Details</span></span>  
  
|<span data-ttu-id="57e10-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="57e10-117">Data Item Name</span></span>|<span data-ttu-id="57e10-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="57e10-118">Data Item Type</span></span>|<span data-ttu-id="57e10-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="57e10-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="57e10-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="57e10-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="57e10-121">Nombre completo (FullName) de CLR del tipo del `MessageInspector` invocado.</span><span class="sxs-lookup"><span data-stu-id="57e10-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="57e10-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="57e10-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="57e10-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="57e10-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="57e10-124">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="57e10-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="57e10-125">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="57e10-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="57e10-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="57e10-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="57e10-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="57e10-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
