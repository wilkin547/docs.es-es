---
title: '&lt;serviceHostingEnvironment&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e3951c52a5bc510cc288b1289f2f6cc9c39255db
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicehostingenvironmentgt"></a><span data-ttu-id="65a3f-102">&lt;serviceHostingEnvironment&gt;</span><span class="sxs-lookup"><span data-stu-id="65a3f-102">&lt;serviceHostingEnvironment&gt;</span></span>
<span data-ttu-id="65a3f-103">Este elemento define el tipo en el que el entorno de hospedaje de servicio crea instancias de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="65a3f-103">This element defines the type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="65a3f-104">Si este elemento está vacío, se usa el tipo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="65a3f-104">If this element is empty, the default type is used.</span></span> <span data-ttu-id="65a3f-105">Este elemento solo se puede usar en los archivos de configuración del nivel de aplicación o equipo.</span><span class="sxs-lookup"><span data-stu-id="65a3f-105">This element can only be used at the application or machine level configuration files.</span></span>  
  
 <span data-ttu-id="65a3f-106">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="65a3f-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="65a3f-107">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="65a3f-107">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a3f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65a3f-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean" 
                           minFreeMemoryPercentageToActivateService="Integer" 
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String" service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String" transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65a3f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="65a3f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="65a3f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="65a3f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65a3f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="65a3f-111">Attributes</span></span>  
  
|<span data-ttu-id="65a3f-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="65a3f-112">Attribute</span></span>|<span data-ttu-id="65a3f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="65a3f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65a3f-114">aspNetCompatibilityEnabled</span><span class="sxs-lookup"><span data-stu-id="65a3f-114">aspNetCompatibilityEnabled</span></span>|<span data-ttu-id="65a3f-115">Un valor booleano que indica si se ha activado el modo de compatibilidad de ASP.NET para la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="65a3f-115">A Boolean value indicating whether the ASP.NET compatibility mode has been turned on for the current application.</span></span> <span data-ttu-id="65a3f-116">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="65a3f-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="65a3f-117">Cuando este atributo se establece en `true`, solicita flujo de servicios a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] a través de la canalización HTTP de ASP.NET y se prohíbe la comunicación a través de los protocolos que no son HTTP.</span><span class="sxs-lookup"><span data-stu-id="65a3f-117">When this attribute is set to `true`, requests to [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services flow through the ASP.NET HTTP pipeline, and communication over non-HTTP protocols is prohibited.</span></span> <span data-ttu-id="65a3f-118">Para obtener más información, consulte [servicios WCF y ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="65a3f-118">For more information, see [WCF Services and ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span>|  
|<span data-ttu-id="65a3f-119">minFreeMemoryPercentageToActivateService</span><span class="sxs-lookup"><span data-stu-id="65a3f-119">minFreeMemoryPercentageToActivateService</span></span>|<span data-ttu-id="65a3f-120">Un entero que especifica la cantidad mínima de memoria libre que debería tener disponible el sistema antes de que se pueda activar un servicio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65a3f-120">An integer that specifies the minimum amount of free memory that should be available to the system, before a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service can be activated.</span></span> <span data-ttu-id="65a3f-121">**Precaución:** especificar este atributo junto con confianza parcial en el archivo web.config de un [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] servicio dará como resultado un <xref:System.Security.SecurityException> cuando se ejecuta el servicio.</span><span class="sxs-lookup"><span data-stu-id="65a3f-121">**Caution:**  Specifying this attribute along with partial trust in the web.config file of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service will result in a <xref:System.Security.SecurityException> when the service is run.</span></span>|  
|<span data-ttu-id="65a3f-122">multipleSiteBindingsEnabled</span><span class="sxs-lookup"><span data-stu-id="65a3f-122">multipleSiteBindingsEnabled</span></span>|<span data-ttu-id="65a3f-123">Valor booleano que especifica si están habilitados varios enlaces de IIS por sitio.</span><span class="sxs-lookup"><span data-stu-id="65a3f-123">A Boolean value that specifies whether multiple IIS bindings per site is enabled.</span></span><br /><br /> <span data-ttu-id="65a3f-124">IIS se compone de sitios web, que son contenedores de aplicaciones virtuales que contienen directorios virtuales.</span><span class="sxs-lookup"><span data-stu-id="65a3f-124">IIS consists of web sites, which are containers for virtual applications containing virtual directories.</span></span> <span data-ttu-id="65a3f-125">Se puede tener acceso a la aplicación de un sitio a través de uno o varios enlaces de IIS.</span><span class="sxs-lookup"><span data-stu-id="65a3f-125">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="65a3f-126">Un enlace de IIS proporciona dos piezas de información: un protocolo de enlace e información de enlace.</span><span class="sxs-lookup"><span data-stu-id="65a3f-126">An IIS binding provides two pieces of information: a binding protocol and binding information.</span></span> <span data-ttu-id="65a3f-127">El protocolo de enlace define el esquema sobre el que se produce la comunicación, y la información de enlace es la información usada para tener acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="65a3f-127">Binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span> <span data-ttu-id="65a3f-128">Un ejemplo de un protocolo de enlace puede ser HTTP, mientras que la información de enlace puede contener una dirección IP, un puerto, un encabezado de host, etc.</span><span class="sxs-lookup"><span data-stu-id="65a3f-128">An example of a binding protocol can be HTTP, whereas binding information can contain an IP address, Port, host header, etc.</span></span><br /><br /> <span data-ttu-id="65a3f-129">IIS permite especificar varios enlaces de IIS por sitio, lo que genera varias direcciones base por esquema.</span><span class="sxs-lookup"><span data-stu-id="65a3f-129">IIS supports specifying multiple IIS bindings per site, which results in multiple base addresses per scheme.</span></span> <span data-ttu-id="65a3f-130">Sin embargo, un servicio de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] hospedado en un sitio permite enlazar únicamente a una baseAddress por esquema.</span><span class="sxs-lookup"><span data-stu-id="65a3f-130">However, a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service hosted under a site allows binding to only one baseAddress per scheme.</span></span><br /><br /> <span data-ttu-id="65a3f-131">Para habilitar varios enlaces de IIS por sitio para un servicio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], establezca este atributo en `true`.</span><span class="sxs-lookup"><span data-stu-id="65a3f-131">To enable multiple IIS bindings per site for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service, set this attribute to `true`.</span></span> <span data-ttu-id="65a3f-132">Observe que solo se admiten varios enlaces del sitio para el protocolo HTTP.</span><span class="sxs-lookup"><span data-stu-id="65a3f-132">Notice that multiple site binding is supported only for the HTTP protocol.</span></span> <span data-ttu-id="65a3f-133">La dirección de puntos de conexión en el archivo de configuración tiene que ser un URI completo.</span><span class="sxs-lookup"><span data-stu-id="65a3f-133">The address of endpoints in the configuration file needs to be a complete URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65a3f-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="65a3f-134">Child Elements</span></span>  
  
