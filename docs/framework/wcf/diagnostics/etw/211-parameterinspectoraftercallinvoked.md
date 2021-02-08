---
description: 'Más información acerca de: 211-ParameterInspectorAfterCallInvoked'
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: 6168528fb001b5669e80595c8327dc57651e815e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794434"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="16cfe-103">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="16cfe-103">211 - ParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="16cfe-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="16cfe-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="16cfe-105">Id.</span><span class="sxs-lookup"><span data-stu-id="16cfe-105">ID</span></span>|<span data-ttu-id="16cfe-106">211</span><span class="sxs-lookup"><span data-stu-id="16cfe-106">211</span></span>|  
|<span data-ttu-id="16cfe-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16cfe-107">Keywords</span></span>|<span data-ttu-id="16cfe-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="16cfe-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="16cfe-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="16cfe-109">Level</span></span>|<span data-ttu-id="16cfe-110">Información</span><span class="sxs-lookup"><span data-stu-id="16cfe-110">Information</span></span>|  
|<span data-ttu-id="16cfe-111">Canal</span><span class="sxs-lookup"><span data-stu-id="16cfe-111">Channel</span></span>|<span data-ttu-id="16cfe-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="16cfe-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="16cfe-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="16cfe-113">Description</span></span>  

 <span data-ttu-id="16cfe-114">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterCall` en `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="16cfe-114">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="16cfe-115">Message</span><span class="sxs-lookup"><span data-stu-id="16cfe-115">Message</span></span>  

 <span data-ttu-id="16cfe-116">El distribuidor invocó 'AfterCall' en un ParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="16cfe-116">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="16cfe-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="16cfe-117">Details</span></span>  
  
|<span data-ttu-id="16cfe-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="16cfe-118">Data Item Name</span></span>|<span data-ttu-id="16cfe-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="16cfe-119">Data Item Type</span></span>|<span data-ttu-id="16cfe-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="16cfe-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="16cfe-121">Nombre del tipo</span><span class="sxs-lookup"><span data-stu-id="16cfe-121">Type Name</span></span>|`xs:string`|<span data-ttu-id="16cfe-122">Nombre completo (FullName) de CLR del tipo del `ParameterInspector` invocado.</span><span class="sxs-lookup"><span data-stu-id="16cfe-122">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="16cfe-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="16cfe-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="16cfe-124">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="16cfe-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="16cfe-125">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="16cfe-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="16cfe-126">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="16cfe-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="16cfe-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="16cfe-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="16cfe-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="16cfe-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
