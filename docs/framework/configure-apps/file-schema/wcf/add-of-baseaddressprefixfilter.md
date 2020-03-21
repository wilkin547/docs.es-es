---
title: <add> de <baseAddressPrefixFilter>
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: 8fdae02b558708a9b3f4535123752dce12dd5cf5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153145"
---
# <a name="add-of-baseaddressprefixfilter"></a><span data-ttu-id="f0e44-102">\<agregue> \<de baseAddressPrefixFilter></span><span class="sxs-lookup"><span data-stu-id="f0e44-102">\<add> of \<baseAddressPrefixFilter></span></span>
<span data-ttu-id="f0e44-103">Representa un elemento de configuración que especifica un filtro de paso a través, que proporciona un mecanismo para elegir los enlaces de Internet Information Services (IIS) adecuados al hospedar una aplicación de Windows Communication Foundation (WCF) en IIS.</span><span class="sxs-lookup"><span data-stu-id="f0e44-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
<span data-ttu-id="f0e44-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0e44-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f0e44-105">&nbsp;&nbsp;[**\<>system.serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f0e44-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f0e44-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="f0e44-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="f0e44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddressPrefixFilters>**](baseaddressprefixfilters.md)</span><span class="sxs-lookup"><span data-stu-id="f0e44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddressPrefixFilters>**](baseaddressprefixfilters.md)</span></span>\
<span data-ttu-id="f0e44-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<añadir>**</span><span class="sxs-lookup"><span data-stu-id="f0e44-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e44-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0e44-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0e44-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f0e44-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f0e44-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f0e44-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0e44-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="f0e44-112">Attributes</span></span>  
  
|<span data-ttu-id="f0e44-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="f0e44-113">Attribute</span></span>|<span data-ttu-id="f0e44-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0e44-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0e44-115">prefix</span><span class="sxs-lookup"><span data-stu-id="f0e44-115">prefix</span></span>|<span data-ttu-id="f0e44-116">Un URI que se utiliza para coincidir con una parte de una dirección base.</span><span class="sxs-lookup"><span data-stu-id="f0e44-116">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0e44-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f0e44-117">Child Elements</span></span>  
 <span data-ttu-id="f0e44-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f0e44-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0e44-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f0e44-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f0e44-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0e44-120">Element</span></span>|<span data-ttu-id="f0e44-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0e44-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0e44-122">\<baseAddressPrefixFilters></span><span class="sxs-lookup"><span data-stu-id="f0e44-122">\<baseAddressPrefixFilters></span></span>](baseaddressprefixfilters.md)|<span data-ttu-id="f0e44-123">Colección de elementos de configuración que especifican filtros de paso a través, que proporcionan un mecanismo para elegir los enlaces IIS adecuados al hospedar una aplicación de Windows Communication Foundation (WCF) en IIS.</span><span class="sxs-lookup"><span data-stu-id="f0e44-123">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0e44-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f0e44-124">Remarks</span></span>  
 <span data-ttu-id="f0e44-125">Un filtro de prefijo proporciona un método para que los proveedores de host compartido especifiquen qué identificadores URI va a utiliza el servicio.</span><span class="sxs-lookup"><span data-stu-id="f0e44-125">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="f0e44-126">Permite a los host compartidos hospedar varias aplicaciones con direcciones base diferentes para el mismo esquema en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="f0e44-126">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="f0e44-127">Los sitios web de IIS son los contenedores para las aplicaciones virtuales que contienen los directorios virtuales.</span><span class="sxs-lookup"><span data-stu-id="f0e44-127">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="f0e44-128">Se puede tener acceso a la aplicación de un sitio a través de uno o varios enlaces de IIS.</span><span class="sxs-lookup"><span data-stu-id="f0e44-128">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="f0e44-129">Los enlaces de IIS proporcionan dos partes de información: protocolo de enlace e información de enlace.</span><span class="sxs-lookup"><span data-stu-id="f0e44-129">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="f0e44-130">El protocolo de enlace (por ejemplo, HTTP), define el esquema sobre el que la comunicación se produce y la información de enlace (por ejemplo, IPAddress, Puerto, Hostheader) contiene los datos utilizados para tener acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="f0e44-130">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="f0e44-131">IIS admite la especificación de varios enlaces IIS para cada sitio, lo que tiene como resultado varias direcciones base para cada esquema.</span><span class="sxs-lookup"><span data-stu-id="f0e44-131">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="f0e44-132">Dado que un servicio WCF hospedado en un sitio permite el enlace a una sola dirección base para cada esquema, puede usar la característica de filtro de prefijo para elegir la dirección base necesaria del servicio hospedado.</span><span class="sxs-lookup"><span data-stu-id="f0e44-132">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="f0e44-133">Las direcciones base de entrada, proporcionadas por IIS, se filtran dependiendo del filtro de la lista de prefijos opcional.</span><span class="sxs-lookup"><span data-stu-id="f0e44-133">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="f0e44-134">Por ejemplo, el sitio puede contener las siguientes direcciones base:</span><span class="sxs-lookup"><span data-stu-id="f0e44-134">For example, your site can contain the following base addresses:</span></span>
  
```
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="f0e44-135">Puede utilizar el archivo de configuración siguiente para especificar un filtro del prefijo en el nivel appdomain.</span><span class="sxs-lookup"><span data-stu-id="f0e44-135">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 <span data-ttu-id="f0e44-136">En este ejemplo, `net.tcp://test1.fabrikam.com:8000` y `http://test2.fabrikam.com:9000` son las únicas direcciones base para los respectivos esquemas a través de los que se puede pasar.</span><span class="sxs-lookup"><span data-stu-id="f0e44-136">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="f0e44-137">De forma predeterminada, cuando no se especifica el prefijo, se pasan todas las direcciones.</span><span class="sxs-lookup"><span data-stu-id="f0e44-137">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="f0e44-138">Especificar el prefijo permite que solo la dirección base coincidente para ese esquema se pase a través.</span><span class="sxs-lookup"><span data-stu-id="f0e44-138">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f0e44-139">El filtro no admite ningún carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="f0e44-139">The filter does not support any wildcards.</span></span> <span data-ttu-id="f0e44-140">Además, las direcciones base proporcionadas por IIS pueden tener direcciones enlazadas a otros esquemas no presentes en la lista `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="f0e44-140">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="f0e44-141">Estas direcciones no se filtran.</span><span class="sxs-lookup"><span data-stu-id="f0e44-141">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0e44-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0e44-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="f0e44-143">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="f0e44-143">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
