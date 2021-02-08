---
description: 'Más información acerca de: 213-ServiceHostStarted'
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 5e2b5b7c633ef053c449ad62c4f8fee40798a386
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794421"
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="605b2-103">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="605b2-103">213 - ServiceHostStarted</span></span>

## <a name="properties"></a><span data-ttu-id="605b2-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="605b2-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="605b2-105">Id.</span><span class="sxs-lookup"><span data-stu-id="605b2-105">ID</span></span>|<span data-ttu-id="605b2-106">213</span><span class="sxs-lookup"><span data-stu-id="605b2-106">213</span></span>|  
|<span data-ttu-id="605b2-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="605b2-107">Keywords</span></span>|<span data-ttu-id="605b2-108">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="605b2-108">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="605b2-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="605b2-109">Level</span></span>|<span data-ttu-id="605b2-110">LogAlways</span><span class="sxs-lookup"><span data-stu-id="605b2-110">LogAlways</span></span>|  
|<span data-ttu-id="605b2-111">Canal</span><span class="sxs-lookup"><span data-stu-id="605b2-111">Channel</span></span>|<span data-ttu-id="605b2-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="605b2-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="605b2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="605b2-113">Description</span></span>  

 <span data-ttu-id="605b2-114">Este evento se emite cuando se inicia un host de servicio hospedado en web.</span><span class="sxs-lookup"><span data-stu-id="605b2-114">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="605b2-115">Esto suele ocurrir cuando un mensaje activa el servicio.</span><span class="sxs-lookup"><span data-stu-id="605b2-115">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="605b2-116">También puede pasar si el servicio se configura para iniciarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="605b2-116">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="605b2-117">Message</span><span class="sxs-lookup"><span data-stu-id="605b2-117">Message</span></span>  

 <span data-ttu-id="605b2-118">ServiceHost iniciado: '%1'.</span><span class="sxs-lookup"><span data-stu-id="605b2-118">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="605b2-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="605b2-119">Details</span></span>  
  
|<span data-ttu-id="605b2-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="605b2-120">Data Item Name</span></span>|<span data-ttu-id="605b2-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="605b2-121">Data Item Type</span></span>|<span data-ttu-id="605b2-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="605b2-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="605b2-123">Service Type Name</span><span class="sxs-lookup"><span data-stu-id="605b2-123">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="605b2-124">El nombre completo (FullName) de CLR del tipo de implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="605b2-124">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="605b2-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="605b2-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="605b2-126">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="605b2-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="605b2-127">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="605b2-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="605b2-128">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="605b2-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="605b2-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="605b2-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="605b2-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="605b2-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
