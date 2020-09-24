---
title: <serviceHostingEnvironment>
ms.date: 03/30/2017
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
ms.openlocfilehash: 5a7043064593fa329618510d15baeb87da432652
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167109"
---
# \<serviceHostingEnvironment>

<span data-ttu-id="2c429-101">Este elemento define el tipo en el que el entorno de hospedaje de servicio crea instancias de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="2c429-101">This element defines the type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="2c429-102">Si este elemento está vacío, se usa el tipo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2c429-102">If this element is empty, the default type is used.</span></span> <span data-ttu-id="2c429-103">Este elemento solo se puede usar en los archivos de configuración del nivel de aplicación o equipo.</span><span class="sxs-lookup"><span data-stu-id="2c429-103">This element can only be used at the application or machine level configuration files.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceHostingEnvironment>**  
  
## <a name="syntax"></a><span data-ttu-id="2c429-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c429-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean"
                           minFreeMemoryPercentageToActivateService="Integer"
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c429-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2c429-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2c429-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2c429-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c429-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="2c429-107">Attributes</span></span>  
  
|<span data-ttu-id="2c429-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="2c429-108">Attribute</span></span>|<span data-ttu-id="2c429-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c429-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2c429-110">aspNetCompatibilityEnabled</span><span class="sxs-lookup"><span data-stu-id="2c429-110">aspNetCompatibilityEnabled</span></span>|<span data-ttu-id="2c429-111">Un valor booleano que indica si se ha activado el modo de compatibilidad de ASP.NET para la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="2c429-111">A Boolean value indicating whether the ASP.NET compatibility mode has been turned on for the current application.</span></span> <span data-ttu-id="2c429-112">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="2c429-112">The default is `false`.</span></span><br /><br /> <span data-ttu-id="2c429-113">Cuando este atributo se establece en `true` , las solicitudes a los servicios Windows Communication Foundation (WCF) fluyen a través de la canalización HTTP ASP.net y se prohíbe la comunicación a través de protocolos que no son http.</span><span class="sxs-lookup"><span data-stu-id="2c429-113">When this attribute is set to `true`, requests to Windows Communication Foundation (WCF) services flow through the ASP.NET HTTP pipeline, and communication over non-HTTP protocols is prohibited.</span></span> <span data-ttu-id="2c429-114">Para obtener más información, vea [servicios WCF y ASP.net](../../../wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="2c429-114">For more information, see [WCF Services and ASP.NET](../../../wcf/feature-details/wcf-services-and-aspnet.md).</span></span>|  
|<span data-ttu-id="2c429-115">minFreeMemoryPercentageToActivateService</span><span class="sxs-lookup"><span data-stu-id="2c429-115">minFreeMemoryPercentageToActivateService</span></span>|<span data-ttu-id="2c429-116">Un entero que especifica la cantidad mínima de memoria libre que debe estar disponible para el sistema, antes de que se pueda activar un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="2c429-116">An integer that specifies the minimum amount of free memory that should be available to the system, before a WCF service can be activated.</span></span> <span data-ttu-id="2c429-117">**PRECAUCIÓN:**  Si se especifica este atributo junto con la confianza parcial en el archivo web.config de un servicio WCF, se producirá una <xref:System.Security.SecurityException> cuando se ejecute el servicio.</span><span class="sxs-lookup"><span data-stu-id="2c429-117">**Caution:**  Specifying this attribute along with partial trust in the web.config file of a WCF service will result in a <xref:System.Security.SecurityException> when the service is run.</span></span>|  
|<span data-ttu-id="2c429-118">multipleSiteBindingsEnabled</span><span class="sxs-lookup"><span data-stu-id="2c429-118">multipleSiteBindingsEnabled</span></span>|<span data-ttu-id="2c429-119">Valor booleano que especifica si están habilitados varios enlaces de IIS por sitio.</span><span class="sxs-lookup"><span data-stu-id="2c429-119">A Boolean value that specifies whether multiple IIS bindings per site is enabled.</span></span><br /><br /> <span data-ttu-id="2c429-120">IIS se compone de sitios web, que son contenedores de aplicaciones virtuales que contienen directorios virtuales.</span><span class="sxs-lookup"><span data-stu-id="2c429-120">IIS consists of web sites, which are containers for virtual applications containing virtual directories.</span></span> <span data-ttu-id="2c429-121">Se puede tener acceso a la aplicación de un sitio a través de uno o varios enlaces de IIS.</span><span class="sxs-lookup"><span data-stu-id="2c429-121">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="2c429-122">Un enlace de IIS proporciona dos piezas de información: un protocolo de enlace e información de enlace.</span><span class="sxs-lookup"><span data-stu-id="2c429-122">An IIS binding provides two pieces of information: a binding protocol and binding information.</span></span> <span data-ttu-id="2c429-123">El protocolo de enlace define el esquema sobre el que se produce la comunicación, y la información de enlace es la información usada para tener acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="2c429-123">Binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span> <span data-ttu-id="2c429-124">Un ejemplo de un protocolo de enlace puede ser HTTP, mientras que la información de enlace puede contener una dirección IP, un puerto, un encabezado de host, etc.</span><span class="sxs-lookup"><span data-stu-id="2c429-124">An example of a binding protocol can be HTTP, whereas binding information can contain an IP address, Port, host header, etc.</span></span><br /><br /> <span data-ttu-id="2c429-125">IIS permite especificar varios enlaces de IIS por sitio, lo que genera varias direcciones base por esquema.</span><span class="sxs-lookup"><span data-stu-id="2c429-125">IIS supports specifying multiple IIS bindings per site, which results in multiple base addresses per scheme.</span></span> <span data-ttu-id="2c429-126">Sin embargo, un servicio de Windows Communication Foundation (WCF) hospedado en un sitio permite el enlace solo a una baseAddress por esquema.</span><span class="sxs-lookup"><span data-stu-id="2c429-126">However, a Windows Communication Foundation (WCF) service hosted under a site allows binding to only one baseAddress per scheme.</span></span><br /><br /> <span data-ttu-id="2c429-127">Para habilitar varios enlaces de IIS por sitio para un servicio de Windows Communication Foundation (WCF), establezca este atributo en `true` .</span><span class="sxs-lookup"><span data-stu-id="2c429-127">To enable multiple IIS bindings per site for a Windows Communication Foundation (WCF) service, set this attribute to `true`.</span></span> <span data-ttu-id="2c429-128">Observe que solo se admiten varios enlaces del sitio para el protocolo HTTP.</span><span class="sxs-lookup"><span data-stu-id="2c429-128">Notice that multiple site binding is supported only for the HTTP protocol.</span></span> <span data-ttu-id="2c429-129">La dirección de puntos de conexión en el archivo de configuración tiene que ser un URI completo.</span><span class="sxs-lookup"><span data-stu-id="2c429-129">The address of endpoints in the configuration file needs to be a complete URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c429-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2c429-130">Child Elements</span></span>  
  
