---
description: 'Más información acerca de: 303-UserDefinedInformationEventOccured'
title: 303 - UserDefinedInformationEventOccured
ms.date: 03/30/2017
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
ms.openlocfilehash: 51c4acd5d10a2d563dd7fbcebf90b75c64ff20ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794239"
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="9b899-103">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="9b899-103">303 - UserDefinedInformationEventOccured</span></span>

## <a name="properties"></a><span data-ttu-id="9b899-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9b899-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b899-105">Id.</span><span class="sxs-lookup"><span data-stu-id="9b899-105">ID</span></span>|<span data-ttu-id="9b899-106">303</span><span class="sxs-lookup"><span data-stu-id="9b899-106">303</span></span>|  
|<span data-ttu-id="9b899-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9b899-107">Keywords</span></span>|<span data-ttu-id="9b899-108">Solución de problemas, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="9b899-108">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="9b899-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="9b899-109">Level</span></span>|<span data-ttu-id="9b899-110">Información</span><span class="sxs-lookup"><span data-stu-id="9b899-110">Information</span></span>|  
|<span data-ttu-id="9b899-111">Canal</span><span class="sxs-lookup"><span data-stu-id="9b899-111">Channel</span></span>|<span data-ttu-id="9b899-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9b899-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9b899-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b899-113">Description</span></span>  

 <span data-ttu-id="9b899-114">Este evento se emite desde el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="9b899-114">This event is emitted from user code.</span></span> <span data-ttu-id="9b899-115">Los desarrolladores pueden emitir este evento cuando se produce un evento informativo definido por el usuario en su servicio.</span><span class="sxs-lookup"><span data-stu-id="9b899-115">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="9b899-116">Esto se puede llevar a cabo mediante las API de <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="9b899-116">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="9b899-117">Además, hay un ejemplo de WCF que ajusta esa API y muestra cómo emitir este evento correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b899-117">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9b899-118">Message</span><span class="sxs-lookup"><span data-stu-id="9b899-118">Message</span></span>  

 <span data-ttu-id="9b899-119">Nombre: '%1', referencia: '%2', carga:%3</span><span class="sxs-lookup"><span data-stu-id="9b899-119">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="9b899-120">Detalles</span><span class="sxs-lookup"><span data-stu-id="9b899-120">Details</span></span>  
  
|<span data-ttu-id="9b899-121">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9b899-121">Data Item Name</span></span>|<span data-ttu-id="9b899-122">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9b899-122">Data Item Type</span></span>|<span data-ttu-id="9b899-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b899-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9b899-124">Nombre</span><span class="sxs-lookup"><span data-stu-id="9b899-124">Name</span></span>|`xs:string`|<span data-ttu-id="9b899-125">El nombre del evento definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9b899-125">The user-defined name of the event</span></span>|  
|<span data-ttu-id="9b899-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="9b899-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="9b899-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="9b899-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9b899-128">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="9b899-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9b899-129">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="9b899-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9b899-130">Carga</span><span class="sxs-lookup"><span data-stu-id="9b899-130">Payload</span></span>|`xs:string`|<span data-ttu-id="9b899-131">La carga del evento definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9b899-131">The user-defined payload of the event.</span></span>|
