---
title: Configurar la detección en un archivo de configuración
ms.date: 03/30/2017
ms.assetid: b9884c11-8011-4763-bc2c-c526b80175d0
ms.openlocfilehash: b2e604f6168e4adff36bfb0c22861124743b358d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185332"
---
# <a name="configuring-discovery-in-a-configuration-file"></a><span data-ttu-id="cd08c-102">Configurar la detección en un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="cd08c-102">Configuring Discovery in a Configuration File</span></span>
<span data-ttu-id="cd08c-103">Hay cuatro grupos principales de configuración usados en la detección.</span><span class="sxs-lookup"><span data-stu-id="cd08c-103">There are four major groups of configuration settings used in discovery.</span></span> <span data-ttu-id="cd08c-104">Este tema describirá brevemente cada uno de ellos y mostrará ejemplos de cómo configurarlos.</span><span class="sxs-lookup"><span data-stu-id="cd08c-104">This topic will briefly describe each and show examples of how to configure them.</span></span> <span data-ttu-id="cd08c-105">Tras cada sección, se ofrece un vínculo a documentación más detallada sobre cada área.</span><span class="sxs-lookup"><span data-stu-id="cd08c-105">Following each section will be a link to more in-depth documentation about each area.</span></span>  
  
## <a name="behavior-configuration"></a><span data-ttu-id="cd08c-106">Configuración de comportamiento</span><span class="sxs-lookup"><span data-stu-id="cd08c-106">Behavior Configuration</span></span>  
 <span data-ttu-id="cd08c-107">La detección usa comportamientos de servicio y comportamientos de extremo.</span><span class="sxs-lookup"><span data-stu-id="cd08c-107">Discovery uses service behaviors and endpoint behaviors.</span></span> <span data-ttu-id="cd08c-108">El comportamiento <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> habilita la detección para todos los extremos de un servicio y le permite especificar los extremos del anuncio.</span><span class="sxs-lookup"><span data-stu-id="cd08c-108">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> behavior enables discovery for all of a service’s endpoints and allows you to specify announcement endpoints.</span></span>  <span data-ttu-id="cd08c-109">En el siguiente ejemplo, se muestra cómo agregar <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> y especificar un punto de conexión del anuncio.</span><span class="sxs-lookup"><span data-stu-id="cd08c-109">The following example shows how to add the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and specify an announcement endpoint.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="helloWorldServiceBehavior">  
          <serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
```  
  
 <span data-ttu-id="cd08c-110">Una vez especificado el comportamiento, `service` haga referencia a él desde un elemento> <como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd08c-110">Once you specify the behavior, reference it from a <`service`> element as shown in the following sample.</span></span>  
  
```xml  
<system.serviceModel>  
   <services>  
      <service name="HelloWorldService" behaviorConfiguration="helloWorldServiceBehavior">  
         <!-- Application Endpoint -->  
         <endpoint address="endpoint0"  
                   binding="basicHttpBinding"  
                   contract="IHelloWorldService" />  
         <!-- Discovery Endpoints -->  
         <endpoint kind="udpDiscoveryEndpoint" />  
        </service>  
    </service>  
```  
  
 <span data-ttu-id="cd08c-111">Para que un servicio sea reconocible, también debe agregar un punto de conexión de detección; en el ejemplo anterior, se agrega un punto de conexión estándar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="cd08c-111">In order for a service to be discoverable, you must also add a discovery endpoint, the example above adds a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> standard endpoint.</span></span>  
  
 <span data-ttu-id="cd08c-112">Al agregar puntos de conexión de anuncio, también `services` debe agregar un servicio de escucha de anuncio al <> elemento como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd08c-112">When you add announcement endpoints you must also add an announcement listener service to the <`services`> element as shown in the following example.</span></span>  
  
```xml  
<services>  
   <service name="HelloWorldService" behaviorConfiguration="helloWorldServiceBehavior">  
      <!-- Application Endpoint -->  
      <endpoint address="endpoint0"  
                binding="basicHttpBinding"  
                contract="IHelloWorldService" />  
      <!-- Discovery Endpoints -->  
      <endpoint kind="udpDiscoveryEndpoint" />  
   </service>  
   <!-- Announcement Listener Configuration -->  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" />  
   </service>  
