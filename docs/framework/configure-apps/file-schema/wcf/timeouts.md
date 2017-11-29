---
title: '&lt;tiempos de espera&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 41ebd88f64b001b577342562c9c3010b307aaccc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="22425-102">&lt;tiempos de espera&gt;</span><span class="sxs-lookup"><span data-stu-id="22425-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="22425-103">Representa un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="22425-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="22425-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="22425-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="22425-105">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="22425-105">\<client></span></span>  
<span data-ttu-id="22425-106">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="22425-106">\<endpoint></span></span>  
<span data-ttu-id="22425-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="22425-107">\<host></span></span>  
<span data-ttu-id="22425-108">\<los tiempos de espera ></span><span class="sxs-lookup"><span data-stu-id="22425-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22425-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22425-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22425-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22425-110">Attributes and Elements</span></span>  
 <span data-ttu-id="22425-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22425-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22425-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="22425-112">Attributes</span></span>  
  
|<span data-ttu-id="22425-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="22425-113">Attribute</span></span>|<span data-ttu-id="22425-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="22425-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="22425-115">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se cierre.</span><span class="sxs-lookup"><span data-stu-id="22425-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="22425-116">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se abra.</span><span class="sxs-lookup"><span data-stu-id="22425-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22425-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22425-117">Child Elements</span></span>  
 <span data-ttu-id="22425-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22425-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22425-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22425-119">Parent Elements</span></span>  
  
|<span data-ttu-id="22425-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="22425-120">Element</span></span>|<span data-ttu-id="22425-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="22425-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22425-122">\<host ></span><span class="sxs-lookup"><span data-stu-id="22425-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="22425-123">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="22425-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22425-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="22425-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="22425-125">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="22425-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
