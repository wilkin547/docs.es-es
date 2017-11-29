---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f896055d958947e54ee77bb812b8d424e6f4f94f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="6a1c1-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="6a1c1-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="6a1c1-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6a1c1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a1c1-104">Id.</span><span class="sxs-lookup"><span data-stu-id="6a1c1-104">ID</span></span>|<span data-ttu-id="6a1c1-105">204</span><span class="sxs-lookup"><span data-stu-id="6a1c1-105">204</span></span>|  
|<span data-ttu-id="6a1c1-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6a1c1-106">Keywords</span></span>|<span data-ttu-id="6a1c1-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6a1c1-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="6a1c1-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="6a1c1-108">Level</span></span>|<span data-ttu-id="6a1c1-109">Información</span><span class="sxs-lookup"><span data-stu-id="6a1c1-109">Information</span></span>|  
|<span data-ttu-id="6a1c1-110">Canal</span><span class="sxs-lookup"><span data-stu-id="6a1c1-110">Channel</span></span>|<span data-ttu-id="6a1c1-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6a1c1-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6a1c1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a1c1-112">Description</span></span>  
 <span data-ttu-id="6a1c1-113">Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeCall` en un inspector de parámetro de cliente.</span><span class="sxs-lookup"><span data-stu-id="6a1c1-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6a1c1-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="6a1c1-114">Message</span></span>  
 <span data-ttu-id="6a1c1-115">El distribuidor invocó 'BeforeCall' en un ClientParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="6a1c1-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6a1c1-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="6a1c1-116">Details</span></span>  
  
|<span data-ttu-id="6a1c1-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6a1c1-117">Data Item Name</span></span>|<span data-ttu-id="6a1c1-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6a1c1-118">Data Item Type</span></span>|<span data-ttu-id="6a1c1-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a1c1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6a1c1-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="6a1c1-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="6a1c1-121">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="6a1c1-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="6a1c1-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="6a1c1-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="6a1c1-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="6a1c1-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="6a1c1-124">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="6a1c1-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="6a1c1-125">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="6a1c1-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="6a1c1-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6a1c1-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6a1c1-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6a1c1-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
