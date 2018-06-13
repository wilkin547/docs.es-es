---
title: '&lt;direcciones base&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 8de962cc70e1399dd1e9459473055651f9aca5fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747491"
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="7f07b-102">&lt;direcciones base&gt;</span><span class="sxs-lookup"><span data-stu-id="7f07b-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="7f07b-103">Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.</span><span class="sxs-lookup"><span data-stu-id="7f07b-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="7f07b-104">Si una dirección base está presente, los puntos de conexión se pueden configurar con direcciones relativas a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="7f07b-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="7f07b-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7f07b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="7f07b-106">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="7f07b-106">\<client></span></span>  
<span data-ttu-id="7f07b-107">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="7f07b-107">\<endpoint></span></span>  
<span data-ttu-id="7f07b-108">\<host ></span><span class="sxs-lookup"><span data-stu-id="7f07b-108">\<host></span></span>  
<span data-ttu-id="7f07b-109">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="7f07b-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f07b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f07b-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="7f07b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="7f07b-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f07b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7f07b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7f07b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7f07b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f07b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="7f07b-114">Attributes</span></span>  
 <span data-ttu-id="7f07b-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7f07b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7f07b-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7f07b-116">Child Elements</span></span>  
  
|<span data-ttu-id="7f07b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f07b-117">Element</span></span>|<span data-ttu-id="7f07b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f07b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f07b-119">\<add></span><span class="sxs-lookup"><span data-stu-id="7f07b-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="7f07b-120">Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="7f07b-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f07b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7f07b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7f07b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f07b-122">Element</span></span>|<span data-ttu-id="7f07b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f07b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f07b-124">\<host ></span><span class="sxs-lookup"><span data-stu-id="7f07b-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="7f07b-125">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="7f07b-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f07b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f07b-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="7f07b-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="7f07b-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
