---
title: '&lt;direcciones base&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4bf698b64b528b0ea109223a2d94e6725c8ce6b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="5984b-102">&lt;direcciones base&gt;</span><span class="sxs-lookup"><span data-stu-id="5984b-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="5984b-103">Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.</span><span class="sxs-lookup"><span data-stu-id="5984b-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="5984b-104">Si una dirección base está presente, los puntos de conexión se pueden configurar con direcciones relativas a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="5984b-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="5984b-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5984b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5984b-106">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="5984b-106">\<client></span></span>  
<span data-ttu-id="5984b-107">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="5984b-107">\<endpoint></span></span>  
<span data-ttu-id="5984b-108">\<host ></span><span class="sxs-lookup"><span data-stu-id="5984b-108">\<host></span></span>  
<span data-ttu-id="5984b-109">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="5984b-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5984b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5984b-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="5984b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="5984b-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5984b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5984b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5984b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5984b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5984b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="5984b-114">Attributes</span></span>  
 <span data-ttu-id="5984b-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5984b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5984b-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5984b-116">Child Elements</span></span>  
  
|<span data-ttu-id="5984b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5984b-117">Element</span></span>|<span data-ttu-id="5984b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="5984b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5984b-119">\<add></span><span class="sxs-lookup"><span data-stu-id="5984b-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="5984b-120">Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="5984b-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5984b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5984b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5984b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="5984b-122">Element</span></span>|<span data-ttu-id="5984b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="5984b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5984b-124">\<host ></span><span class="sxs-lookup"><span data-stu-id="5984b-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="5984b-125">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="5984b-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5984b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5984b-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="5984b-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="5984b-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
