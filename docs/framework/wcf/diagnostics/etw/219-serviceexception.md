---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: 832ced406b6079fad8f4b9bea512a6d390bdcc0f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241946"
---
# <a name="219---serviceexception"></a><span data-ttu-id="8e533-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="8e533-102">219 - ServiceException</span></span>

## <a name="properties"></a><span data-ttu-id="8e533-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8e533-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8e533-104">ID</span><span class="sxs-lookup"><span data-stu-id="8e533-104">ID</span></span>|<span data-ttu-id="8e533-105">219</span><span class="sxs-lookup"><span data-stu-id="8e533-105">219</span></span>|  
|<span data-ttu-id="8e533-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8e533-106">Keywords</span></span>|<span data-ttu-id="8e533-107">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8e533-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="8e533-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="8e533-108">Level</span></span>|<span data-ttu-id="8e533-109">Error</span><span class="sxs-lookup"><span data-stu-id="8e533-109">Error</span></span>|  
|<span data-ttu-id="8e533-110">Canal</span><span class="sxs-lookup"><span data-stu-id="8e533-110">Channel</span></span>|<span data-ttu-id="8e533-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="8e533-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8e533-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e533-112">Description</span></span>  

 <span data-ttu-id="8e533-113">Este evento se emite cuando un servicio WCF encuentra una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="8e533-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="8e533-114">Esto incluye las excepciones no controladas durante la activación, durante el procesamiento de mensajes y en código de usuario.</span><span class="sxs-lookup"><span data-stu-id="8e533-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8e533-115">Message</span><span class="sxs-lookup"><span data-stu-id="8e533-115">Message</span></span>  

 <span data-ttu-id="8e533-116">Excepción no controlada del tipo '%2' durante el procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="8e533-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="8e533-117">ToString de excepción completa: %1.</span><span class="sxs-lookup"><span data-stu-id="8e533-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8e533-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="8e533-118">Details</span></span>  
  
|<span data-ttu-id="8e533-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8e533-119">Data Item Name</span></span>|<span data-ttu-id="8e533-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8e533-120">Data Item Type</span></span>|<span data-ttu-id="8e533-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e533-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8e533-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="8e533-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="8e533-123">El resultado de llamar a `ToString`() en la excepción de CLR.</span><span class="sxs-lookup"><span data-stu-id="8e533-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="8e533-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="8e533-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="8e533-125">El nombre completo (FullName) de CLR del tipo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="8e533-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="8e533-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="8e533-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="8e533-127">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="8e533-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="8e533-128">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="8e533-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="8e533-129">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="8e533-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="8e533-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8e533-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8e533-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8e533-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
