---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 28c2aca4555d2e4ff498e450deae55ad6a87743c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279043"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="e2f3e-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="e2f3e-102">212 - ParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="e2f3e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e2f3e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2f3e-104">ID</span><span class="sxs-lookup"><span data-stu-id="e2f3e-104">ID</span></span>|<span data-ttu-id="e2f3e-105">212</span><span class="sxs-lookup"><span data-stu-id="e2f3e-105">212</span></span>|  
|<span data-ttu-id="e2f3e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e2f3e-106">Keywords</span></span>|<span data-ttu-id="e2f3e-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e2f3e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e2f3e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="e2f3e-108">Level</span></span>|<span data-ttu-id="e2f3e-109">Información</span><span class="sxs-lookup"><span data-stu-id="e2f3e-109">Information</span></span>|  
|<span data-ttu-id="e2f3e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e2f3e-110">Channel</span></span>|<span data-ttu-id="e2f3e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e2f3e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e2f3e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2f3e-112">Description</span></span>  

 <span data-ttu-id="e2f3e-113">Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeCall` en `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="e2f3e-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e2f3e-114">Message</span><span class="sxs-lookup"><span data-stu-id="e2f3e-114">Message</span></span>  

 <span data-ttu-id="e2f3e-115">El distribuidor invocó 'BeforeCall' en un ParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="e2f3e-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e2f3e-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="e2f3e-116">Details</span></span>  
  
|<span data-ttu-id="e2f3e-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e2f3e-117">Data Item Name</span></span>|<span data-ttu-id="e2f3e-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e2f3e-118">Data Item Type</span></span>|<span data-ttu-id="e2f3e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2f3e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e2f3e-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="e2f3e-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="e2f3e-121">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="e2f3e-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="e2f3e-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="e2f3e-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="e2f3e-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="e2f3e-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e2f3e-124">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="e2f3e-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e2f3e-125">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="e2f3e-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e2f3e-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e2f3e-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e2f3e-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e2f3e-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
