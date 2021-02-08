---
description: 'Más información acerca de: 212-ParameterInspectorBeforeCallInvoked'
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: aa02ff22b533855716c212d312396e6de23ace42
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794408"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="3ed98-103">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="3ed98-103">212 - ParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="3ed98-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3ed98-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ed98-105">Id.</span><span class="sxs-lookup"><span data-stu-id="3ed98-105">ID</span></span>|<span data-ttu-id="3ed98-106">212</span><span class="sxs-lookup"><span data-stu-id="3ed98-106">212</span></span>|  
|<span data-ttu-id="3ed98-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3ed98-107">Keywords</span></span>|<span data-ttu-id="3ed98-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3ed98-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="3ed98-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="3ed98-109">Level</span></span>|<span data-ttu-id="3ed98-110">Información</span><span class="sxs-lookup"><span data-stu-id="3ed98-110">Information</span></span>|  
|<span data-ttu-id="3ed98-111">Canal</span><span class="sxs-lookup"><span data-stu-id="3ed98-111">Channel</span></span>|<span data-ttu-id="3ed98-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="3ed98-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3ed98-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ed98-113">Description</span></span>  

 <span data-ttu-id="3ed98-114">Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeCall` en `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="3ed98-114">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3ed98-115">Message</span><span class="sxs-lookup"><span data-stu-id="3ed98-115">Message</span></span>  

 <span data-ttu-id="3ed98-116">El distribuidor invocó 'BeforeCall' en un ParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="3ed98-116">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3ed98-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="3ed98-117">Details</span></span>  
  
|<span data-ttu-id="3ed98-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3ed98-118">Data Item Name</span></span>|<span data-ttu-id="3ed98-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3ed98-119">Data Item Type</span></span>|<span data-ttu-id="3ed98-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ed98-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3ed98-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="3ed98-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="3ed98-122">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="3ed98-122">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="3ed98-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="3ed98-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="3ed98-124">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="3ed98-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="3ed98-125">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="3ed98-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="3ed98-126">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="3ed98-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="3ed98-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3ed98-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3ed98-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3ed98-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
