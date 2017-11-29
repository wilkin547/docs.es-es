---
title: '&lt;serviceMetadata&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a771b3b89c9031a011185a579e70767081d20597
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicemetadatagt"></a><span data-ttu-id="d84c2-102">&lt;serviceMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="d84c2-102">&lt;serviceMetadata&gt;</span></span>
<span data-ttu-id="d84c2-103">Especifica la publicación de metadatos e información asociada del servicio.</span><span class="sxs-lookup"><span data-stu-id="d84c2-103">Specifies the publication of service metadata and associated information.</span></span>  
  
<span data-ttu-id="d84c2-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d84c2-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d84c2-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="d84c2-105">\<behaviors></span></span>  
<span data-ttu-id="d84c2-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d84c2-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d84c2-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d84c2-107">\<behavior></span></span>  
<span data-ttu-id="d84c2-108">\<serviceMetadata ></span><span class="sxs-lookup"><span data-stu-id="d84c2-108">\<serviceMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d84c2-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d84c2-109">Syntax</span></span>  
  
```xml
<serviceMetadata externalMetadataLocation="String"  
                 httpGetBinding="String" 
                 httpGetBindingConfiguration="String"  
                 httpGetEnabled="Boolean" 
                 httpGetUrl="String" 
                 httpsGetBinding="String" 
                 httpsGetBindingConfiguration="String"  
                 httpsGetEnabled="Boolean"   
                 httpsGetUrl="String"  
                 policyVersion="Policy12/Policy15" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d84c2-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d84c2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d84c2-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d84c2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d84c2-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d84c2-112">Attributes</span></span>  
  
|<span data-ttu-id="d84c2-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="d84c2-113">Attribute</span></span>|<span data-ttu-id="d84c2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d84c2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d84c2-115">externalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="d84c2-115">externalMetadataLocation</span></span>|<span data-ttu-id="d84c2-116">Un URI que contiene la ubicación de un archivo WSDL que se devuelve al usuario en respuesta a las solicitudes WSDL y MEX en lugar del WSDL generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d84c2-116">A Uri that contains the location of a WSDL file, which is returned to the user in response to WSDL and MEX requests instead of the auto-generated WSDL.</span></span> <span data-ttu-id="d84c2-117">Cuando no se establece este atributo, se devuelve el WSDL predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d84c2-117">When this attribute is not set, the default WSDL is returned.</span></span> <span data-ttu-id="d84c2-118">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="d84c2-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="d84c2-119">httpGetBinding</span><span class="sxs-lookup"><span data-stu-id="d84c2-119">httpGetBinding</span></span>|<span data-ttu-id="d84c2-120">Cadena que especifica el tipo de enlace que se usará para la recuperación de metadatos a través de HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="d84c2-120">A string that specifies the type of the binding that will be used for metadata retrieval via HTTP GET.</span></span> <span data-ttu-id="d84c2-121">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="d84c2-121">This setting is optional.</span></span> <span data-ttu-id="d84c2-122">Si no se especifica, se usarán los enlaces predeterminados.</span><span class="sxs-lookup"><span data-stu-id="d84c2-122">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="d84c2-123">Solo se admitirán los enlaces con elementos de enlace internos que admiten <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="d84c2-123">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="d84c2-124">Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="d84c2-124">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="d84c2-125">httpGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d84c2-125">httpGetBindingConfiguration</span></span>|<span data-ttu-id="d84c2-126">Cadena que establece el nombre del enlace que se especifica en el atributo `httpGetBinding`, que hace referencia a la información de configuración adicional de este enlace.</span><span class="sxs-lookup"><span data-stu-id="d84c2-126">A string that sets the name of the binding that is specified in the `httpGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="d84c2-127">El mismo nombre se debe definir en la sección `<bindings>`.</span><span class="sxs-lookup"><span data-stu-id="d84c2-127">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="d84c2-128">httpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="d84c2-128">httpGetEnabled</span></span>|<span data-ttu-id="d84c2-129">Un valor boolenao que especifica si publicar los metadatos del servicio para la recuperación utilizando un HTTP/Obtener solicitud.</span><span class="sxs-lookup"><span data-stu-id="d84c2-129">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="d84c2-130">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="d84c2-130">The default is `false`.</span></span><br /><br /> <span data-ttu-id="d84c2-131">Si no se especifica el atributo httpGetUrl, la dirección en la que se publican los metadatos es la dirección de servicio más un "? wsdl."</span><span class="sxs-lookup"><span data-stu-id="d84c2-131">If the httpGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="d84c2-132">Por ejemplo, si la dirección de servicio es "http://localhost:8080/CalculatorService", la dirección de los metadatos de HTTP/Get es "http://localhost:8080/CalculatorService?wsdl."</span><span class="sxs-lookup"><span data-stu-id="d84c2-132">For example, if the service address is "http://localhost:8080/CalculatorService", the HTTP/Get metadata address is "http://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="d84c2-133">Si esta propiedad es `false`, o la dirección del servicio no se basa en HTTP o HTTPS, "? wsdl" se omite.</span><span class="sxs-lookup"><span data-stu-id="d84c2-133">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="d84c2-134">httpGetUrl</span><span class="sxs-lookup"><span data-stu-id="d84c2-134">httpGetUrl</span></span>|<span data-ttu-id="d84c2-135">URI que especifica la dirección en la que se publican los metadatos para la recuperación mediante una solicitud HTTP/Get.</span><span class="sxs-lookup"><span data-stu-id="d84c2-135">A Uri that specifies the address at which the metadata is published for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="d84c2-136">Si se especifica un URI relativo, se tratará como relativo a la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="d84c2-136">If a relative Uri is specified it will be treated as relative to the service’s base address.</span></span>|  
|<span data-ttu-id="d84c2-137">httpsGetBinding</span><span class="sxs-lookup"><span data-stu-id="d84c2-137">httpsGetBinding</span></span>|<span data-ttu-id="d84c2-138">Cadena que especifica el tipo de enlace que se usará para la recuperación de metadatos a través de HTTPS GET.</span><span class="sxs-lookup"><span data-stu-id="d84c2-138">A string that specifies the type of the binding that will be used for metadata retrieval via HTTPS GET.</span></span> <span data-ttu-id="d84c2-139">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="d84c2-139">This setting is optional.</span></span> <span data-ttu-id="d84c2-140">Si no se especifica, se usarán los enlaces predeterminados.</span><span class="sxs-lookup"><span data-stu-id="d84c2-140">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="d84c2-141">Solo se admitirán los enlaces con elementos de enlace internos que admiten <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="d84c2-141">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="d84c2-142">Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="d84c2-142">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="d84c2-143">httpsGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d84c2-143">httpsGetBindingConfiguration</span></span>|<span data-ttu-id="d84c2-144">Cadena que establece el nombre del enlace que se especifica en el atributo `httpsGetBinding`, que hace referencia a la información de configuración adicional de este enlace.</span><span class="sxs-lookup"><span data-stu-id="d84c2-144">A string that sets the name of the binding that is specified in the `httpsGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="d84c2-145">El mismo nombre se debe definir en la sección `<bindings>`.</span><span class="sxs-lookup"><span data-stu-id="d84c2-145">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="d84c2-146">httpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="d84c2-146">httpsGetEnabled</span></span>|<span data-ttu-id="d84c2-147">Un valor boolenao que especifica si se van a publicar los metadatos del servicio para la recuperación mediante una solicitud HTTP/Get.</span><span class="sxs-lookup"><span data-stu-id="d84c2-147">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTPS/Get request.</span></span> <span data-ttu-id="d84c2-148">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="d84c2-148">The default is `false`.</span></span><br /><br /> <span data-ttu-id="d84c2-149">Si no se especifica el atributo httpsGetUrl, la dirección en la que se publican los metadatos es la dirección de servicio más un "? wsdl."</span><span class="sxs-lookup"><span data-stu-id="d84c2-149">If the httpsGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="d84c2-150">Por ejemplo, si la dirección de servicio es "https://localhost:8080/CalculatorService", la dirección de los metadatos de HTTP/Get es "https://localhost:8080/CalculatorService?wsdl."</span><span class="sxs-lookup"><span data-stu-id="d84c2-150">For example, if the service address is "https://localhost:8080/CalculatorService", the HTTP/Get metadata address is "https://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="d84c2-151">Si esta propiedad es `false`, o la dirección del servicio no se basa en HTTP o HTTPS, "? wsdl" se omite.</span><span class="sxs-lookup"><span data-stu-id="d84c2-151">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="d84c2-152">httpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="d84c2-152">httpsGetUrl</span></span>|<span data-ttu-id="d84c2-153">URI que especifica la dirección en la que se publican los metadatos para la recuperación mediante una solicitud HTTPS/Get.</span><span class="sxs-lookup"><span data-stu-id="d84c2-153">A Uri that specifies the address at which the metadata is published for retrieval using an HTTPS/Get request.</span></span>|  
|<span data-ttu-id="d84c2-154">policyVersion</span><span class="sxs-lookup"><span data-stu-id="d84c2-154">policyVersion</span></span>|<span data-ttu-id="d84c2-155">Una cadena que especifica la versión de la especificación WS-Policy que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="d84c2-155">A string that specifies the version of the WS-Policy specification being used.</span></span> <span data-ttu-id="d84c2-156">Este atributo es del tipo <xref:System.ServiceModel.Description.PolicyVersion>.</span><span class="sxs-lookup"><span data-stu-id="d84c2-156">This attribute is of type <xref:System.ServiceModel.Description.PolicyVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d84c2-157">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d84c2-157">Child Elements</span></span>  
 <span data-ttu-id="d84c2-158">Ninguna</span><span class="sxs-lookup"><span data-stu-id="d84c2-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d84c2-159">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d84c2-159">Parent Elements</span></span>  
  
