---
description: 'Más información acerca de: 202-ClientMessageInspectorBeforeSendInvoked'
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
ms.openlocfilehash: 0267304ba805c8f23109c820c8516a27958c3040
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99645053"
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="203f3-103">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="203f3-103">202 - ClientMessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="203f3-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="203f3-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="203f3-105">Id.</span><span class="sxs-lookup"><span data-stu-id="203f3-105">ID</span></span>|<span data-ttu-id="203f3-106">202</span><span class="sxs-lookup"><span data-stu-id="203f3-106">202</span></span>|  
|<span data-ttu-id="203f3-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="203f3-107">Keywords</span></span>|<span data-ttu-id="203f3-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="203f3-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="203f3-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="203f3-109">Level</span></span>|<span data-ttu-id="203f3-110">Información</span><span class="sxs-lookup"><span data-stu-id="203f3-110">Information</span></span>|  
|<span data-ttu-id="203f3-111">Canal</span><span class="sxs-lookup"><span data-stu-id="203f3-111">Channel</span></span>|<span data-ttu-id="203f3-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="203f3-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="203f3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="203f3-113">Description</span></span>  

 <span data-ttu-id="203f3-114">Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeSendRequest` en un inspector de mensaje de cliente.</span><span class="sxs-lookup"><span data-stu-id="203f3-114">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="203f3-115">Message</span><span class="sxs-lookup"><span data-stu-id="203f3-115">Message</span></span>  

 <span data-ttu-id="203f3-116">El distribuidor invocó 'BeforeSendRequest' en un ClientMessageInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="203f3-116">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="203f3-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="203f3-117">Details</span></span>  
  
|<span data-ttu-id="203f3-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="203f3-118">Data Item Name</span></span>|<span data-ttu-id="203f3-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="203f3-119">Data Item Type</span></span>|<span data-ttu-id="203f3-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="203f3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="203f3-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="203f3-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="203f3-122">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="203f3-122">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="203f3-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="203f3-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="203f3-124">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="203f3-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="203f3-125">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="203f3-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="203f3-126">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="203f3-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="203f3-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="203f3-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="203f3-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="203f3-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
