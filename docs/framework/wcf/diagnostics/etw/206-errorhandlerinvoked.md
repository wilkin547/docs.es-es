---
title: 206 - ErrorHandlerInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 43acd7ae7bbfc84e1d1ffb1bf4fa49a3dd3f191a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="509af-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="509af-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="509af-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="509af-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="509af-104">Id.</span><span class="sxs-lookup"><span data-stu-id="509af-104">ID</span></span>|<span data-ttu-id="509af-105">206</span><span class="sxs-lookup"><span data-stu-id="509af-105">206</span></span>|  
|<span data-ttu-id="509af-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="509af-106">Keywords</span></span>|<span data-ttu-id="509af-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="509af-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="509af-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="509af-108">Level</span></span>|<span data-ttu-id="509af-109">Información</span><span class="sxs-lookup"><span data-stu-id="509af-109">Information</span></span>|  
|<span data-ttu-id="509af-110">Canal</span><span class="sxs-lookup"><span data-stu-id="509af-110">Channel</span></span>|<span data-ttu-id="509af-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="509af-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="509af-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="509af-112">Description</span></span>  
 <span data-ttu-id="509af-113">Este evento se emite cuando `ErrorHandler` ha tenido la oportunidad de administrar una excepción producida en una operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="509af-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="509af-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="509af-114">Message</span></span>  
 <span data-ttu-id="509af-115">El distribuidor invocó un ErrorHandler del tipo '%1' con una excepción de tipo '%3'.</span><span class="sxs-lookup"><span data-stu-id="509af-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="509af-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="509af-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="509af-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="509af-117">Details</span></span>  
  
|<span data-ttu-id="509af-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="509af-118">Data Item Name</span></span>|<span data-ttu-id="509af-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="509af-119">Data Item Type</span></span>|<span data-ttu-id="509af-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="509af-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="509af-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="509af-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="509af-122">Nombre completo (FullName) de CLR del tipo del `ErrorHandler` invocado.</span><span class="sxs-lookup"><span data-stu-id="509af-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="509af-123">Handled</span><span class="sxs-lookup"><span data-stu-id="509af-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="509af-124">`true` si el controlador de errores administra el error; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="509af-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="509af-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="509af-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="509af-126">El nombre completo (FullName) de CLR de la excepción que se administraba.</span><span class="sxs-lookup"><span data-stu-id="509af-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="509af-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="509af-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="509af-128">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="509af-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="509af-129">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="509af-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="509af-130">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="509af-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="509af-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="509af-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="509af-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="509af-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
