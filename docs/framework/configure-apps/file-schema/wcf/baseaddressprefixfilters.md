---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 378db238d647be2248c0303f45aece42f7ea5b31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227631"
---
# <a name="baseaddressprefixfilters"></a><span data-ttu-id="c40b5-101">\<baseAddressPrefixFilters></span><span class="sxs-lookup"><span data-stu-id="c40b5-101">\<baseAddressPrefixFilters></span></span>
<span data-ttu-id="c40b5-102">Representa una colección de configuración de elementos que especifican pasan a través de filtros, que proporcionan un mecanismo para escoger los enlaces adecuados de Internet Information Services (IIS) al hospedar la aplicación de Windows Communication Foundation (WCF) en IIS.</span><span class="sxs-lookup"><span data-stu-id="c40b5-102">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c40b5-103">\<baseAddressPrefixFilters > no reconoce el "localhost", use el nombre de equipo completo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c40b5-103">\<baseAddressPrefixFilters> does not recognize "localhost", use the fully qualified machine name instead.</span></span>  
  
 <span data-ttu-id="c40b5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c40b5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c40b5-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="c40b5-105">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c40b5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c40b5-106">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c40b5-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c40b5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c40b5-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c40b5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c40b5-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="c40b5-109">Attributes</span></span>  
 <span data-ttu-id="c40b5-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c40b5-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c40b5-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c40b5-111">Child Elements</span></span>  
  
|<span data-ttu-id="c40b5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c40b5-112">Element</span></span>|<span data-ttu-id="c40b5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c40b5-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c40b5-114">\<add></span><span class="sxs-lookup"><span data-stu-id="c40b5-114">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddressprefixfilter.md)|<span data-ttu-id="c40b5-115">Agrega un elemento de configuración que especifica un filtro de prefijo para las direcciones base usadas por el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="c40b5-115">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c40b5-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c40b5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c40b5-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c40b5-117">Element</span></span>|<span data-ttu-id="c40b5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c40b5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c40b5-119">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="c40b5-119">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="c40b5-120">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="c40b5-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c40b5-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c40b5-121">Remarks</span></span>  
 <span data-ttu-id="c40b5-122">Un filtro de prefijo proporciona un método para que los proveedores de host compartido especifiquen qué identificadores URI va a utiliza el servicio.</span><span class="sxs-lookup"><span data-stu-id="c40b5-122">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="c40b5-123">Permite a los host compartidos hospedar varias aplicaciones con direcciones base diferentes para el mismo esquema en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="c40b5-123">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="c40b5-124">Los sitios web de IIS son los contenedores para las aplicaciones virtuales que contienen los directorios virtuales.</span><span class="sxs-lookup"><span data-stu-id="c40b5-124">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="c40b5-125">Se puede tener acceso a la aplicación en un sitio a través de uno o más enlaces de IIS.</span><span class="sxs-lookup"><span data-stu-id="c40b5-125">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="c40b5-126">Los enlaces de IIS proporcionan dos partes de información: protocolo de enlace e información de enlace.</span><span class="sxs-lookup"><span data-stu-id="c40b5-126">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="c40b5-127">El protocolo de enlace (por ejemplo, HTTP), define el esquema sobre el que la comunicación se produce y la información de enlace (por ejemplo, IPAddress, Puerto, Hostheader) contiene los datos utilizados para tener acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="c40b5-127">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="c40b5-128">IIS admite la especificación de varios enlaces IIS para cada sitio, lo que tiene como resultado varias direcciones base para cada esquema.</span><span class="sxs-lookup"><span data-stu-id="c40b5-128">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="c40b5-129">Dado que un servicio WCF hospedado en un sitio permite el enlace a sólo una dirección base para cada esquema, puede usar la característica de filtro de prefijo para escoger la dirección base necesaria del servicio hospedado.</span><span class="sxs-lookup"><span data-stu-id="c40b5-129">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="c40b5-130">Las direcciones base de entrada, proporcionadas por IIS, se filtran dependiendo del filtro de la lista de prefijos opcional.</span><span class="sxs-lookup"><span data-stu-id="c40b5-130">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="c40b5-131">Por ejemplo, su sitio puede contener las direcciones base siguientes.</span><span class="sxs-lookup"><span data-stu-id="c40b5-131">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="c40b5-132">Puede utilizar el archivo de configuración siguiente para especificar un filtro del prefijo en el nivel appdomain.</span><span class="sxs-lookup"><span data-stu-id="c40b5-132">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="c40b5-133">En este ejemplo, `net.tcp://test1.fabrikam.com:8000` y `http://test2.fabrikam.com:9000` son las únicas direcciones base para sus respectivos esquemas, a través de los que se puede pasar.</span><span class="sxs-lookup"><span data-stu-id="c40b5-133">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="c40b5-134">De forma predeterminada, cuando no se especifica el prefijo, se pasan todas las direcciones.</span><span class="sxs-lookup"><span data-stu-id="c40b5-134">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="c40b5-135">Especificar el prefijo permite que solo la dirección base coincidente para ese esquema se pase a través.</span><span class="sxs-lookup"><span data-stu-id="c40b5-135">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c40b5-136">El filtro no admite ningún carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="c40b5-136">The filter does not support any wildcards.</span></span> <span data-ttu-id="c40b5-137">Además, las direcciones base proporcionadas por IIS pueden tener direcciones enlazadas a otros esquemas no presentes en la lista `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="c40b5-137">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="c40b5-138">Estas direcciones no se filtran.</span><span class="sxs-lookup"><span data-stu-id="c40b5-138">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c40b5-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="c40b5-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="c40b5-140">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="c40b5-140">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
