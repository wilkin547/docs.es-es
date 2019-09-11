---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 9b3ed6b39f1743249925d5b6d9a47845c87983bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850207"
---
# <a name="baseaddresses"></a><span data-ttu-id="56d69-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="56d69-101">\<baseAddresses></span></span>
<span data-ttu-id="56d69-102">Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.</span><span class="sxs-lookup"><span data-stu-id="56d69-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="56d69-103">Si una dirección base está presente, los extremos se pueden configurar con direcciones relativas a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="56d69-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
<span data-ttu-id="56d69-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="56d69-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="56d69-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="56d69-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="56d69-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de servicios**](services.md)</span><span class="sxs-lookup"><span data-stu-id="56d69-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="56d69-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de servicio**](service.md)</span><span class="sxs-lookup"><span data-stu-id="56d69-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="56d69-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> host**](host.md)</span><span class="sxs-lookup"><span data-stu-id="56d69-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="56d69-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> baseAddresses**</span><span class="sxs-lookup"><span data-stu-id="56d69-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56d69-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56d69-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="56d69-111">Type</span><span class="sxs-lookup"><span data-stu-id="56d69-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56d69-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="56d69-112">Attributes and Elements</span></span>  
 <span data-ttu-id="56d69-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="56d69-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56d69-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="56d69-114">Attributes</span></span>  
 <span data-ttu-id="56d69-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="56d69-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="56d69-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="56d69-116">Child Elements</span></span>  
  
|<span data-ttu-id="56d69-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="56d69-117">Element</span></span>|<span data-ttu-id="56d69-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="56d69-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56d69-119">\<add></span><span class="sxs-lookup"><span data-stu-id="56d69-119">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="56d69-120">Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="56d69-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56d69-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="56d69-121">Parent Elements</span></span>  
  
|<span data-ttu-id="56d69-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="56d69-122">Element</span></span>|<span data-ttu-id="56d69-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="56d69-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56d69-124">\<> host</span><span class="sxs-lookup"><span data-stu-id="56d69-124">\<host></span></span>](host.md)|<span data-ttu-id="56d69-125">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="56d69-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56d69-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="56d69-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="56d69-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="56d69-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
