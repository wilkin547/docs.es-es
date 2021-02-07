---
description: 'Más información acerca de: <serviceMetadata>'
title: <serviceMetadata>
ms.date: 03/30/2017
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
ms.openlocfilehash: b519de04c333f9ddc12de72757587c9b38f29dba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682831"
---
# \<serviceMetadata>

<span data-ttu-id="9aa48-102">Especifica la publicación de metadatos e información asociada del servicio.</span><span class="sxs-lookup"><span data-stu-id="9aa48-102">Specifies the publication of service metadata and associated information.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="9aa48-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9aa48-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9aa48-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9aa48-104">Attributes and Elements</span></span>  

 <span data-ttu-id="9aa48-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9aa48-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9aa48-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="9aa48-106">Attributes</span></span>  
  
|<span data-ttu-id="9aa48-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="9aa48-107">Attribute</span></span>|<span data-ttu-id="9aa48-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9aa48-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9aa48-109">externalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="9aa48-109">externalMetadataLocation</span></span>|<span data-ttu-id="9aa48-110">Un URI que contiene la ubicación de un archivo WSDL que se devuelve al usuario en respuesta a las solicitudes WSDL y MEX en lugar del WSDL generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9aa48-110">A Uri that contains the location of a WSDL file, which is returned to the user in response to WSDL and MEX requests instead of the auto-generated WSDL.</span></span> <span data-ttu-id="9aa48-111">Cuando no se establece este atributo, se devuelve el WSDL predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9aa48-111">When this attribute is not set, the default WSDL is returned.</span></span> <span data-ttu-id="9aa48-112">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="9aa48-112">The default is an empty string.</span></span>|  
|<span data-ttu-id="9aa48-113">httpGetBinding</span><span class="sxs-lookup"><span data-stu-id="9aa48-113">httpGetBinding</span></span>|<span data-ttu-id="9aa48-114">Cadena que especifica el tipo de enlace que se usará para la recuperación de metadatos a través de HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="9aa48-114">A string that specifies the type of the binding that will be used for metadata retrieval via HTTP GET.</span></span> <span data-ttu-id="9aa48-115">Esta configuración es opcional.</span><span class="sxs-lookup"><span data-stu-id="9aa48-115">This setting is optional.</span></span> <span data-ttu-id="9aa48-116">Si no se especifica, se usarán los enlaces predeterminados.</span><span class="sxs-lookup"><span data-stu-id="9aa48-116">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="9aa48-117">Solo se admitirán los enlaces con elementos de enlace internos que admiten <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="9aa48-117">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="9aa48-118">Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="9aa48-118">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="9aa48-119">httpGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9aa48-119">httpGetBindingConfiguration</span></span>|<span data-ttu-id="9aa48-120">Cadena que establece el nombre del enlace que se especifica en el atributo `httpGetBinding`, que hace referencia a la información de configuración adicional de este enlace.</span><span class="sxs-lookup"><span data-stu-id="9aa48-120">A string that sets the name of the binding that is specified in the `httpGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="9aa48-121">El mismo nombre se debe definir en la sección `<bindings>`.</span><span class="sxs-lookup"><span data-stu-id="9aa48-121">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="9aa48-122">httpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="9aa48-122">httpGetEnabled</span></span>|<span data-ttu-id="9aa48-123">Un valor boolenao que especifica si publicar los metadatos del servicio para la recuperación utilizando un HTTP/Obtener solicitud.</span><span class="sxs-lookup"><span data-stu-id="9aa48-123">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="9aa48-124">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="9aa48-124">The default is `false`.</span></span><br /><br /> <span data-ttu-id="9aa48-125">Si no se especifica el atributo httpGetUrl, la dirección en la que se publican los metadatos es la dirección de servicio más un "? wsdl."</span><span class="sxs-lookup"><span data-stu-id="9aa48-125">If the httpGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="9aa48-126">Por ejemplo, si la dirección del servicio es `http://localhost:8080/CalculatorService` , la dirección de los metadatos de http/get es `http://localhost:8080/CalculatorService?wsdl` .</span><span class="sxs-lookup"><span data-stu-id="9aa48-126">For example, if the service address is `http://localhost:8080/CalculatorService`, the HTTP/Get metadata address is `http://localhost:8080/CalculatorService?wsdl`.</span></span><br /><br /> <span data-ttu-id="9aa48-127">Si esta propiedad es `false` , o la dirección del servicio no se basa en http o https, "? WSDL" se omite.</span><span class="sxs-lookup"><span data-stu-id="9aa48-127">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="9aa48-128">httpGetUrl</span><span class="sxs-lookup"><span data-stu-id="9aa48-128">httpGetUrl</span></span>|<span data-ttu-id="9aa48-129">URI que especifica la dirección en la que se publican los metadatos para la recuperación mediante una solicitud HTTP/Get.</span><span class="sxs-lookup"><span data-stu-id="9aa48-129">A Uri that specifies the address at which the metadata is published for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="9aa48-130">Si se especifica un URI relativo, se tratará como relativo a la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="9aa48-130">If a relative Uri is specified it will be treated as relative to the service’s base address.</span></span>|  
|<span data-ttu-id="9aa48-131">httpsGetBinding</span><span class="sxs-lookup"><span data-stu-id="9aa48-131">httpsGetBinding</span></span>|<span data-ttu-id="9aa48-132">Cadena que especifica el tipo de enlace que se usará para la recuperación de metadatos a través de HTTPS GET.</span><span class="sxs-lookup"><span data-stu-id="9aa48-132">A string that specifies the type of the binding that will be used for metadata retrieval via HTTPS GET.</span></span> <span data-ttu-id="9aa48-133">Esta configuración es opcional.</span><span class="sxs-lookup"><span data-stu-id="9aa48-133">This setting is optional.</span></span> <span data-ttu-id="9aa48-134">Si no se especifica, se usarán los enlaces predeterminados.</span><span class="sxs-lookup"><span data-stu-id="9aa48-134">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="9aa48-135">Solo se admitirán los enlaces con elementos de enlace internos que admiten <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="9aa48-135">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="9aa48-136">Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="9aa48-136">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="9aa48-137">httpsGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9aa48-137">httpsGetBindingConfiguration</span></span>|<span data-ttu-id="9aa48-138">Cadena que establece el nombre del enlace que se especifica en el atributo `httpsGetBinding`, que hace referencia a la información de configuración adicional de este enlace.</span><span class="sxs-lookup"><span data-stu-id="9aa48-138">A string that sets the name of the binding that is specified in the `httpsGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="9aa48-139">El mismo nombre se debe definir en la sección `<bindings>`.</span><span class="sxs-lookup"><span data-stu-id="9aa48-139">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="9aa48-140">httpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="9aa48-140">httpsGetEnabled</span></span>|<span data-ttu-id="9aa48-141">Un valor boolenao que especifica si se van a publicar los metadatos del servicio para la recuperación mediante una solicitud HTTP/Get.</span><span class="sxs-lookup"><span data-stu-id="9aa48-141">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTPS/Get request.</span></span> <span data-ttu-id="9aa48-142">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="9aa48-142">The default is `false`.</span></span><br /><br /> <span data-ttu-id="9aa48-143">Si no se especifica el atributo httpsGetUrl, la dirección en la que se publican los metadatos es la dirección de servicio más un "? wsdl."</span><span class="sxs-lookup"><span data-stu-id="9aa48-143">If the httpsGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="9aa48-144">Por ejemplo, si la dirección de servicio es " https://localhost:8080/CalculatorService ", la dirección de los metadatos de http/get es " https://localhost:8080/CalculatorService?wsdl ".</span><span class="sxs-lookup"><span data-stu-id="9aa48-144">For example, if the service address is "https://localhost:8080/CalculatorService", the HTTP/Get metadata address is "https://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="9aa48-145">Si esta propiedad es `false` , o la dirección del servicio no se basa en http o https, "? WSDL" se omite.</span><span class="sxs-lookup"><span data-stu-id="9aa48-145">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="9aa48-146">httpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="9aa48-146">httpsGetUrl</span></span>|<span data-ttu-id="9aa48-147">URI que especifica la dirección en la que se publican los metadatos para la recuperación mediante una solicitud HTTPS/Get.</span><span class="sxs-lookup"><span data-stu-id="9aa48-147">A Uri that specifies the address at which the metadata is published for retrieval using an HTTPS/Get request.</span></span>|  
|<span data-ttu-id="9aa48-148">policyVersion</span><span class="sxs-lookup"><span data-stu-id="9aa48-148">policyVersion</span></span>|<span data-ttu-id="9aa48-149">Una cadena que especifica la versión de la especificación WS-Policy que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9aa48-149">A string that specifies the version of the WS-Policy specification being used.</span></span> <span data-ttu-id="9aa48-150">Este atributo es del tipo <xref:System.ServiceModel.Description.PolicyVersion>.</span><span class="sxs-lookup"><span data-stu-id="9aa48-150">This attribute is of type <xref:System.ServiceModel.Description.PolicyVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9aa48-151">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9aa48-151">Child Elements</span></span>  

 <span data-ttu-id="9aa48-152">None</span><span class="sxs-lookup"><span data-stu-id="9aa48-152">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9aa48-153">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9aa48-153">Parent Elements</span></span>  
  
