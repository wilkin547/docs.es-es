---
title: '&lt;Servicios de&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca55770da8da0fe91a12aeb5fa72e61d6dcd67ae
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicesgt"></a><span data-ttu-id="65671-102">&lt;Servicios de&gt;</span><span class="sxs-lookup"><span data-stu-id="65671-102">&lt;services&gt;</span></span>
<span data-ttu-id="65671-103">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="65671-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="65671-104">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="65671-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="65671-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="65671-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65671-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65671-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65671-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="65671-107">Attributes and Elements</span></span>  
 <span data-ttu-id="65671-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="65671-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65671-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="65671-109">Attributes</span></span>  
 <span data-ttu-id="65671-110">Ninguna</span><span class="sxs-lookup"><span data-stu-id="65671-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="65671-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="65671-111">Child Elements</span></span>  
  
|<span data-ttu-id="65671-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="65671-112">Element</span></span>|<span data-ttu-id="65671-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="65671-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65671-114">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="65671-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="65671-115">Defina el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="65671-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65671-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="65671-116">Parent Elements</span></span>  
  
|<span data-ttu-id="65671-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="65671-117">Element</span></span>|<span data-ttu-id="65671-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="65671-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65671-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="65671-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="65671-120">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="65671-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65671-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="65671-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
