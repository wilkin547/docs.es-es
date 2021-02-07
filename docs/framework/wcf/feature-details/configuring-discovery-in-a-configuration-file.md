---
description: Más información acerca de cómo configurar la detección en un archivo de configuración
title: Configurar la detección en un archivo de configuración
ms.date: 03/30/2017
ms.assetid: b9884c11-8011-4763-bc2c-c526b80175d0
ms.openlocfilehash: 95ac1a08d40f16141dc5c8763640a258b15ef497
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743296"
---
# <a name="configuring-discovery-in-a-configuration-file"></a><span data-ttu-id="19ab7-103">Configurar la detección en un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="19ab7-103">Configuring Discovery in a Configuration File</span></span>

<span data-ttu-id="19ab7-104">Hay cuatro grupos principales de configuración usados en la detección.</span><span class="sxs-lookup"><span data-stu-id="19ab7-104">There are four major groups of configuration settings used in discovery.</span></span> <span data-ttu-id="19ab7-105">Este tema describirá brevemente cada uno de ellos y mostrará ejemplos de cómo configurarlos.</span><span class="sxs-lookup"><span data-stu-id="19ab7-105">This topic will briefly describe each and show examples of how to configure them.</span></span> <span data-ttu-id="19ab7-106">Tras cada sección, se ofrece un vínculo a documentación más detallada sobre cada área.</span><span class="sxs-lookup"><span data-stu-id="19ab7-106">Following each section will be a link to more in-depth documentation about each area.</span></span>  
  
