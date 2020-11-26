---
title: 302 - UserDefinedWarningOccurred
ms.date: 03/30/2017
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
ms.openlocfilehash: b942b2e9716713371b8679fc9df9b9634dfc7283
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243448"
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="774eb-102">302 - UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="774eb-102">302 - UserDefinedWarningOccurred</span></span>

## <a name="properties"></a><span data-ttu-id="774eb-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="774eb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="774eb-104">ID</span><span class="sxs-lookup"><span data-stu-id="774eb-104">ID</span></span>|<span data-ttu-id="774eb-105">302</span><span class="sxs-lookup"><span data-stu-id="774eb-105">302</span></span>|  
|<span data-ttu-id="774eb-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="774eb-106">Keywords</span></span>|<span data-ttu-id="774eb-107">Solución de problemas, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="774eb-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="774eb-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="774eb-108">Level</span></span>|<span data-ttu-id="774eb-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="774eb-109">Warning</span></span>|  
|<span data-ttu-id="774eb-110">Canal</span><span class="sxs-lookup"><span data-stu-id="774eb-110">Channel</span></span>|<span data-ttu-id="774eb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="774eb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="774eb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="774eb-112">Description</span></span>  

 <span data-ttu-id="774eb-113">Este evento se emite desde el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="774eb-113">This event is emitted from user code.</span></span> <span data-ttu-id="774eb-114">Los desarrolladores pueden emitir este evento cuando se produce un evento de advertencia definido por el usuario en su servicio.</span><span class="sxs-lookup"><span data-stu-id="774eb-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="774eb-115">Esto se puede llevar a cabo mediante las API de <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="774eb-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="774eb-116">Además, hay un ejemplo de WCF que ajusta esa API y muestra cómo emitir este evento correctamente.</span><span class="sxs-lookup"><span data-stu-id="774eb-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="774eb-117">Message</span><span class="sxs-lookup"><span data-stu-id="774eb-117">Message</span></span>  

 <span data-ttu-id="774eb-118">Nombre: '%1', referencia: '%2', carga:%3</span><span class="sxs-lookup"><span data-stu-id="774eb-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="774eb-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="774eb-119">Details</span></span>  
  
|<span data-ttu-id="774eb-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="774eb-120">Data Item Name</span></span>|<span data-ttu-id="774eb-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="774eb-121">Data Item Type</span></span>|<span data-ttu-id="774eb-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="774eb-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="774eb-123">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="774eb-123">Name</span></span>|`xs:string`|<span data-ttu-id="774eb-124">El nombre del evento definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="774eb-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="774eb-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="774eb-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="774eb-126">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="774eb-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="774eb-127">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="774eb-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="774eb-128">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="774eb-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="774eb-129">Carga</span><span class="sxs-lookup"><span data-stu-id="774eb-129">Payload</span></span>|`xs:string`|<span data-ttu-id="774eb-130">La carga del evento definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="774eb-130">The user-defined payload of the event.</span></span>|