```  
  
 <span data-ttu-id="cd08c-113">El comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> se usa para habilitar o deshabilitar la detección de un punto de conexión concreto.</span><span class="sxs-lookup"><span data-stu-id="cd08c-113">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior is used to enable or disable discovery of a specific endpoint.</span></span>  <span data-ttu-id="cd08c-114">En el siguiente ejemplo, se configura un servicio con dos puntos de conexión de la aplicación: uno con detección habilitada y uno con detección deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="cd08c-114">The following example configures a service with two application endpoints, one with discovery enabled and one with discovery disabled.</span></span> <span data-ttu-id="cd08c-115">Para cada punto de conexión, se agrega un comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="cd08c-115">For each endpoint an <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior is added.</span></span>  
  
```xml  
<system.serviceModel>  
   <services>  
      <service name="HelloWorldService"  
               behaviorConfiguration="helloWorldServiceBehavior">  
  
        <!-- Application Endpoints -->  
        <endpoint address="endpoint0"  
                 binding="basicHttpBinding"  
                 contract="IHelloWorldService"
                 behaviorConfiguration="ep0Behavior" />  
  
        <endpoint address="endpoint1"  
                  binding="basicHttpBinding"  
                  contract="IHelloWorldService"  
                  behaviorConfiguration="ep1Behavior" />  
  
        <!-- Discovery Endpoints -->  
        <endpoint kind="udpDiscoveryEndpoint" />  
      </service>  
   </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="helloWorldServiceBehavior">  
          <serviceDiscovery />  
        </behavior>  
      </serviceBehaviors>  
      <endpointBehaviors>  
        <behavior name="ep0Behavior">  
          <endpointDiscovery enabled="true"/>  
        </behavior>  
        <behavior name="ep1Behavior">  
          <endpointDiscovery enabled="false"/>  
        </behavior>  
     </endpointBehaviors>  
   </behaviors>  
```  
  
 <span data-ttu-id="cd08c-116">El comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> también se puede usar para agregar metadatos personalizados a los metadatos del punto de conexión devuelto por el servicio.</span><span class="sxs-lookup"><span data-stu-id="cd08c-116">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior can also be used to add custom metadata to the endpoint metadata returned by the service.</span></span> <span data-ttu-id="cd08c-117">El ejemplo siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="cd08c-117">The following example shows how to do this.</span></span>  
  
```xml  
<behavior name="ep4Behavior">  
   <endpointDiscovery enabled="true">  
      <extensions>  
         <CustomMetadata>This is custom metadata.</CustomMetadata>  
         <d:Types xmlns:d="http://schemas.xmlsoap.org/ws/2005/04/discovery" xmlns:i="http://printer.example.org/2003/imaging">i:PrintBasic</d:Types>  
         <CustomMetadata netsted="true">  
            <NestedMetadata>This is a nested custom metadata.</NestedMetadata>  
         </CustomMetadata>  
      </extensions>  
   </endpointDiscovery>  
</behavior>  
```  
  
 <span data-ttu-id="cd08c-118">El comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> también se puede usar para agregar los ámbitos y los tipos que emplean los clientes para buscar servicios.</span><span class="sxs-lookup"><span data-stu-id="cd08c-118">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior can also be used to add scopes and types that clients use to search for services.</span></span> <span data-ttu-id="cd08c-119">El ejemplo siguiente muestra cómo realizarlo en un archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="cd08c-119">The following example shows how to do this in a client side configuration file.</span></span>  
  
```xml  
<behavior name="ep2Behavior">  
   <endpointDiscovery enabled="true">  
      <scopes>  
         <add scope="http://www.microsoft.com/building42/floor1"/>  
         <add scope="ldap:///ou=engineeringo=examplecomc=us"/>  
      </scopes>  
      <types>  
         <add name="test" namespace="http://example.microsoft.com/" />  
         <add name="additionalContract" namespace="http://example.microsoft.com/" />  
      </types>  
   </endpointDiscovery>  