|<span data-ttu-id="2c429-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c429-131">Element</span></span>|<span data-ttu-id="2c429-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c429-132">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters>](baseaddressprefixfilters.md)|<span data-ttu-id="2c429-133">Una colección de elementos de configuración que especifican los filtros de prefijo de las direcciones base usadas por el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="2c429-133">A collection of configuration elements that specify prefix filters for the base addresses used by the service host.</span></span>|  
|[\<serviceActivations>](serviceactivations.md)|<span data-ttu-id="2c429-134">Sección de configuración que describe la configuración de activación.</span><span class="sxs-lookup"><span data-stu-id="2c429-134">A configuration section that describes activation settings.</span></span>|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="2c429-135">Una colección de elementos de configuración que identifican el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="2c429-135">A collection of configuration elements that identify the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c429-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2c429-136">Parent Elements</span></span>  
  
|<span data-ttu-id="2c429-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c429-137">Element</span></span>|<span data-ttu-id="2c429-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c429-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c429-139">serviceModel</span><span class="sxs-lookup"><span data-stu-id="2c429-139">serviceModel</span></span>|<span data-ttu-id="2c429-140">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2c429-140">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c429-141">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2c429-141">Remarks</span></span>  

 <span data-ttu-id="2c429-142">De forma predeterminada, los servicios WCF se ejecutan en paralelo con ASP.NET en dominios de aplicación hospedados (AppDomain).</span><span class="sxs-lookup"><span data-stu-id="2c429-142">By default, WCF services run side-by-side with ASP.NET in hosted Application Domains (AppDomain).</span></span> <span data-ttu-id="2c429-143">Aunque WCF y ASP.NET pueden coexistir en el mismo AppDomain, la canalización de HTTP de ASP.NET no procesa de forma predeterminada las solicitudes de WCF.</span><span class="sxs-lookup"><span data-stu-id="2c429-143">Even though WCF and ASP.NET can coexist in the same AppDomain, WCF requests are not processed by the ASP.NET HTTP Pipeline by default.</span></span> <span data-ttu-id="2c429-144">Como resultado, varios elementos de la plataforma de la aplicación ASP.NET no están disponibles para los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="2c429-144">As a result, several elements of the ASP.NET application platform are not available to WCF services.</span></span> <span data-ttu-id="2c429-145">Entre ellas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="2c429-145">These include</span></span>  
  
- <span data-ttu-id="2c429-146">Autorización de dirección URL/archivo de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2c429-146">ASP.NET File/URL Authorization</span></span>  
  
- <span data-ttu-id="2c429-147">Suplantación de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2c429-147">ASP.NET Impersonation</span></span>  
  
- <span data-ttu-id="2c429-148">Estado de sesión basado en cookies</span><span class="sxs-lookup"><span data-stu-id="2c429-148">Cookie-based Session State</span></span>  
  
