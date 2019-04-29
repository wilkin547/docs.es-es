---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 819efa2e13c94e2c7a16c24f6ba9c7ef2b87ef8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781828"
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="a01d8-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="a01d8-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="a01d8-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a01d8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a01d8-104">ID</span><span class="sxs-lookup"><span data-stu-id="a01d8-104">ID</span></span>|<span data-ttu-id="a01d8-105">213</span><span class="sxs-lookup"><span data-stu-id="a01d8-105">213</span></span>|  
|<span data-ttu-id="a01d8-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a01d8-106">Keywords</span></span>|<span data-ttu-id="a01d8-107">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="a01d8-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="a01d8-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a01d8-108">Level</span></span>|<span data-ttu-id="a01d8-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="a01d8-109">LogAlways</span></span>|  
|<span data-ttu-id="a01d8-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a01d8-110">Channel</span></span>|<span data-ttu-id="a01d8-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a01d8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a01d8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a01d8-112">Description</span></span>  
 <span data-ttu-id="a01d8-113">Este evento se emite cuando se inicia un host de servicio hospedado en web.</span><span class="sxs-lookup"><span data-stu-id="a01d8-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="a01d8-114">Esto suele ocurrir cuando un mensaje activa el servicio.</span><span class="sxs-lookup"><span data-stu-id="a01d8-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="a01d8-115">También puede pasar si el servicio se configura para iniciarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a01d8-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a01d8-116">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a01d8-116">Message</span></span>  
 <span data-ttu-id="a01d8-117">ServiceHost iniciado: '%1'.</span><span class="sxs-lookup"><span data-stu-id="a01d8-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a01d8-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="a01d8-118">Details</span></span>  
  
|<span data-ttu-id="a01d8-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a01d8-119">Data Item Name</span></span>|<span data-ttu-id="a01d8-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a01d8-120">Data Item Type</span></span>|<span data-ttu-id="a01d8-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="a01d8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a01d8-122">Service Type Name</span><span class="sxs-lookup"><span data-stu-id="a01d8-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="a01d8-123">El nombre completo (FullName) de CLR del tipo de implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="a01d8-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="a01d8-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="a01d8-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="a01d8-125">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="a01d8-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a01d8-126">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="a01d8-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a01d8-127">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="a01d8-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a01d8-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a01d8-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a01d8-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a01d8-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
