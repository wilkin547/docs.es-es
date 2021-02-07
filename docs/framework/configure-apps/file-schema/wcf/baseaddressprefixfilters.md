---
description: 'Más información acerca de: <baseAddressPrefixFilters>'
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 9212838393ead04bdcd475b314bb2707e6f899ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749680"
---
# \<baseAddressPrefixFilters>

<span data-ttu-id="7f579-102">Representa una colección de elementos de configuración que especifican los filtros de paso a través, que proporcionan un mecanismo para seleccionar los enlaces de Internet Information Services (IIS) adecuados al hospedar la aplicación Windows Communication Foundation (WCF) en IIS.</span><span class="sxs-lookup"><span data-stu-id="7f579-102">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="7f579-103">\<baseAddressPrefixFilters> no reconoce "localhost"; en su lugar, use el nombre completo de la máquina.</span><span class="sxs-lookup"><span data-stu-id="7f579-103">\<baseAddressPrefixFilters> does not recognize "localhost"; use the fully qualified machine name instead.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddressPrefixFilters>**  
  
## <a name="syntax"></a><span data-ttu-id="7f579-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f579-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f579-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7f579-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7f579-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7f579-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f579-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="7f579-107">Attributes</span></span>  

 <span data-ttu-id="7f579-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7f579-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7f579-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7f579-109">Child Elements</span></span>  
  
|<span data-ttu-id="7f579-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f579-110">Element</span></span>|<span data-ttu-id="7f579-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f579-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddressprefixfilter.md)|<span data-ttu-id="7f579-112">Agrega un elemento de configuración que especifica un filtro de prefijo para las direcciones base usadas por el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="7f579-112">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f579-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7f579-113">Parent Elements</span></span>  
  
|<span data-ttu-id="7f579-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f579-114">Element</span></span>|<span data-ttu-id="7f579-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f579-115">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="7f579-116">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="7f579-116">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f579-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7f579-117">Remarks</span></span>  

 <span data-ttu-id="7f579-118">Un filtro de prefijo proporciona un método para que los proveedores de host compartido especifiquen qué identificadores URI va a utiliza el servicio.</span><span class="sxs-lookup"><span data-stu-id="7f579-118">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="7f579-119">Permite a los host compartidos hospedar varias aplicaciones con direcciones base diferentes para el mismo esquema en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="7f579-119">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="7f579-120">Los sitios web de IIS son los contenedores para las aplicaciones virtuales que contienen los directorios virtuales.</span><span class="sxs-lookup"><span data-stu-id="7f579-120">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="7f579-121">Se puede tener acceso a la aplicación en un sitio a través de uno o más enlaces de IIS.</span><span class="sxs-lookup"><span data-stu-id="7f579-121">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="7f579-122">Los enlaces de IIS proporcionan dos partes de información: protocolo de enlace e información de enlace.</span><span class="sxs-lookup"><span data-stu-id="7f579-122">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="7f579-123">El protocolo de enlace (por ejemplo, HTTP), define el esquema sobre el que la comunicación se produce y la información de enlace (por ejemplo, IPAddress, Puerto, Hostheader) contiene los datos utilizados para tener acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="7f579-123">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="7f579-124">IIS admite la especificación de varios enlaces IIS para cada sitio, lo que tiene como resultado varias direcciones base para cada esquema.</span><span class="sxs-lookup"><span data-stu-id="7f579-124">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="7f579-125">Dado que un servicio WCF hospedado bajo un sitio permite el enlace solo a una dirección base para cada esquema, puede usar la característica de filtro de prefijo para seleccionar la dirección base necesaria del servicio hospedado.</span><span class="sxs-lookup"><span data-stu-id="7f579-125">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="7f579-126">Las direcciones base de entrada, proporcionadas por IIS, se filtran dependiendo del filtro de la lista de prefijos opcional.</span><span class="sxs-lookup"><span data-stu-id="7f579-126">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="7f579-127">Por ejemplo, su sitio puede contener las siguientes direcciones base:</span><span class="sxs-lookup"><span data-stu-id="7f579-127">For example, your site can contain the following base addresses:</span></span>
  
```http
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="7f579-128">Puede utilizar el archivo de configuración siguiente para especificar un filtro del prefijo en el nivel appdomain.</span><span class="sxs-lookup"><span data-stu-id="7f579-128">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="7f579-129">En este ejemplo, `net.tcp://test1.fabrikam.com:8000` y `http://test2.fabrikam.com:9000` son las únicas direcciones base para sus respectivos esquemas, a través de los que se puede pasar.</span><span class="sxs-lookup"><span data-stu-id="7f579-129">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="7f579-130">De forma predeterminada, cuando no se especifica el prefijo, se pasan todas las direcciones.</span><span class="sxs-lookup"><span data-stu-id="7f579-130">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="7f579-131">Especificar el prefijo permite que solo la dirección base coincidente para ese esquema se pase a través.</span><span class="sxs-lookup"><span data-stu-id="7f579-131">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7f579-132">El filtro no admite ningún carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="7f579-132">The filter does not support any wildcards.</span></span> <span data-ttu-id="7f579-133">Además, las direcciones base proporcionadas por IIS pueden tener direcciones enlazadas a otros esquemas no presentes en la lista `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="7f579-133">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="7f579-134">Estas direcciones no se filtran.</span><span class="sxs-lookup"><span data-stu-id="7f579-134">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f579-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f579-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="7f579-136">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="7f579-136">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
