---
title: 219 - ServiceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dd38ab45bceeee577d9e33f699a03a81c09dfc99
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="219---serviceexception"></a><span data-ttu-id="03fce-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="03fce-102">219 - ServiceException</span></span>
## <a name="properties"></a><span data-ttu-id="03fce-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="03fce-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="03fce-104">Id.</span><span class="sxs-lookup"><span data-stu-id="03fce-104">ID</span></span>|<span data-ttu-id="03fce-105">219</span><span class="sxs-lookup"><span data-stu-id="03fce-105">219</span></span>|  
|<span data-ttu-id="03fce-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="03fce-106">Keywords</span></span>|<span data-ttu-id="03fce-107">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="03fce-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="03fce-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="03fce-108">Level</span></span>|<span data-ttu-id="03fce-109">Error</span><span class="sxs-lookup"><span data-stu-id="03fce-109">Error</span></span>|  
|<span data-ttu-id="03fce-110">Canal</span><span class="sxs-lookup"><span data-stu-id="03fce-110">Channel</span></span>|<span data-ttu-id="03fce-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="03fce-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="03fce-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="03fce-112">Description</span></span>  
 <span data-ttu-id="03fce-113">Este evento se emite cuando un servicio WCF encuentra una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="03fce-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="03fce-114">Esto incluye las excepciones no controladas durante la activación, durante el procesamiento de mensajes y en código de usuario.</span><span class="sxs-lookup"><span data-stu-id="03fce-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="03fce-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="03fce-115">Message</span></span>  
 <span data-ttu-id="03fce-116">Excepción no controlada del tipo '%2' durante el procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="03fce-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="03fce-117">ToString de excepción completa: %1.</span><span class="sxs-lookup"><span data-stu-id="03fce-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="03fce-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="03fce-118">Details</span></span>  
  
|<span data-ttu-id="03fce-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="03fce-119">Data Item Name</span></span>|<span data-ttu-id="03fce-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="03fce-120">Data Item Type</span></span>|<span data-ttu-id="03fce-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="03fce-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="03fce-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="03fce-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="03fce-123">El resultado de llamar a `ToString`() en la excepción de CLR.</span><span class="sxs-lookup"><span data-stu-id="03fce-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="03fce-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="03fce-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="03fce-125">El nombre completo (FullName) de CLR del tipo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="03fce-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="03fce-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="03fce-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="03fce-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="03fce-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="03fce-128">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="03fce-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="03fce-129">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="03fce-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="03fce-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="03fce-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="03fce-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="03fce-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
