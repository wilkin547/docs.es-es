---
description: 'Más información sobre: <add> de <baseAddressPrefixFilter>'
title: <add> de <baseAddressPrefixFilter>
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: f3abdf59223921a56c96e02dd95babc54f91dc03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804054"
---
# <a name="add-of-baseaddressprefixfilter"></a><span data-ttu-id="ddc51-103">\<add> de \<baseAddressPrefixFilter></span><span class="sxs-lookup"><span data-stu-id="ddc51-103">\<add> of \<baseAddressPrefixFilter></span></span>

<span data-ttu-id="ddc51-104">Representa un elemento de configuración que especifica un filtro de paso a través, que proporciona un mecanismo para seleccionar los enlaces de Internet Information Services (IIS) adecuados al hospedar una aplicación Windows Communication Foundation (WCF) en IIS.</span><span class="sxs-lookup"><span data-stu-id="ddc51-104">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddressPrefixFilters>**](baseaddressprefixfilters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="ddc51-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddc51-105">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddc51-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ddc51-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ddc51-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ddc51-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddc51-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="ddc51-108">Attributes</span></span>  
  
|<span data-ttu-id="ddc51-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="ddc51-109">Attribute</span></span>|<span data-ttu-id="ddc51-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddc51-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ddc51-111">prefix</span><span class="sxs-lookup"><span data-stu-id="ddc51-111">prefix</span></span>|<span data-ttu-id="ddc51-112">Un URI que se utiliza para coincidir con una parte de una dirección base.</span><span class="sxs-lookup"><span data-stu-id="ddc51-112">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ddc51-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ddc51-113">Child Elements</span></span>  

 <span data-ttu-id="ddc51-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ddc51-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ddc51-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ddc51-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ddc51-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="ddc51-116">Element</span></span>|<span data-ttu-id="ddc51-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddc51-117">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters>](baseaddressprefixfilters.md)|<span data-ttu-id="ddc51-118">Colección de elementos de configuración que especifican filtros de paso a través, que proporcionan un mecanismo para seleccionar los enlaces de IIS adecuados al hospedar una aplicación Windows Communication Foundation (WCF) en IIS.</span><span class="sxs-lookup"><span data-stu-id="ddc51-118">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddc51-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ddc51-119">Remarks</span></span>  

 <span data-ttu-id="ddc51-120">Un filtro de prefijo proporciona un método para que los proveedores de host compartido especifiquen qué identificadores URI va a utiliza el servicio.</span><span class="sxs-lookup"><span data-stu-id="ddc51-120">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="ddc51-121">Permite a los host compartidos hospedar varias aplicaciones con direcciones base diferentes para el mismo esquema en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="ddc51-121">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="ddc51-122">Los sitios web de IIS son los contenedores para las aplicaciones virtuales que contienen los directorios virtuales.</span><span class="sxs-lookup"><span data-stu-id="ddc51-122">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="ddc51-123">Se puede tener acceso a la aplicación de un sitio a través de uno o varios enlaces de IIS.</span><span class="sxs-lookup"><span data-stu-id="ddc51-123">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="ddc51-124">Los enlaces de IIS proporcionan dos partes de información: protocolo de enlace e información de enlace.</span><span class="sxs-lookup"><span data-stu-id="ddc51-124">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="ddc51-125">El protocolo de enlace (por ejemplo, HTTP), define el esquema sobre el que la comunicación se produce y la información de enlace (por ejemplo, IPAddress, Puerto, Hostheader) contiene los datos utilizados para tener acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="ddc51-125">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="ddc51-126">IIS admite la especificación de varios enlaces IIS para cada sitio, lo que tiene como resultado varias direcciones base para cada esquema.</span><span class="sxs-lookup"><span data-stu-id="ddc51-126">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="ddc51-127">Dado que un servicio WCF hospedado bajo un sitio permite el enlace solo a una dirección base para cada esquema, puede usar la característica de filtro de prefijo para seleccionar la dirección base necesaria del servicio hospedado.</span><span class="sxs-lookup"><span data-stu-id="ddc51-127">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="ddc51-128">Las direcciones base de entrada, proporcionadas por IIS, se filtran dependiendo del filtro de la lista de prefijos opcional.</span><span class="sxs-lookup"><span data-stu-id="ddc51-128">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="ddc51-129">Por ejemplo, su sitio puede contener las siguientes direcciones base:</span><span class="sxs-lookup"><span data-stu-id="ddc51-129">For example, your site can contain the following base addresses:</span></span>
  
```http
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="ddc51-130">Puede utilizar el archivo de configuración siguiente para especificar un filtro del prefijo en el nivel appdomain.</span><span class="sxs-lookup"><span data-stu-id="ddc51-130">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="ddc51-131">En este ejemplo, `net.tcp://test1.fabrikam.com:8000` y `http://test2.fabrikam.com:9000` son las únicas direcciones base para los respectivos esquemas a través de los que se puede pasar.</span><span class="sxs-lookup"><span data-stu-id="ddc51-131">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="ddc51-132">De forma predeterminada, cuando no se especifica el prefijo, se pasan todas las direcciones.</span><span class="sxs-lookup"><span data-stu-id="ddc51-132">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="ddc51-133">Especificar el prefijo permite que solo la dirección base coincidente para ese esquema se pase a través.</span><span class="sxs-lookup"><span data-stu-id="ddc51-133">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ddc51-134">El filtro no admite ningún carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="ddc51-134">The filter does not support any wildcards.</span></span> <span data-ttu-id="ddc51-135">Además, las direcciones base proporcionadas por IIS pueden tener direcciones enlazadas a otros esquemas no presentes en la lista `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="ddc51-135">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="ddc51-136">Estas direcciones no se filtran.</span><span class="sxs-lookup"><span data-stu-id="ddc51-136">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddc51-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddc51-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="ddc51-138">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ddc51-138">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
