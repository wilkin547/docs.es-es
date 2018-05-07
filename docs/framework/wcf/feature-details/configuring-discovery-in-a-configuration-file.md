---
title: Configurar la detección en un archivo de configuración
ms.date: 03/30/2017
ms.assetid: b9884c11-8011-4763-bc2c-c526b80175d0
ms.openlocfilehash: c282767e686ac8a6382268aee8b45eb2d1297f5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-discovery-in-a-configuration-file"></a>Configurar la detección en un archivo de configuración
Hay cuatro grupos principales de configuración usados en la detección. Este tema describirá brevemente cada uno de ellos y mostrará ejemplos de cómo configurarlos. Tras cada sección, se ofrece un vínculo a documentación más detallada sobre cada área.  
  
## <a name="behavior-configuration"></a>Configuración de comportamiento  
 La detección usa comportamientos de servicio y comportamientos de extremo. El comportamiento <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> habilita la detección para todos los extremos de un servicio y le permite especificar los extremos del anuncio.  En el siguiente ejemplo, se muestra cómo agregar <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> y especificar un extremo del anuncio.  
  
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
  
 Cuando especifique el comportamiento, haga referencia a él desde un elemento <`service`>, tal como se muestra en el siguiente ejemplo.  
  
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
  
 Para que un servicio sea reconocible, también debe agregar un extremo de detección; en el ejemplo anterior, se agrega un extremo estándar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.  
  
 Cuando agregue extremos de anuncio también debe agregar un servicio de escucha de anuncio al elemento <`services`>, tal como se muestra en el siguiente ejemplo.  
  
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
  
 El comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> se usa para habilitar o deshabilitar la detección de un extremo concreto.  En el siguiente ejemplo, se configura un servicio con dos extremos de la aplicación: uno con detección habilitada y uno con detección deshabilitada. Para cada extremo, se agrega un comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.  
  
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
  
 El comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> también se puede usar para agregar metadatos personalizados a los metadatos del extremo devuelto por el servicio. En el ejemplo siguiente se muestra cómo hacerlo.  
  
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
  
 El comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> también se puede usar para agregar los ámbitos y los tipos que emplean los clientes para buscar servicios. El ejemplo siguiente muestra cómo realizarlo en un archivo de configuración del cliente.  
  
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
  
 Para obtener más información acerca de <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> y <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> vea [información general sobre la detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md).  
  
## <a name="binding-element-configuration"></a>Configuración del elemento de enlace  
 La configuración del elemento de enlace es más interesante para el cliente. Puede usar la configuración para especificar los criterios de búsqueda usados para detectar servicios de una aplicación cliente de WCF.  El siguiente ejemplo crea un enlace personalizado con el canal <xref:System.ServiceModel.Discovery.DiscoveryClient> y especifica criterios de búsqueda que incluyen un tipo y un ámbito. Además, especifica valores para las propiedades <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> y <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A>.  
  
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
  
 Un punto de conexión de cliente debe hacer referencia a esta configuración del enlace personalizado:  
  
```xml  
<client>  
      <endpoint address="http://schemas.microsoft.com/discovery/dynamic"  
                binding="customBinding"  
                bindingConfiguration="discoBindingConfiguration"  
                contract="IHelloWorldService" />  
    </client>  
```  
  
 Para obtener más información acerca de los criterios de búsqueda, vea [buscar de detección y FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md). Para obtener más información sobre la detección y vea los elementos de enlace, [información general sobre la detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
  
## <a name="standard-endpoint-configuration"></a>Configuración de punto de conexión estándar  
 Los extremos estándar son extremos predefinidos que tienen valores predeterminados para una o varias propiedades (dirección, enlace o contrato) o uno o varios valores de propiedad que no se pueden modificar. .NET 4 se distribuye con 3 extremos estándar relacionados con la detección: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> y <xref:System.ServiceModel.Discovery.DynamicEndpoint>.  <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> es un extremo estándar pre-configurado para las operaciones de detección en un enlace de multidifusión de UDP. La clase <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> es un extremo estándar pre-configurado para enviar mensajes de anuncio en un enlace de UDP. <xref:System.ServiceModel.Discovery.DynamicEndpoint> es un extremo estándar que usa la detección para buscar la dirección de extremo de un servicio detectado dinámicamente durante el tiempo de ejecución.  Los enlaces estándar se especifican con un elemento <`endpoint`> que contiene un atributo de clase que especifica el tipo de extremo estándar que se va a agregar. En el siguiente ejemplo, se muestra cómo agregar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.  
  
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
  
 Los extremos estándar se configuran en un elemento <`standardEndpoints`>. El ejemplo siguiente muestra cómo habilitar y configurar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.  
  
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
  
 Cuando haya agregado la configuración de extremo estándar, haga referencia a la configuración en el elemento <`endpoint`> para cada extremo, tal como se muestra en el siguiente ejemplo.  
  
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
  
 A diferencia de los otros extremos estándar usados en la detección, debe especificar un enlace y un contrato para <xref:System.ServiceModel.Discovery.DynamicEndpoint>. El ejemplo siguiente muestra cómo agregar y configurar <xref:System.ServiceModel.Discovery.DynamicEndpoint>.  
  
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
  
 Para obtener más información acerca de los puntos de conexión estándares vea [puntos de conexión estándar](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)