## <a name="behavior-configuration"></a><span data-ttu-id="19ab7-107">Configuración de comportamiento</span><span class="sxs-lookup"><span data-stu-id="19ab7-107">Behavior Configuration</span></span>  

 <span data-ttu-id="19ab7-108">La detección usa comportamientos de servicio y comportamientos de extremo.</span><span class="sxs-lookup"><span data-stu-id="19ab7-108">Discovery uses service behaviors and endpoint behaviors.</span></span> <span data-ttu-id="19ab7-109">El comportamiento <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> habilita la detección para todos los extremos de un servicio y le permite especificar los extremos del anuncio.</span><span class="sxs-lookup"><span data-stu-id="19ab7-109">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> behavior enables discovery for all of a service’s endpoints and allows you to specify announcement endpoints.</span></span>  <span data-ttu-id="19ab7-110">En el siguiente ejemplo, se muestra cómo agregar <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> y especificar un punto de conexión del anuncio.</span><span class="sxs-lookup"><span data-stu-id="19ab7-110">The following example shows how to add the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and specify an announcement endpoint.</span></span>  
  
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
</behaviors>  
```  
  
 <span data-ttu-id="19ab7-111">Una vez que especifique el comportamiento, haga referencia a él desde un `service` elemento <> como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="19ab7-111">Once you specify the behavior, reference it from a <`service`> element as shown in the following sample.</span></span>  
  
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
    </services>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="19ab7-112">Para que un servicio sea reconocible, también debe agregar un punto de conexión de detección; en el ejemplo anterior, se agrega un punto de conexión estándar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="19ab7-112">In order for a service to be discoverable, you must also add a discovery endpoint, the example above adds a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> standard endpoint.</span></span>  
  
 <span data-ttu-id="19ab7-113">Al agregar puntos de conexión de anuncio, también debe agregar un servicio de escucha de anuncio al `services` elemento <> como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="19ab7-113">When you add announcement endpoints you must also add an announcement listener service to the <`services`> element as shown in the following example.</span></span>  
  
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
</services>
```  
  
 <span data-ttu-id="19ab7-114">El comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> se usa para habilitar o deshabilitar la detección de un punto de conexión concreto.</span><span class="sxs-lookup"><span data-stu-id="19ab7-114">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior is used to enable or disable discovery of a specific endpoint.</span></span>  <span data-ttu-id="19ab7-115">En el siguiente ejemplo, se configura un servicio con dos puntos de conexión de la aplicación: uno con detección habilitada y uno con detección deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="19ab7-115">The following example configures a service with two application endpoints, one with discovery enabled and one with discovery disabled.</span></span> <span data-ttu-id="19ab7-116">Para cada punto de conexión, se agrega un comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="19ab7-116">For each endpoint an <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior is added.</span></span>  
  
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
</system.serviceModel>  
```  
  
 <span data-ttu-id="19ab7-117">El comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> también se puede usar para agregar metadatos personalizados a los metadatos del punto de conexión devuelto por el servicio.</span><span class="sxs-lookup"><span data-stu-id="19ab7-117">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior can also be used to add custom metadata to the endpoint metadata returned by the service.</span></span> <span data-ttu-id="19ab7-118">El ejemplo siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="19ab7-118">The following example shows how to do this.</span></span>  
  
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
  
 <span data-ttu-id="19ab7-119">El comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> también se puede usar para agregar los ámbitos y los tipos que emplean los clientes para buscar servicios.</span><span class="sxs-lookup"><span data-stu-id="19ab7-119">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior can also be used to add scopes and types that clients use to search for services.</span></span> <span data-ttu-id="19ab7-120">El ejemplo siguiente muestra cómo realizarlo en un archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="19ab7-120">The following example shows how to do this in a client side configuration file.</span></span>  
  
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
  
 <span data-ttu-id="19ab7-121">Para obtener más información acerca de <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> y <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> consulte [información general](wcf-discovery-overview.md)sobre la detección de WCF.</span><span class="sxs-lookup"><span data-stu-id="19ab7-121">For more information about <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> see [WCF Discovery Overview](wcf-discovery-overview.md).</span></span>  
  
## <a name="binding-element-configuration"></a><span data-ttu-id="19ab7-122">Configuración del elemento de enlace</span><span class="sxs-lookup"><span data-stu-id="19ab7-122">Binding Element Configuration</span></span>  

 <span data-ttu-id="19ab7-123">La configuración del elemento de enlace es más interesante para el cliente.</span><span class="sxs-lookup"><span data-stu-id="19ab7-123">Binding element configuration is most interesting on the client side.</span></span> <span data-ttu-id="19ab7-124">Puede usar la configuración para especificar los criterios de búsqueda usados para detectar servicios de una aplicación cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="19ab7-124">You can use configuration to specify the find criteria used to discover services from a WCF client application.</span></span>  <span data-ttu-id="19ab7-125">El siguiente ejemplo crea un enlace personalizado con el canal <xref:System.ServiceModel.Discovery.DiscoveryClient> y especifica criterios de búsqueda que incluyen un tipo y un ámbito.</span><span class="sxs-lookup"><span data-stu-id="19ab7-125">The following example creates a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClient> channel and specifies find criteria that includes a type and scope.</span></span> <span data-ttu-id="19ab7-126">Además, especifica valores para las propiedades <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> y <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A>.</span><span class="sxs-lookup"><span data-stu-id="19ab7-126">In addition it specifies values for the <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> and <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> properties.</span></span>  
  
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
   </customBinding>
</bindings>  
```  
  
 <span data-ttu-id="19ab7-127">Un punto de conexión de cliente debe hacer referencia a esta configuración del enlace personalizado:</span><span class="sxs-lookup"><span data-stu-id="19ab7-127">This custom binding configuration must be referenced by a client endpoint:</span></span>  
  
```xml  
<client>  
      <endpoint address="http://schemas.microsoft.com/discovery/dynamic"  
                binding="customBinding"  
                bindingConfiguration="discoBindingConfiguration"  
                contract="IHelloWorldService" />  
</client>  
```  
  
 <span data-ttu-id="19ab7-128">Para obtener más información sobre los criterios de búsqueda [, consulte descubrimiento y FindCriteria de detección](discovery-find-and-findcriteria.md).</span><span class="sxs-lookup"><span data-stu-id="19ab7-128">For more information about find criteria see [Discovery Find and FindCriteria](discovery-find-and-findcriteria.md).</span></span> <span data-ttu-id="19ab7-129">Para obtener más información sobre los elementos de detección y enlace, vea [información general](wcf-discovery-overview.md) sobre la detección de WCF</span><span class="sxs-lookup"><span data-stu-id="19ab7-129">For more information about discovery and binding elements see, [WCF Discovery Overview](wcf-discovery-overview.md)</span></span>  
  
