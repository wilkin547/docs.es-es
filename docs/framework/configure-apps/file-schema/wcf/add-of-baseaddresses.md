---
title: '&lt;add&gt; de &lt;baseAddresses&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cf417653652c2a0f28fe5c6491a7da9949678140
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="d6f46-102">&lt;add&gt; de &lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="d6f46-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="d6f46-103">Representa un elemento de configuración que especifica las direcciones base usadas por el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="d6f46-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="d6f46-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d6f46-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d6f46-105">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="d6f46-105">\<client></span></span>  
<span data-ttu-id="d6f46-106">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="d6f46-106">\<endpoint></span></span>  
<span data-ttu-id="d6f46-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="d6f46-107">\<host></span></span>  
<span data-ttu-id="d6f46-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="d6f46-108">\<baseAddresses></span></span>  
<span data-ttu-id="d6f46-109">\<baseAddress ></span><span class="sxs-lookup"><span data-stu-id="d6f46-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f46-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6f46-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />  
```  
  
## <a name="type"></a><span data-ttu-id="d6f46-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6f46-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6f46-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d6f46-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d6f46-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d6f46-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6f46-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d6f46-114">Attributes</span></span>  
  
|<span data-ttu-id="d6f46-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="d6f46-115">Attribute</span></span>|<span data-ttu-id="d6f46-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6f46-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="d6f46-117">Cadena que especifica una dirección base usada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="d6f46-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6f46-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d6f46-118">Child Elements</span></span>  
 <span data-ttu-id="d6f46-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d6f46-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6f46-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d6f46-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d6f46-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6f46-121">Element</span></span>|<span data-ttu-id="d6f46-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6f46-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6f46-123">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="d6f46-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="d6f46-124">Una colección de elementos de `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="d6f46-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6f46-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6f46-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="d6f46-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="d6f46-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
