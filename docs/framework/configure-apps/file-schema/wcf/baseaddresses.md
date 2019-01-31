---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: dc4b31e729f9037da101bdf3e6cde28e91b1a070
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277022"
---
# <a name="baseaddresses"></a><span data-ttu-id="3a053-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="3a053-101">\<baseAddresses></span></span>
<span data-ttu-id="3a053-102">Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.</span><span class="sxs-lookup"><span data-stu-id="3a053-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="3a053-103">Si una dirección base está presente, los puntos de conexión se pueden configurar con direcciones relativas a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="3a053-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="3a053-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3a053-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3a053-105">\<client></span><span class="sxs-lookup"><span data-stu-id="3a053-105">\<client></span></span>  
<span data-ttu-id="3a053-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="3a053-106">\<endpoint></span></span>  
<span data-ttu-id="3a053-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="3a053-107">\<host></span></span>  
<span data-ttu-id="3a053-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="3a053-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a053-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a053-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="3a053-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="3a053-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a053-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3a053-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3a053-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3a053-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a053-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="3a053-113">Attributes</span></span>  
 <span data-ttu-id="3a053-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3a053-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3a053-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3a053-115">Child Elements</span></span>  
  
|<span data-ttu-id="3a053-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a053-116">Element</span></span>|<span data-ttu-id="3a053-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a053-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a053-118">\<add></span><span class="sxs-lookup"><span data-stu-id="3a053-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="3a053-119">Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="3a053-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a053-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3a053-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3a053-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a053-121">Element</span></span>|<span data-ttu-id="3a053-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a053-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a053-123">\<host></span><span class="sxs-lookup"><span data-stu-id="3a053-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="3a053-124">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="3a053-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a053-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a053-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="3a053-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="3a053-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