## <a name="standard-endpoint-configuration"></a><span data-ttu-id="19ab7-130">Configuración de punto de conexión estándar</span><span class="sxs-lookup"><span data-stu-id="19ab7-130">Standard Endpoint Configuration</span></span>  

 <span data-ttu-id="19ab7-131">Los puntos de conexión estándar son puntos de conexión predefinidos que tienen valores predeterminados para una o varias propiedades (dirección, enlace o contrato) o uno o varios valores de propiedad que no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="19ab7-131">Standard endpoints are predefined endpoints that have default values for one or more properties (address, binding, or contract) or one or more property values that cannot change.</span></span> <span data-ttu-id="19ab7-132">.NET 4 se distribuye con 3 puntos de conexión estándar relacionados con la detección: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> y <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="19ab7-132">.NET 4 ships with 3 discovery related standard endpoints: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>, and <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span>  <span data-ttu-id="19ab7-133"><xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> es un extremo estándar pre-configurado para las operaciones de detección en un enlace de multidifusión de UDP.</span><span class="sxs-lookup"><span data-stu-id="19ab7-133">The <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="19ab7-134">La clase <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> es un punto de conexión estándar pre-configurado para enviar mensajes de anuncio en un enlace de UDP.</span><span class="sxs-lookup"><span data-stu-id="19ab7-134">The <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> is a standard endpoint that is pre-configured to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="19ab7-135"><xref:System.ServiceModel.Discovery.DynamicEndpoint> es un extremo estándar que usa la detección para buscar la dirección de extremo de un servicio detectado dinámicamente durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="19ab7-135">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> is a standard endpoint that uses discovery to find the endpoint address of a discovered service dynamically at runtime.</span></span>  <span data-ttu-id="19ab7-136">Los enlaces estándar se especifican con un `endpoint` elemento <> que contiene el atributo Kind que especifica el tipo de extremo estándar que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="19ab7-136">Standard bindings are specified with an <`endpoint`> element that contains kind attribute that specified the type of standard endpoint to add.</span></span> <span data-ttu-id="19ab7-137">En el siguiente ejemplo, se muestra cómo agregar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="19ab7-137">The following example shows how to add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> and a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span></span>  
  
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
  
 <span data-ttu-id="19ab7-138">Los extremos estándar se configuran en un `standardEndpoints` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="19ab7-138">Standard endpoints are configured in a <`standardEndpoints`> element.</span></span> <span data-ttu-id="19ab7-139">El ejemplo siguiente muestra cómo habilitar y configurar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="19ab7-139">The following example shows how to configure the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> and the <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span></span>  
  
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
</standardEndpoints>
```  
  
 <span data-ttu-id="19ab7-140">Una vez que haya agregado la configuración de extremo estándar, haga referencia a la configuración del `endpoint` elemento <> para cada extremo, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="19ab7-140">Once you’ve added the standard endpoint configuration, reference the configuration in the <`endpoint`> element for each endpoint as shown in the following sample.</span></span>  
  
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
  
 <span data-ttu-id="19ab7-141">A diferencia de los otros punto de conexión estándar usados en la detección, debe especificar un enlace y un contrato para <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="19ab7-141">Unlike the other standard endpoints used in discovery, you specify a binding and contract for <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span> <span data-ttu-id="19ab7-142">El ejemplo siguiente muestra cómo agregar y configurar <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="19ab7-142">The following example shows how to add and configure a <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span>  
  
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
  
 <span data-ttu-id="19ab7-143">Para obtener más información sobre los puntos de conexión estándar, vea [puntos de conexión estándar](standard-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="19ab7-143">For more information about standard endpoints see [Standard Endpoints](standard-endpoints.md).</span></span>
