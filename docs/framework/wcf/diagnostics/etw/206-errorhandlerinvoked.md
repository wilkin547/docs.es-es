---
description: 'Más información acerca de: 206-ErrorHandlerInvoked'
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: addbcbdea25c7f8e7515b743e98e426476fa0b28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783786"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="7458e-103">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="7458e-103">206 - ErrorHandlerInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="7458e-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7458e-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7458e-105">Id.</span><span class="sxs-lookup"><span data-stu-id="7458e-105">ID</span></span>|<span data-ttu-id="7458e-106">206</span><span class="sxs-lookup"><span data-stu-id="7458e-106">206</span></span>|  
|<span data-ttu-id="7458e-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="7458e-107">Keywords</span></span>|<span data-ttu-id="7458e-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7458e-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7458e-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="7458e-109">Level</span></span>|<span data-ttu-id="7458e-110">Información</span><span class="sxs-lookup"><span data-stu-id="7458e-110">Information</span></span>|  
|<span data-ttu-id="7458e-111">Canal</span><span class="sxs-lookup"><span data-stu-id="7458e-111">Channel</span></span>|<span data-ttu-id="7458e-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="7458e-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7458e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7458e-113">Description</span></span>  

 <span data-ttu-id="7458e-114">Este evento se emite cuando `ErrorHandler` ha tenido la oportunidad de administrar una excepción producida en una operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="7458e-114">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7458e-115">Message</span><span class="sxs-lookup"><span data-stu-id="7458e-115">Message</span></span>  

 <span data-ttu-id="7458e-116">El distribuidor invocó un ErrorHandler del tipo ' %1 ' con una excepción del tipo ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="7458e-116">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="7458e-117">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="7458e-117">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7458e-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="7458e-118">Details</span></span>  
  
|<span data-ttu-id="7458e-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7458e-119">Data Item Name</span></span>|<span data-ttu-id="7458e-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7458e-120">Data Item Type</span></span>|<span data-ttu-id="7458e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7458e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7458e-122">TypeName</span><span class="sxs-lookup"><span data-stu-id="7458e-122">TypeName</span></span>|`xs:string`|<span data-ttu-id="7458e-123">Nombre completo (FullName) de CLR del tipo del `ErrorHandler` invocado.</span><span class="sxs-lookup"><span data-stu-id="7458e-123">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="7458e-124">Controlado</span><span class="sxs-lookup"><span data-stu-id="7458e-124">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="7458e-125">`true` si el controlador de errores administra el error; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7458e-125">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="7458e-126">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="7458e-126">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="7458e-127">El nombre completo (FullName) de CLR de la excepción que se administraba.</span><span class="sxs-lookup"><span data-stu-id="7458e-127">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="7458e-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="7458e-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="7458e-129">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="7458e-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7458e-130">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="7458e-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7458e-131">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="7458e-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7458e-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7458e-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7458e-133">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7458e-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
