---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 99415733624752217d32f6f026a419b2b32bfa7b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244618"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="ea113-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="ea113-102">206 - ErrorHandlerInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="ea113-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ea113-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea113-104">ID</span><span class="sxs-lookup"><span data-stu-id="ea113-104">ID</span></span>|<span data-ttu-id="ea113-105">206</span><span class="sxs-lookup"><span data-stu-id="ea113-105">206</span></span>|  
|<span data-ttu-id="ea113-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ea113-106">Keywords</span></span>|<span data-ttu-id="ea113-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ea113-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ea113-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ea113-108">Level</span></span>|<span data-ttu-id="ea113-109">Información</span><span class="sxs-lookup"><span data-stu-id="ea113-109">Information</span></span>|  
|<span data-ttu-id="ea113-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ea113-110">Channel</span></span>|<span data-ttu-id="ea113-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ea113-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ea113-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea113-112">Description</span></span>  

 <span data-ttu-id="ea113-113">Este evento se emite cuando `ErrorHandler` ha tenido la oportunidad de administrar una excepción producida en una operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="ea113-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ea113-114">Message</span><span class="sxs-lookup"><span data-stu-id="ea113-114">Message</span></span>  

 <span data-ttu-id="ea113-115">El distribuidor invocó un ErrorHandler del tipo ' %1 ' con una excepción del tipo ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="ea113-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="ea113-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="ea113-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ea113-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="ea113-117">Details</span></span>  
  
|<span data-ttu-id="ea113-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ea113-118">Data Item Name</span></span>|<span data-ttu-id="ea113-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ea113-119">Data Item Type</span></span>|<span data-ttu-id="ea113-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea113-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ea113-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="ea113-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="ea113-122">Nombre completo (FullName) de CLR del tipo del `ErrorHandler` invocado.</span><span class="sxs-lookup"><span data-stu-id="ea113-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="ea113-123">Controlado</span><span class="sxs-lookup"><span data-stu-id="ea113-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="ea113-124">`true` si el controlador de errores administra el error; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ea113-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="ea113-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="ea113-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="ea113-126">El nombre completo (FullName) de CLR de la excepción que se administraba.</span><span class="sxs-lookup"><span data-stu-id="ea113-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="ea113-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="ea113-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="ea113-128">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="ea113-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ea113-129">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="ea113-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ea113-130">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="ea113-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ea113-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ea113-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ea113-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ea113-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
