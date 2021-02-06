---
description: 'Más información acerca de: 203-ClientParameterInspectorAfterCallInvoked'
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
ms.openlocfilehash: bacdc2a74fc2cef6d7e473fa58c0cbbcffffcf16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99645027"
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="b0cfe-103">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="b0cfe-103">203 - ClientParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="b0cfe-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b0cfe-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b0cfe-105">Id.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-105">ID</span></span>|<span data-ttu-id="b0cfe-106">203</span><span class="sxs-lookup"><span data-stu-id="b0cfe-106">203</span></span>|  
|<span data-ttu-id="b0cfe-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b0cfe-107">Keywords</span></span>|<span data-ttu-id="b0cfe-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b0cfe-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b0cfe-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0cfe-109">Level</span></span>|<span data-ttu-id="b0cfe-110">Información</span><span class="sxs-lookup"><span data-stu-id="b0cfe-110">Information</span></span>|  
|<span data-ttu-id="b0cfe-111">Canal</span><span class="sxs-lookup"><span data-stu-id="b0cfe-111">Channel</span></span>|<span data-ttu-id="b0cfe-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b0cfe-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b0cfe-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0cfe-113">Description</span></span>  

 <span data-ttu-id="b0cfe-114">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterCall` en un inspector de parámetro de cliente.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-114">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b0cfe-115">Message</span><span class="sxs-lookup"><span data-stu-id="b0cfe-115">Message</span></span>  

 <span data-ttu-id="b0cfe-116">El distribuidor invocó 'AfterCall' en ClientParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-116">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b0cfe-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="b0cfe-117">Details</span></span>  
  
|<span data-ttu-id="b0cfe-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b0cfe-118">Data Item Name</span></span>|<span data-ttu-id="b0cfe-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b0cfe-119">Data Item Type</span></span>|<span data-ttu-id="b0cfe-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0cfe-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b0cfe-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="b0cfe-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="b0cfe-122">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-122">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="b0cfe-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="b0cfe-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="b0cfe-124">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b0cfe-125">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b0cfe-126">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b0cfe-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b0cfe-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b0cfe-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