|<span data-ttu-id="65a3f-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="65a3f-135">Element</span></span>|<span data-ttu-id="65a3f-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="65a3f-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65a3f-137">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="65a3f-137">\<baseAddressPrefixFilters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|<span data-ttu-id="65a3f-138">Una colección de elementos de configuración que especifican los filtros de prefijo de las direcciones base usadas por el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="65a3f-138">A collection of configuration elements that specify prefix filters for the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="65a3f-139">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="65a3f-139">\<serviceActivations></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceactivations.md)|<span data-ttu-id="65a3f-140">Sección de configuración que describe la configuración de activación.</span><span class="sxs-lookup"><span data-stu-id="65a3f-140">A configuration section that describes activation settings.</span></span>|  
|[<span data-ttu-id="65a3f-141">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="65a3f-141">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="65a3f-142">Una colección de elementos de configuración que identifican el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="65a3f-142">A collection of configuration elements that identify the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65a3f-143">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="65a3f-143">Parent Elements</span></span>  
  
|<span data-ttu-id="65a3f-144">Elemento</span><span class="sxs-lookup"><span data-stu-id="65a3f-144">Element</span></span>|<span data-ttu-id="65a3f-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="65a3f-145">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65a3f-146">serviceModel</span><span class="sxs-lookup"><span data-stu-id="65a3f-146">serviceModel</span></span>|<span data-ttu-id="65a3f-147">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="65a3f-147">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65a3f-148">Comentarios</span><span class="sxs-lookup"><span data-stu-id="65a3f-148">Remarks</span></span>  
 <span data-ttu-id="65a3f-149">De forma predeterminada, los servicios WCF se ejecutan en paralelo con ASP.NET en dominios de aplicación hospedados (AppDomain).</span><span class="sxs-lookup"><span data-stu-id="65a3f-149">By default, WCF services run side-by-side with ASP.NET in hosted Application Domains (AppDomain).</span></span> <span data-ttu-id="65a3f-150">Aunque WCF y ASP.NET pueden coexistir en el mismo AppDomain, la canalización de HTTP de ASP.NET no procesa de forma predeterminada las solicitudes de WCF.</span><span class="sxs-lookup"><span data-stu-id="65a3f-150">Even though WCF and ASP.NET can coexist in the same AppDomain, WCF requests are not processed by the ASP.NET HTTP Pipeline by default.</span></span> <span data-ttu-id="65a3f-151">Como resultado, varios elementos de la plataforma de la aplicación ASP.NET no están disponibles para los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="65a3f-151">As a result, several elements of the ASP.NET application platform are not available to WCF services.</span></span> <span data-ttu-id="65a3f-152">Éstos incluyen:</span><span class="sxs-lookup"><span data-stu-id="65a3f-152">These include</span></span>  
  
-   <span data-ttu-id="65a3f-153">Autorización de dirección URL/archivo de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="65a3f-153">ASP.NET File/URL Authorization</span></span>  
  
-   <span data-ttu-id="65a3f-154">Suplantación de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="65a3f-154">ASP.NET Impersonation</span></span>  
  
-   <span data-ttu-id="65a3f-155">Estado de sesión basado en cookies</span><span class="sxs-lookup"><span data-stu-id="65a3f-155">Cookie-based Session State</span></span>  
  
-   <span data-ttu-id="65a3f-156">HttpContext.Current</span><span class="sxs-lookup"><span data-stu-id="65a3f-156">HttpContext.Current</span></span>  
  
-   <span data-ttu-id="65a3f-157">Extensibilidad de la canalización a través de HttpModule personalizado</span><span class="sxs-lookup"><span data-stu-id="65a3f-157">Pipeline Extensibility via custom HttpModule</span></span>  
  
 <span data-ttu-id="65a3f-158">Si sus servicios WCF necesitan funcionar en el contexto de ASP.NET, y solo comunicarse sobre HTTP, puede usar el modo de compatibilidad de ASP.NET de WCF.</span><span class="sxs-lookup"><span data-stu-id="65a3f-158">If your WCF services need to function in the ASP.NET context, and communicate only over HTTP, you can use WCF’s ASP.NET compatibility mode.</span></span> <span data-ttu-id="65a3f-159">Este modo se activa cuando el atributo `aspNetCompatibilityEnabled` se establece en `true` en el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="65a3f-159">This mode is turned on when the `aspNetCompatibilityEnabled` attribute is set to `true` at the application level.</span></span> <span data-ttu-id="65a3f-160">Las implementaciones del servicio deben declarar su capacidad de ejecutarse en modo de compatibilidad usando la clase <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="65a3f-160">Service implementations must declare their ability to run in compatibility mode using the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> class.</span></span> <span data-ttu-id="65a3f-161">Cuando el modo de compatibilidad está habilitado</span><span class="sxs-lookup"><span data-stu-id="65a3f-161">When the compatibility mode is enabled,</span></span>  
  
-   <span data-ttu-id="65a3f-162">Se exige la autorización de dirección URL/archivo de ASP.NET antes que la autorización de WCF.</span><span class="sxs-lookup"><span data-stu-id="65a3f-162">ASP.NET File/URL Authorization is enforced prior to WCF authorization.</span></span> <span data-ttu-id="65a3f-163">Una decisión de autorización se basa en la identidad a nivel de transporte de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="65a3f-163">An authorization decision is based on the transport-level identity of the request.</span></span> <span data-ttu-id="65a3f-164">Se omiten las identidades a nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="65a3f-164">Identities at the message level are ignored.</span></span>  
  
-   <span data-ttu-id="65a3f-165">Las operaciones del servicio WCF empiezan a ejecutarse en el contexto de suplantación de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="65a3f-165">WCF service operations start to execute in the ASP.NET impersonation context.</span></span> <span data-ttu-id="65a3f-166">Si la suplantación de ASP.NET y la suplantación de WCF están habilitadas para un servicio concreto, se aplica el contexto de suplantación de WCF.</span><span class="sxs-lookup"><span data-stu-id="65a3f-166">If both ASP.NET impersonation and WCF impersonation are enabled for a specific service, the WCF impersonation context applies.</span></span>  
  
-   <span data-ttu-id="65a3f-167">HttpContext.Current se puede usar del código del servicio WCF y se evita que los servicios expongan los extremos que no son HTTP.</span><span class="sxs-lookup"><span data-stu-id="65a3f-167">HttpContext.Current can be used from WCF service code, and services are prevented from exposing non-HTTP endpoints.</span></span>  
  
-   <span data-ttu-id="65a3f-168">La canalización de ASP.NET procesa las solicitudes de WCF.</span><span class="sxs-lookup"><span data-stu-id="65a3f-168">WCF requests are processed by the ASP.NET pipeline.</span></span> <span data-ttu-id="65a3f-169">HttpModules que se ha configurado para actuar en solicitudes entrante también puede procesar las solicitudes de WCF.</span><span class="sxs-lookup"><span data-stu-id="65a3f-169">HttpModules that have been configured to act on incoming requests can also process WCF requests.</span></span> <span data-ttu-id="65a3f-170">Éstas pueden incluir componentes de plataforma de ASP.NET (por ejemplo, <xref:System.Web.SessionState.SessionStateModule>), y también módulos personalizados de terceros.</span><span class="sxs-lookup"><span data-stu-id="65a3f-170">These can include ASP.NET platform components (e.g., <xref:System.Web.SessionState.SessionStateModule>), as well as custom third party modules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65a3f-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="65a3f-171">Example</span></span>  
 <span data-ttu-id="65a3f-172">El ejemplo de código siguiente muestra cómo habilitar el modo de compatibilidad de ASP.</span><span class="sxs-lookup"><span data-stu-id="65a3f-172">The following code sample shows how to enable ASP Compatibility Mode.</span></span>  
  
## <a name="code"></a><span data-ttu-id="65a3f-173">Código</span><span class="sxs-lookup"><span data-stu-id="65a3f-173">Code</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="65a3f-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="65a3f-174">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="65a3f-175">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="65a3f-175">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="65a3f-176">Servicios WCF y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="65a3f-176">WCF Services and ASP.NET</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