|<span data-ttu-id="9aa48-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="9aa48-154">Element</span></span>|<span data-ttu-id="9aa48-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="9aa48-155">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9aa48-156">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="9aa48-156">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9aa48-157">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9aa48-157">Remarks</span></span>  

 <span data-ttu-id="9aa48-158">Este elemento de configuración permite controlar los metadatos que publican características de un servicio.</span><span class="sxs-lookup"><span data-stu-id="9aa48-158">This configuration element allows you to control the metadata publishing features of a service.</span></span> <span data-ttu-id="9aa48-159">Para evitar la revelación involuntaria de metadatos de servicio potencialmente confidenciales, la configuración predeterminada de los servicios Windows Communication Foundation (WCF) deshabilita la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9aa48-159">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="9aa48-160">Este comportamiento es seguro de forma predeterminada, pero también quiere decir que no puede usar una herramienta de importación de metadatos (como Svcutil.exe) Para compilar el código de cliente necesario para llamar al servicio a menos que el comportamiento de publicación de metadatos del servicio se habilite de manera explícita en la configuración.</span><span class="sxs-lookup"><span data-stu-id="9aa48-160">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="9aa48-161">Con este elemento de configuración, puede habilitar este comportamiento de publicación para su servicio.</span><span class="sxs-lookup"><span data-stu-id="9aa48-161">Using this configuration element, you can enable this publishing behavior for your service.</span></span>  
  
 <span data-ttu-id="9aa48-162">Para obtener un ejemplo detallado de cómo configurar este comportamiento, vea [comportamiento de publicación de metadatos](../../../wcf/samples/metadata-publishing-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="9aa48-162">For a detailed example of configuring this behavior, see [Metadata Publishing Behavior](../../../wcf/samples/metadata-publishing-behavior.md).</span></span>  
  
 <span data-ttu-id="9aa48-163">Los atributos `httpGetBinding` y `httpsGetBinding` opcionales le permiten configurar los enlaces utilizados para la recuperación de metadatos a través de HTTP GET (o HTTPS GET).</span><span class="sxs-lookup"><span data-stu-id="9aa48-163">The optional `httpGetBinding` and `httpsGetBinding` attributes allow you to configure the bindings used for metadata retrieval via HTTP GET (or HTTPS GET).</span></span> <span data-ttu-id="9aa48-164">Si no se especifican, los enlaces predeterminados (`HttpTransportBindingElement`, en el caso de HTTP y `HttpsTransportBindingElement`, en el caso de HTTPS) se utilizan según corresponda para la recuperación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9aa48-164">If they are not specified, the default bindings (`HttpTransportBindingElement`, in the case of HTTP and `HttpsTransportBindingElement`, in the case of HTTPS) are used for metadata retrieval as appropriate.</span></span> <span data-ttu-id="9aa48-165">Observe que no puede utilizar estos atributos con los enlaces WCF integrados.</span><span class="sxs-lookup"><span data-stu-id="9aa48-165">Notice that you cannot use these attributes with the built-in WCF bindings.</span></span> <span data-ttu-id="9aa48-166">Solo se admitirán los enlaces con elementos de enlace internos que admiten <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="9aa48-166">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="9aa48-167">Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="9aa48-167">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="9aa48-168">Para reducir la exposición de un servicio a los usuarios malintencionados, es posible proteger la transferencia mediante el mecanismo SSL sobre HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="9aa48-168">To reduce the exposure of a service to malicious users, it is possible to secure the transfer using the SSL over HTTP (HTTPS) mechanism.</span></span> <span data-ttu-id="9aa48-169">Para realizar esto, debe enlazar primero un certificado X.509 adecuado a un puerto concreto en el equipo que esté hospedando el servicio.</span><span class="sxs-lookup"><span data-stu-id="9aa48-169">To do so, you must first bind a suitable X.509 certificate to a specific port on the computer that is hosting the service.</span></span> <span data-ttu-id="9aa48-170">(Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md)). En segundo lugar, agregue este elemento a la configuración del servicio y establezca el `httpsGetEnabled` atributo en `true` .</span><span class="sxs-lookup"><span data-stu-id="9aa48-170">(For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).) Second, add this element to the service configuration and set the `httpsGetEnabled` attribute to `true`.</span></span> <span data-ttu-id="9aa48-171">Finalmente, establezca el atributo `httpsGetUrl` en la dirección URL del punto de conexión de metadatos del servicio, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9aa48-171">Finally, set the `httpsGetUrl` attribute to the URL of the service metadata endpoint, as shown in the following example.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="9aa48-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9aa48-172">Example</span></span>  

 <span data-ttu-id="9aa48-173">En el ejemplo siguiente se configura un servicio para exponer los metadatos mediante el \<serviceMetadata> elemento.</span><span class="sxs-lookup"><span data-stu-id="9aa48-173">The following example configure a service to expose metadata by using the \<serviceMetadata> element.</span></span> <span data-ttu-id="9aa48-174">También configura un extremo para exponer el contrato `IMetadataExchange` como una implementación de un protocolo WS-MetadataExchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="9aa48-174">It also configures an endpoint to expose the `IMetadataExchange` contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="9aa48-175">El ejemplo usa `mexHttpBinding`, que es un enlace estándar de conveniencia equivalente a `wsHttpBinding` con el modo de seguridad establecido en `None`.</span><span class="sxs-lookup"><span data-stu-id="9aa48-175">The example uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="9aa48-176">Se utiliza una dirección relativa de "Mex" en el punto de conexión, que cuando se resuelve con la dirección base de los servicios, da como resultado una dirección de extremo de `http://localhost/servicemodelsamples/service.svc/mex` .</span><span class="sxs-lookup"><span data-stu-id="9aa48-176">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of `http://localhost/servicemodelsamples/service.svc/mex`.</span></span>  
  
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
          <!-- The serviceMetadata behavior publishes metadata through the IMetadataExchange contract. When this behavior is
               present, you can expose this contract through an endpoint as shown above. Setting httpGetEnabled to true publishes
               the service's WSDL at the <baseaddress>?wsdl eg. http://localhost/servicemodelsamples/service.svc?wsdl -->
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="9aa48-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="9aa48-177">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [<span data-ttu-id="9aa48-178">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="9aa48-178">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9aa48-179">Comportamiento de publicación de metadatos</span><span class="sxs-lookup"><span data-stu-id="9aa48-179">Metadata Publishing Behavior</span></span>](../../../wcf/samples/metadata-publishing-behavior.md)
