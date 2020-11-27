---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: 7027b6557520a9ccb587f8d383d3598571da5838
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279069"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="703f0-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="703f0-102">211 - ParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="703f0-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="703f0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="703f0-104">ID</span><span class="sxs-lookup"><span data-stu-id="703f0-104">ID</span></span>|<span data-ttu-id="703f0-105">211</span><span class="sxs-lookup"><span data-stu-id="703f0-105">211</span></span>|  
|<span data-ttu-id="703f0-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="703f0-106">Keywords</span></span>|<span data-ttu-id="703f0-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="703f0-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="703f0-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="703f0-108">Level</span></span>|<span data-ttu-id="703f0-109">Información</span><span class="sxs-lookup"><span data-stu-id="703f0-109">Information</span></span>|  
|<span data-ttu-id="703f0-110">Canal</span><span class="sxs-lookup"><span data-stu-id="703f0-110">Channel</span></span>|<span data-ttu-id="703f0-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="703f0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="703f0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="703f0-112">Description</span></span>  

 <span data-ttu-id="703f0-113">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterCall` en `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="703f0-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="703f0-114">Message</span><span class="sxs-lookup"><span data-stu-id="703f0-114">Message</span></span>  

 <span data-ttu-id="703f0-115">El distribuidor invocó 'AfterCall' en un ParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="703f0-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="703f0-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="703f0-116">Details</span></span>  
  
|<span data-ttu-id="703f0-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="703f0-117">Data Item Name</span></span>|<span data-ttu-id="703f0-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="703f0-118">Data Item Type</span></span>|<span data-ttu-id="703f0-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="703f0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="703f0-120">Nombre del tipo</span><span class="sxs-lookup"><span data-stu-id="703f0-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="703f0-121">Nombre completo (FullName) de CLR del tipo del `ParameterInspector` invocado.</span><span class="sxs-lookup"><span data-stu-id="703f0-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="703f0-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="703f0-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="703f0-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="703f0-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="703f0-124">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="703f0-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="703f0-125">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="703f0-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="703f0-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="703f0-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="703f0-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="703f0-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
