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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69a049e1daacce901685050ab9fbe99a9c4d3428
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="3a3f1-102">&lt;direcciones base&gt;</span><span class="sxs-lookup"><span data-stu-id="3a3f1-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="3a3f1-103">Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.</span><span class="sxs-lookup"><span data-stu-id="3a3f1-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="3a3f1-104">Si una dirección base está presente, los puntos de conexión se pueden configurar con direcciones relativas a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="3a3f1-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="3a3f1-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3a3f1-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3a3f1-106">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="3a3f1-106">\<client></span></span>  
<span data-ttu-id="3a3f1-107">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="3a3f1-107">\<endpoint></span></span>  
<span data-ttu-id="3a3f1-108">\<host ></span><span class="sxs-lookup"><span data-stu-id="3a3f1-108">\<host></span></span>  
<span data-ttu-id="3a3f1-109">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="3a3f1-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a3f1-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a3f1-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="3a3f1-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="3a3f1-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a3f1-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3a3f1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3a3f1-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3a3f1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a3f1-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="3a3f1-114">Attributes</span></span>  
 <span data-ttu-id="3a3f1-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3a3f1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3a3f1-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3a3f1-116">Child Elements</span></span>  
  
|<span data-ttu-id="3a3f1-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a3f1-117">Element</span></span>|<span data-ttu-id="3a3f1-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a3f1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a3f1-119">\<add></span><span class="sxs-lookup"><span data-stu-id="3a3f1-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="3a3f1-120">Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="3a3f1-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a3f1-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3a3f1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3a3f1-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a3f1-122">Element</span></span>|<span data-ttu-id="3a3f1-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a3f1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a3f1-124">\<host ></span><span class="sxs-lookup"><span data-stu-id="3a3f1-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="3a3f1-125">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="3a3f1-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a3f1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a3f1-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="3a3f1-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="3a3f1-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
