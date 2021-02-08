---
description: 'Más información acerca de: 219-ServiceException'
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: b2ac12d6c5c68517b085b39dd7d0f81c39db9ebd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794330"
---
# <a name="219---serviceexception"></a><span data-ttu-id="78f3b-103">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="78f3b-103">219 - ServiceException</span></span>

## <a name="properties"></a><span data-ttu-id="78f3b-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="78f3b-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78f3b-105">Id.</span><span class="sxs-lookup"><span data-stu-id="78f3b-105">ID</span></span>|<span data-ttu-id="78f3b-106">219</span><span class="sxs-lookup"><span data-stu-id="78f3b-106">219</span></span>|  
|<span data-ttu-id="78f3b-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="78f3b-107">Keywords</span></span>|<span data-ttu-id="78f3b-108">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="78f3b-108">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="78f3b-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="78f3b-109">Level</span></span>|<span data-ttu-id="78f3b-110">Error</span><span class="sxs-lookup"><span data-stu-id="78f3b-110">Error</span></span>|  
|<span data-ttu-id="78f3b-111">Canal</span><span class="sxs-lookup"><span data-stu-id="78f3b-111">Channel</span></span>|<span data-ttu-id="78f3b-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="78f3b-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="78f3b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="78f3b-113">Description</span></span>  

 <span data-ttu-id="78f3b-114">Este evento se emite cuando un servicio WCF encuentra una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="78f3b-114">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="78f3b-115">Esto incluye las excepciones no controladas durante la activación, durante el procesamiento de mensajes y en código de usuario.</span><span class="sxs-lookup"><span data-stu-id="78f3b-115">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="78f3b-116">Message</span><span class="sxs-lookup"><span data-stu-id="78f3b-116">Message</span></span>  

 <span data-ttu-id="78f3b-117">Excepción no controlada del tipo '%2' durante el procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="78f3b-117">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="78f3b-118">ToString de excepción completa: %1.</span><span class="sxs-lookup"><span data-stu-id="78f3b-118">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="78f3b-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="78f3b-119">Details</span></span>  
  
|<span data-ttu-id="78f3b-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="78f3b-120">Data Item Name</span></span>|<span data-ttu-id="78f3b-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="78f3b-121">Data Item Type</span></span>|<span data-ttu-id="78f3b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="78f3b-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="78f3b-123">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="78f3b-123">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="78f3b-124">El resultado de llamar a `ToString`() en la excepción de CLR.</span><span class="sxs-lookup"><span data-stu-id="78f3b-124">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="78f3b-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="78f3b-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="78f3b-126">El nombre completo (FullName) de CLR del tipo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="78f3b-126">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="78f3b-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="78f3b-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="78f3b-128">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="78f3b-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="78f3b-129">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="78f3b-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="78f3b-130">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="78f3b-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="78f3b-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="78f3b-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="78f3b-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="78f3b-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
