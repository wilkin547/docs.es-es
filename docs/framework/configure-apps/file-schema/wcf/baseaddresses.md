---
title: '&lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 34d400e74b24e9eb4140d1b43597b0217b23d80c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730131"
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="9c568-102">&lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="9c568-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="9c568-103">Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.</span><span class="sxs-lookup"><span data-stu-id="9c568-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="9c568-104">Si una dirección base está presente, los puntos de conexión se pueden configurar con direcciones relativas a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="9c568-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="9c568-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9c568-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="9c568-106">\<client></span><span class="sxs-lookup"><span data-stu-id="9c568-106">\<client></span></span>  
<span data-ttu-id="9c568-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="9c568-107">\<endpoint></span></span>  
<span data-ttu-id="9c568-108">\<host ></span><span class="sxs-lookup"><span data-stu-id="9c568-108">\<host></span></span>  
<span data-ttu-id="9c568-109">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="9c568-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c568-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c568-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="9c568-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="9c568-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c568-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9c568-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9c568-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9c568-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c568-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="9c568-114">Attributes</span></span>  
 <span data-ttu-id="9c568-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9c568-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9c568-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9c568-116">Child Elements</span></span>  
  
|<span data-ttu-id="9c568-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c568-117">Element</span></span>|<span data-ttu-id="9c568-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c568-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c568-119">\<add></span><span class="sxs-lookup"><span data-stu-id="9c568-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="9c568-120">Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="9c568-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c568-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9c568-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9c568-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c568-122">Element</span></span>|<span data-ttu-id="9c568-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c568-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c568-124">\<host></span><span class="sxs-lookup"><span data-stu-id="9c568-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="9c568-125">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="9c568-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c568-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c568-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="9c568-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="9c568-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