|<span data-ttu-id="d84c2-160">Elemento</span><span class="sxs-lookup"><span data-stu-id="d84c2-160">Element</span></span>|<span data-ttu-id="d84c2-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="d84c2-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d84c2-162">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d84c2-162">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d84c2-163">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d84c2-163">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d84c2-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d84c2-164">Remarks</span></span>  
 <span data-ttu-id="d84c2-165">Este elemento de configuración permite controlar los metadatos que publican características de un servicio.</span><span class="sxs-lookup"><span data-stu-id="d84c2-165">This configuration element allows you to control the metadata publishing features of a service.</span></span> <span data-ttu-id="d84c2-166">Para evitar la divulgación involuntaria de metadatos de servicio con información confidencial potencial, la configuración predeterminada para los servicios [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] deshabilita la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="d84c2-166">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services disables metadata publishing.</span></span> <span data-ttu-id="d84c2-167">Este comportamiento es seguro de forma predeterminada, pero también quiere decir que no puede usar una herramienta de importación de metadatos (como Svcutil.exe) Para compilar el código de cliente necesario para llamar al servicio a menos que el comportamiento de publicación de metadatos del servicio se habilite de manera explícita en la configuración.</span><span class="sxs-lookup"><span data-stu-id="d84c2-167">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="d84c2-168">Con este elemento de configuración, puede habilitar este comportamiento de publicación para su servicio.</span><span class="sxs-lookup"><span data-stu-id="d84c2-168">Using this configuration element, you can enable this publishing behavior for your service.</span></span>  
  
 <span data-ttu-id="d84c2-169">Para obtener un ejemplo detallado de la configuración de este comportamiento, consulte [comportamiento de publicación de metadatos](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="d84c2-169">For a detailed example of configuring this behavior, see [Metadata Publishing Behavior](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).</span></span>  
  
 <span data-ttu-id="d84c2-170">Los atributos `httpGetBinding` y `httpsGetBinding` opcionales le permiten configurar los enlaces utilizados para la recuperación de metadatos a través de HTTP GET (o HTTPS GET).</span><span class="sxs-lookup"><span data-stu-id="d84c2-170">The optional `httpGetBinding` and `httpsGetBinding` attributes allow you to configure the bindings used for metadata retrieval via HTTP GET (or HTTPS GET).</span></span> <span data-ttu-id="d84c2-171">Si no se especifican, los enlaces predeterminados (`HttpTransportBindingElement`, en el caso de HTTP y `HttpsTransportBindingElement`, en el caso de HTTPS) se utilizan según corresponda para la recuperación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="d84c2-171">If they are not specified, the default bindings (`HttpTransportBindingElement`, in the case of HTTP and `HttpsTransportBindingElement`, in the case of HTTPS) are used for metadata retrieval as appropriate.</span></span> <span data-ttu-id="d84c2-172">Observe que no puede utilizar estos atributos con los enlaces WCF integrados.</span><span class="sxs-lookup"><span data-stu-id="d84c2-172">Notice that you cannot use these attributes with the built-in WCF bindings.</span></span> <span data-ttu-id="d84c2-173">Solo se admitirán los enlaces con elementos de enlace internos que admiten <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="d84c2-173">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="d84c2-174">Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="d84c2-174">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="d84c2-175">Para reducir la exposición de un servicio a los usuarios malintencionados, es posible proteger la transferencia mediante el mecanismo SSL sobre HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="d84c2-175">To reduce the exposure of a service to malicious users, it is possible to secure the transfer using the SSL over HTTP (HTTPS) mechanism.</span></span> <span data-ttu-id="d84c2-176">Para realizar esto, debe enlazar primero un certificado X.509 adecuado a un puerto concreto en el equipo que esté hospedando el servicio.</span><span class="sxs-lookup"><span data-stu-id="d84c2-176">To do so, you must first bind a suitable X.509 certificate to a specific port on the computer that is hosting the service.</span></span> <span data-ttu-id="d84c2-177">([!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Segundo, agregue este elemento a la configuración de servicio y establezca el atributo `httpsGetEnabled` en `true`.</span><span class="sxs-lookup"><span data-stu-id="d84c2-177">([!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Second, add this element to the service configuration and set the `httpsGetEnabled` attribute to `true`.</span></span> <span data-ttu-id="d84c2-178">Finalmente, establezca el atributo `httpsGetUrl` en la dirección URL del extremo de metadatos del servicio, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d84c2-178">Finally, set the `httpsGetUrl` attribute to the URL of the service metadata endpoint, as shown in the following example.</span></span>  
  
```xml
<behaviors>  
  <serviceBehaviors>  
    <behavior name="NewBehavior">  
      <serviceMetadata httpsGetEnabled="true"   
                       httpsGetUrl="https://myComputerName/myEndpoint" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="example"></a><span data-ttu-id="d84c2-179">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d84c2-179">Example</span></span>  
 <span data-ttu-id="d84c2-180">El ejemplo siguiente configura un servicio para exponer metadatos utilizando la \<serviceMetadata > elemento.</span><span class="sxs-lookup"><span data-stu-id="d84c2-180">The following example configure a service to expose metadata by using the \<serviceMetadata> element.</span></span> <span data-ttu-id="d84c2-181">También configura un extremo para exponer el contrato `IMetadataExchange` como una implementación de un protocolo WS-MetadataExchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="d84c2-181">It also configures an endpoint to expose the `IMetadataExchange` contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="d84c2-182">El ejemplo usa `mexHttpBinding`, que es un enlace estándar de conveniencia equivalente a `wsHttpBinding` con el modo de seguridad establecido en `None`.</span><span class="sxs-lookup"><span data-stu-id="d84c2-182">The example uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="d84c2-183">Se utiliza una dirección relativa de "mex" en el punto de conexión que, cuando se resuelve con los resultados de la dirección base de los servicios resulta en una dirección de punto de conexión de http://localhost/servicemodelsamples/service.svc/mex.</span><span class="sxs-lookup"><span data-stu-id="d84c2-183">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of http://localhost/servicemodelsamples/service.svc/mex.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService" 
               behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex   
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <!-- The serviceMetadata behavior publishes metadata through   
               the IMetadataExchange contract. When this behavior is   
               present, you can expose this contract through an endpoint   
               as shown above. Setting httpGetEnabled to true publishes   
               the service's WSDL at the <baseaddress>?wsdl  
               eg. http://localhost/servicemodelsamples/service.svc?wsdl -->  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d84c2-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="d84c2-184">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 [<span data-ttu-id="d84c2-185">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="d84c2-185">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="d84c2-186">Metadatos que publican el comportamiento</span><span class="sxs-lookup"><span data-stu-id="d84c2-186">Metadata Publishing Behavior</span></span>](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
