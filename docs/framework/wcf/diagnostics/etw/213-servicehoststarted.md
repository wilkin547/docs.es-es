---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 819efa2e13c94e2c7a16c24f6ba9c7ef2b87ef8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458479"
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="69d7e-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="69d7e-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="69d7e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="69d7e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="69d7e-104">Id.</span><span class="sxs-lookup"><span data-stu-id="69d7e-104">ID</span></span>|<span data-ttu-id="69d7e-105">213</span><span class="sxs-lookup"><span data-stu-id="69d7e-105">213</span></span>|  
|<span data-ttu-id="69d7e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="69d7e-106">Keywords</span></span>|<span data-ttu-id="69d7e-107">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="69d7e-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="69d7e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="69d7e-108">Level</span></span>|<span data-ttu-id="69d7e-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="69d7e-109">LogAlways</span></span>|  
|<span data-ttu-id="69d7e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="69d7e-110">Channel</span></span>|<span data-ttu-id="69d7e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="69d7e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="69d7e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="69d7e-112">Description</span></span>  
 <span data-ttu-id="69d7e-113">Este evento se emite cuando se inicia un host de servicio hospedado en web.</span><span class="sxs-lookup"><span data-stu-id="69d7e-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="69d7e-114">Esto suele ocurrir cuando un mensaje activa el servicio.</span><span class="sxs-lookup"><span data-stu-id="69d7e-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="69d7e-115">También puede pasar si el servicio se configura para iniciarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="69d7e-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="69d7e-116">Mensaje</span><span class="sxs-lookup"><span data-stu-id="69d7e-116">Message</span></span>  
 <span data-ttu-id="69d7e-117">ServiceHost iniciado: '%1'.</span><span class="sxs-lookup"><span data-stu-id="69d7e-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="69d7e-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="69d7e-118">Details</span></span>  
  
|<span data-ttu-id="69d7e-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="69d7e-119">Data Item Name</span></span>|<span data-ttu-id="69d7e-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="69d7e-120">Data Item Type</span></span>|<span data-ttu-id="69d7e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="69d7e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="69d7e-122">Service Type Name</span><span class="sxs-lookup"><span data-stu-id="69d7e-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="69d7e-123">El nombre completo (FullName) de CLR del tipo de implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="69d7e-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="69d7e-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="69d7e-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="69d7e-125">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="69d7e-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="69d7e-126">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="69d7e-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="69d7e-127">Ejemplo: ' predeterminado sitio Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="69d7e-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="69d7e-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="69d7e-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="69d7e-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="69d7e-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