</behavior>  
```  
  
 <span data-ttu-id="cd08c-120">Para obtener <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> más <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> información acerca de y vea información general sobre la [detección](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)de WCF .</span><span class="sxs-lookup"><span data-stu-id="cd08c-120">For more information about <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> see [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md).</span></span>  
  
## <a name="binding-element-configuration"></a><span data-ttu-id="cd08c-121">Configuración del elemento de enlace</span><span class="sxs-lookup"><span data-stu-id="cd08c-121">Binding Element Configuration</span></span>  
 <span data-ttu-id="cd08c-122">La configuración del elemento de enlace es más interesante para el cliente.</span><span class="sxs-lookup"><span data-stu-id="cd08c-122">Binding element configuration is most interesting on the client side.</span></span> <span data-ttu-id="cd08c-123">Puede usar la configuración para especificar los criterios de búsqueda usados para detectar servicios de una aplicación cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="cd08c-123">You can use configuration to specify the find criteria used to discover services from a WCF client application.</span></span>  <span data-ttu-id="cd08c-124">El siguiente ejemplo crea un enlace personalizado con el canal <xref:System.ServiceModel.Discovery.DiscoveryClient> y especifica criterios de búsqueda que incluyen un tipo y un ámbito.</span><span class="sxs-lookup"><span data-stu-id="cd08c-124">The following example creates a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClient> channel and specifies find criteria that includes a type and scope.</span></span> <span data-ttu-id="cd08c-125">Además, especifica valores para las propiedades <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> y <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A>.</span><span class="sxs-lookup"><span data-stu-id="cd08c-125">In addition it specifies values for the <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> and <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> properties.</span></span>  
  
```xml  
<bindings>  
   <customBinding>  
      <!-- Binding Configuration for the Application Endpoint -->  
      <binding name="discoBindingConfiguration">  
         <discoveryClient>  
            <endpoint kind="discoveryEndpoint"  
                      address="http://localhost:8000/ConfigTest/Discovery"  
                      binding="customBinding"  
                      bindingConfiguration="httpSoap12WSAddressing10"/>  
            <findCriteria duration="00:00:10" maxResults="2">  
              <types>  
                <add name="IHelloWorldService"/>  
              </types>  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>
            </findCriteria>  
          </discoveryClient>  
          <textMessageEncoding messageVersion="Soap11"/>  
          <httpTransport />  
        </binding>  
```  
  
 <span data-ttu-id="cd08c-126">Un punto de conexión de cliente debe hacer referencia a esta configuración del enlace personalizado:</span><span class="sxs-lookup"><span data-stu-id="cd08c-126">This custom binding configuration must be referenced by a client endpoint:</span></span>  
  
```xml  
<client>  
      <endpoint address="http://schemas.microsoft.com/discovery/dynamic"  
                binding="customBinding"  
                bindingConfiguration="discoBindingConfiguration"  
                contract="IHelloWorldService" />  
    </client>  
```  
  
 <span data-ttu-id="cd08c-127">Para obtener más información sobre los criterios de búsqueda, consulte [Búsqueda de detección y FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span><span class="sxs-lookup"><span data-stu-id="cd08c-127">For more information about find criteria see [Discovery Find and FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span></span> <span data-ttu-id="cd08c-128">Para obtener más información acerca de los elementos de detección y enlace, vea Información [general sobre la detección](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md) de WCF</span><span class="sxs-lookup"><span data-stu-id="cd08c-128">For more information about discovery and binding elements see, [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)</span></span>  
  
## <a name="standard-endpoint-configuration"></a><span data-ttu-id="cd08c-129">Configuración de punto de conexión estándar</span><span class="sxs-lookup"><span data-stu-id="cd08c-129">Standard Endpoint Configuration</span></span>  
 <span data-ttu-id="cd08c-130">Los puntos de conexión estándar son puntos de conexión predefinidos que tienen valores predeterminados para una o varias propiedades (dirección, enlace o contrato) o uno o varios valores de propiedad que no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="cd08c-130">Standard endpoints are predefined endpoints that have default values for one or more properties (address, binding, or contract) or one or more property values that cannot change.</span></span> <span data-ttu-id="cd08c-131">.NET 4 se distribuye con 3 puntos de conexión estándar relacionados con la detección: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> y <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="cd08c-131">.NET 4 ships with 3 discovery related standard endpoints: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>, and <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span>  <span data-ttu-id="cd08c-132"><xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> es un extremo estándar pre-configurado para las operaciones de detección en un enlace de multidifusión de UDP.</span><span class="sxs-lookup"><span data-stu-id="cd08c-132">The <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="cd08c-133">La clase <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> es un punto de conexión estándar pre-configurado para enviar mensajes de anuncio en un enlace de UDP.</span><span class="sxs-lookup"><span data-stu-id="cd08c-133">The <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> is a standard endpoint that is pre-configured to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="cd08c-134"><xref:System.ServiceModel.Discovery.DynamicEndpoint> es un extremo estándar que usa la detección para buscar la dirección de extremo de un servicio detectado dinámicamente durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cd08c-134">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> is a standard endpoint that uses discovery to find the endpoint address of a discovered service dynamically at runtime.</span></span>  <span data-ttu-id="cd08c-135">Los enlaces estándar se `endpoint` especifican con un elemento> <que contiene el atributo kind que especifica el tipo de extremo estándar que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="cd08c-135">Standard bindings are specified with an <`endpoint`> element that contains kind attribute that specified the type of standard endpoint to add.</span></span> <span data-ttu-id="cd08c-136">En el siguiente ejemplo, se muestra cómo agregar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="cd08c-136">The following example shows how to add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> and a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span></span>  
  
```xml  
<services>  
   <service name="HelloWorldService">  
      <!-- ...  -->
      <endpoint kind="udpDiscoveryEndpoint" />  
   </service>  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" />  
   </service>  
