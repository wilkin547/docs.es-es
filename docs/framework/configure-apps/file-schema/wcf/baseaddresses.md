---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 7d0afd638e9a311b69ff47b6789d5fde093945ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212107"
---
# <a name="baseaddresses"></a><span data-ttu-id="6afae-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="6afae-101">\<baseAddresses></span></span>
<span data-ttu-id="6afae-102">Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.</span><span class="sxs-lookup"><span data-stu-id="6afae-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="6afae-103">Si una dirección base está presente, los extremos se pueden configurar con direcciones relativas a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="6afae-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="6afae-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6afae-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6afae-105">\<client></span><span class="sxs-lookup"><span data-stu-id="6afae-105">\<client></span></span>  
<span data-ttu-id="6afae-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="6afae-106">\<endpoint></span></span>  
<span data-ttu-id="6afae-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="6afae-107">\<host></span></span>  
<span data-ttu-id="6afae-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="6afae-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6afae-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6afae-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="6afae-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="6afae-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6afae-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6afae-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6afae-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6afae-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6afae-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="6afae-113">Attributes</span></span>  
 <span data-ttu-id="6afae-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6afae-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6afae-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6afae-115">Child Elements</span></span>  
  
|<span data-ttu-id="6afae-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="6afae-116">Element</span></span>|<span data-ttu-id="6afae-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="6afae-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6afae-118">\<add></span><span class="sxs-lookup"><span data-stu-id="6afae-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="6afae-119">Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="6afae-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6afae-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6afae-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6afae-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="6afae-121">Element</span></span>|<span data-ttu-id="6afae-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="6afae-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6afae-123">\<host></span><span class="sxs-lookup"><span data-stu-id="6afae-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="6afae-124">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="6afae-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6afae-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="6afae-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="6afae-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="6afae-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
