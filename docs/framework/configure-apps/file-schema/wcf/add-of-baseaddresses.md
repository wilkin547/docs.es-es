---
title: '&lt;add&gt; de &lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: 3f1b7e8f1f4ab8542270d459ce5020ce4320eea9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="0e655-102">&lt;add&gt; de &lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="0e655-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="0e655-103">Representa un elemento de configuración que especifica las direcciones base usadas por el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="0e655-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="0e655-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0e655-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0e655-105">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="0e655-105">\<client></span></span>  
<span data-ttu-id="0e655-106">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="0e655-106">\<endpoint></span></span>  
<span data-ttu-id="0e655-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="0e655-107">\<host></span></span>  
<span data-ttu-id="0e655-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="0e655-108">\<baseAddresses></span></span>  
<span data-ttu-id="0e655-109">\<baseAddress ></span><span class="sxs-lookup"><span data-stu-id="0e655-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e655-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e655-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />  
```  
  
## <a name="type"></a><span data-ttu-id="0e655-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="0e655-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e655-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0e655-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0e655-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0e655-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e655-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="0e655-114">Attributes</span></span>  
  
|<span data-ttu-id="0e655-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="0e655-115">Attribute</span></span>|<span data-ttu-id="0e655-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e655-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="0e655-117">Cadena que especifica una dirección base usada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="0e655-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e655-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0e655-118">Child Elements</span></span>  
 <span data-ttu-id="0e655-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0e655-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e655-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0e655-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0e655-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e655-121">Element</span></span>|<span data-ttu-id="0e655-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e655-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e655-123">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="0e655-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="0e655-124">Una colección de elementos de `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="0e655-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e655-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e655-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="0e655-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="0e655-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
