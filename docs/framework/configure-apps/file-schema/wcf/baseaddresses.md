---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 7d0afd638e9a311b69ff47b6789d5fde093945ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212107"
---
# <a name="baseaddresses"></a><span data-ttu-id="8a899-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="8a899-101">\<baseAddresses></span></span>
<span data-ttu-id="8a899-102">Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.</span><span class="sxs-lookup"><span data-stu-id="8a899-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="8a899-103">Si una dirección base está presente, los extremos se pueden configurar con direcciones relativas a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="8a899-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="8a899-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8a899-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8a899-105">\<client></span><span class="sxs-lookup"><span data-stu-id="8a899-105">\<client></span></span>  
<span data-ttu-id="8a899-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="8a899-106">\<endpoint></span></span>  
<span data-ttu-id="8a899-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="8a899-107">\<host></span></span>  
<span data-ttu-id="8a899-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="8a899-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a899-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a899-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="8a899-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="8a899-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a899-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8a899-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8a899-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8a899-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a899-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="8a899-113">Attributes</span></span>  
 <span data-ttu-id="8a899-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8a899-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8a899-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8a899-115">Child Elements</span></span>  
  
|<span data-ttu-id="8a899-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a899-116">Element</span></span>|<span data-ttu-id="8a899-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a899-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a899-118">\<add></span><span class="sxs-lookup"><span data-stu-id="8a899-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="8a899-119">Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="8a899-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8a899-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a899-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8a899-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a899-121">Element</span></span>|<span data-ttu-id="8a899-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a899-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a899-123">\<host ></span><span class="sxs-lookup"><span data-stu-id="8a899-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="8a899-124">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="8a899-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a899-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a899-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="8a899-126">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="8a899-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