</services>  
```  
  
 <span data-ttu-id="cd08c-137">Los puntos de conexión `standardEndpoints` estándar se configuran en un elemento> <.</span><span class="sxs-lookup"><span data-stu-id="cd08c-137">Standard endpoints are configured in a <`standardEndpoints`> element.</span></span> <span data-ttu-id="cd08c-138">El ejemplo siguiente muestra cómo habilitar y configurar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="cd08c-138">The following example shows how to configure the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> and the <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span></span>  
  
```xml  
<standardEndpoints>  
      <udpAnnouncementEndpoint>  
        <standardEndpoint
            name="udpAnnouncementEndpointSettings"
            multicastAddress="soap.udp://239.255.255.250:3703"
            maxAnnouncementDelay="00:00:00.800">  
          <transportSettings  
            duplicateMessageHistoryLength="1028"  
            maxPendingMessageCount="10"  
            maxMulticastRetransmitCount="3"  
            maxUnicastRetransmitCount="2"  
            socketReceiveBufferSize="131072"  
            timeToLive="2" />  
        </standardEndpoint>  
      </udpAnnouncementEndpoint>  
      <udpDiscoveryEndpoint>  
        <standardEndpoint  
            name="udpDiscoveryEndpointSettings"  
            multicastAddress="soap.udp://239.255.255.252:3704"  
            maxResponseDelay="00:00:00.800">  
          <transportSettings  
            duplicateMessageHistoryLength="2048"  
            maxPendingMessageCount="5"  
            maxReceivedMessageSize="8192"  
            maxBufferPoolSize="262144"/>  
        </standardEndpoint>  
      </udpDiscoveryEndpoint>  
```  
  
 <span data-ttu-id="cd08c-139">Una vez que haya agregado la configuración de `endpoint` punto final estándar, haga referencia a la configuración en el elemento> de <para cada extremo, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd08c-139">Once you’ve added the standard endpoint configuration, reference the configuration in the <`endpoint`> element for each endpoint as shown in the following sample.</span></span>  
  
```xml  
<services>  
   <service name="HelloWorldService">  
      <!-- ...  -->
      <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="udpDiscoveryEndpointSettings"/>  
   </service>  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" endpointConfiguration="udpAnnouncementEndpointSettings" >  
   </service>  
</services>  
```  
  
 <span data-ttu-id="cd08c-140">A diferencia de los otros punto de conexión estándar usados en la detección, debe especificar un enlace y un contrato para <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="cd08c-140">Unlike the other standard endpoints used in discovery, you specify a binding and contract for <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span> <span data-ttu-id="cd08c-141">El ejemplo siguiente muestra cómo agregar y configurar <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="cd08c-141">The following example shows how to add and configure a <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
      <endpoint kind="dynamicEndpoint" binding="basicHttpBinding" contract="IHelloWorldService" endpointConfiguration="dynamicEndpointConfiguration" />  
    </client>
   <standardEndpoints>  
      <dynamicEndpoint>  
         <standardEndpoint name="dynamicEndpointConfiguration">  
             <discoveryClientSettings>  
              <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="2">  
                 <types>  
                   <add name="IHelloWorldService"/>  
                 </types>  
                 <scopes>  
                   <add scope="http://www.microsoft.com/building42/floor1"/>  
                 </scopes>  
                 <extensions>  
                   <CustomMetadata>This is custom metadata.</CustomMetadata>
                 </extensions>  
               </findCriteria>  
             </discoveryClientSettings>  
           </standardEndpoint>  
         </dynamicEndpoint>  
   </standardEndpoints>  
</system.ServiceModel>  
```  
  
 <span data-ttu-id="cd08c-142">Para obtener más información acerca de los puntos de conexión estándar, consulte [Puntos de conexión estándar](standard-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="cd08c-142">For more information about standard endpoints see [Standard Endpoints](standard-endpoints.md).</span></span>