- <span data-ttu-id="2c429-149">HttpContext.Current</span><span class="sxs-lookup"><span data-stu-id="2c429-149">HttpContext.Current</span></span>  
  
- <span data-ttu-id="2c429-150">Extensibilidad de la canalización a través de HttpModule personalizado</span><span class="sxs-lookup"><span data-stu-id="2c429-150">Pipeline Extensibility via custom HttpModule</span></span>  
  
 <span data-ttu-id="2c429-151">Si sus servicios WCF necesitan funcionar en el contexto de ASP.NET, y solo comunicarse sobre HTTP, puede usar el modo de compatibilidad de ASP.NET de WCF.</span><span class="sxs-lookup"><span data-stu-id="2c429-151">If your WCF services need to function in the ASP.NET context, and communicate only over HTTP, you can use WCF’s ASP.NET compatibility mode.</span></span> <span data-ttu-id="2c429-152">Este modo se activa cuando el atributo `aspNetCompatibilityEnabled` se establece en `true` en el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c429-152">This mode is turned on when the `aspNetCompatibilityEnabled` attribute is set to `true` at the application level.</span></span> <span data-ttu-id="2c429-153">Las implementaciones del servicio deben declarar su capacidad de ejecutarse en modo de compatibilidad usando la clase <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2c429-153">Service implementations must declare their ability to run in compatibility mode using the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> class.</span></span> <span data-ttu-id="2c429-154">Cuando el modo de compatibilidad está habilitado</span><span class="sxs-lookup"><span data-stu-id="2c429-154">When the compatibility mode is enabled,</span></span>  
  
- <span data-ttu-id="2c429-155">Se exige la autorización de dirección URL/archivo de ASP.NET antes que la autorización de WCF.</span><span class="sxs-lookup"><span data-stu-id="2c429-155">ASP.NET File/URL Authorization is enforced prior to WCF authorization.</span></span> <span data-ttu-id="2c429-156">Una decisión de autorización se basa en la identidad a nivel de transporte de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2c429-156">An authorization decision is based on the transport-level identity of the request.</span></span> <span data-ttu-id="2c429-157">Se omiten las identidades a nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c429-157">Identities at the message level are ignored.</span></span>  
  
- <span data-ttu-id="2c429-158">Las operaciones del servicio WCF empiezan a ejecutarse en el contexto de suplantación de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2c429-158">WCF service operations start to execute in the ASP.NET impersonation context.</span></span> <span data-ttu-id="2c429-159">Si la suplantación de ASP.NET y la suplantación de WCF están habilitadas para un servicio concreto, se aplica el contexto de suplantación de WCF.</span><span class="sxs-lookup"><span data-stu-id="2c429-159">If both ASP.NET impersonation and WCF impersonation are enabled for a specific service, the WCF impersonation context applies.</span></span>  
  
- <span data-ttu-id="2c429-160">HttpContext.Current se puede usar del código del servicio WCF y se evita que los servicios expongan los puntos de conexión que no son HTTP.</span><span class="sxs-lookup"><span data-stu-id="2c429-160">HttpContext.Current can be used from WCF service code, and services are prevented from exposing non-HTTP endpoints.</span></span>  
  
- <span data-ttu-id="2c429-161">La canalización de ASP.NET procesa las solicitudes de WCF.</span><span class="sxs-lookup"><span data-stu-id="2c429-161">WCF requests are processed by the ASP.NET pipeline.</span></span> <span data-ttu-id="2c429-162">HttpModules que se ha configurado para actuar en solicitudes entrante también puede procesar las solicitudes de WCF.</span><span class="sxs-lookup"><span data-stu-id="2c429-162">HttpModules that have been configured to act on incoming requests can also process WCF requests.</span></span> <span data-ttu-id="2c429-163">Éstas pueden incluir componentes de plataforma de ASP.NET (por ejemplo, <xref:System.Web.SessionState.SessionStateModule>), y también módulos personalizados de terceros.</span><span class="sxs-lookup"><span data-stu-id="2c429-163">These can include ASP.NET platform components (e.g., <xref:System.Web.SessionState.SessionStateModule>), as well as custom third party modules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c429-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c429-164">Example</span></span>  

 <span data-ttu-id="2c429-165">El ejemplo de código siguiente muestra cómo habilitar el modo de compatibilidad de ASP.</span><span class="sxs-lookup"><span data-stu-id="2c429-165">The following code sample shows how to enable ASP Compatibility Mode.</span></span>  
  
## <a name="code"></a><span data-ttu-id="2c429-166">Código</span><span class="sxs-lookup"><span data-stu-id="2c429-166">Code</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
```  
  
## <a name="see-also"></a><span data-ttu-id="2c429-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c429-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="2c429-168">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="2c429-168">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
- [<span data-ttu-id="2c429-169">Servicios WCF y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2c429-169">WCF Services and ASP.NET</span></span>](../../../wcf/feature-details/wcf-services-and-aspnet.md)
