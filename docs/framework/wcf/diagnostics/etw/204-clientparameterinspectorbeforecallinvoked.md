---
description: 'Más información acerca de: 204-ClientParameterInspectorBeforeCallInvoked'
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
ms.openlocfilehash: fa5646da7c48f624dc40f4fcc54a890c0758b4ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99645001"
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="500ac-103">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="500ac-103">204 - ClientParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="500ac-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="500ac-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="500ac-105">Id.</span><span class="sxs-lookup"><span data-stu-id="500ac-105">ID</span></span>|<span data-ttu-id="500ac-106">204</span><span class="sxs-lookup"><span data-stu-id="500ac-106">204</span></span>|  
|<span data-ttu-id="500ac-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="500ac-107">Keywords</span></span>|<span data-ttu-id="500ac-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="500ac-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="500ac-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="500ac-109">Level</span></span>|<span data-ttu-id="500ac-110">Información</span><span class="sxs-lookup"><span data-stu-id="500ac-110">Information</span></span>|  
|<span data-ttu-id="500ac-111">Canal</span><span class="sxs-lookup"><span data-stu-id="500ac-111">Channel</span></span>|<span data-ttu-id="500ac-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="500ac-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="500ac-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="500ac-113">Description</span></span>  

 <span data-ttu-id="500ac-114">Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeCall` en un inspector de parámetro de cliente.</span><span class="sxs-lookup"><span data-stu-id="500ac-114">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="500ac-115">Message</span><span class="sxs-lookup"><span data-stu-id="500ac-115">Message</span></span>  

 <span data-ttu-id="500ac-116">El distribuidor invocó 'BeforeCall' en un ClientParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="500ac-116">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="500ac-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="500ac-117">Details</span></span>  
  
|<span data-ttu-id="500ac-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="500ac-118">Data Item Name</span></span>|<span data-ttu-id="500ac-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="500ac-119">Data Item Type</span></span>|<span data-ttu-id="500ac-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="500ac-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="500ac-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="500ac-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="500ac-122">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="500ac-122">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="500ac-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="500ac-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="500ac-124">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="500ac-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="500ac-125">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="500ac-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="500ac-126">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="500ac-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="500ac-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="500ac-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="500ac-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="500ac-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
