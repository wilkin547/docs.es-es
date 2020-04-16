---
title: Configurar la detección en un archivo de configuración
ms.date: 03/30/2017
ms.assetid: b9884c11-8011-4763-bc2c-c526b80175d0
ms.openlocfilehash: 934b04b51b9954cf943f57f33250951048e5671b
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464203"
---
# <a name="configuring-discovery-in-a-configuration-file"></a>Configurar la detección en un archivo de configuración
Hay cuatro grupos principales de configuración usados en la detección. Este tema describirá brevemente cada uno de ellos y mostrará ejemplos de cómo configurarlos. Tras cada sección, se ofrece un vínculo a documentación más detallada sobre cada área.  
  
## <a name="behavior-configuration"></a>Configuración de comportamiento  
 La detección usa comportamientos de servicio y comportamientos de extremo. El comportamiento <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> habilita la detección para todos los extremos de un servicio y le permite especificar los extremos del anuncio.  En el siguiente ejemplo, se muestra cómo agregar <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> y especificar un punto de conexión del anuncio.  
  
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
  
 Una vez especificado el comportamiento, `service` haga referencia a él desde un elemento> <como se muestra en el ejemplo siguiente.  
  
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
  
 Para que un servicio sea reconocible, también debe agregar un punto de conexión de detección; en el ejemplo anterior, se agrega un punto de conexión estándar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.  
  
 Al agregar puntos de conexión de anuncio, también `services` debe agregar un servicio de escucha de anuncio al <> elemento como se muestra en el ejemplo siguiente.  
  
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
  
 El comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> se usa para habilitar o deshabilitar la detección de un punto de conexión concreto.  En el siguiente ejemplo, se configura un servicio con dos puntos de conexión de la aplicación: uno con detección habilitada y uno con detección deshabilitada. Para cada punto de conexión, se agrega un comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.  
  
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
  
 El comportamiento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> también se puede usar para agregar metadatos personalizados a los metadatos del punto de conexión devuelto por el servicio. El ejemplo siguiente muestra cómo hacerlo.  
  
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
  
 Para obtener <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> más <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> información acerca de y vea información general sobre la [detección](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)de WCF .  
  
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
   </customBinding>
</bindings>  
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
  
 Para obtener más información sobre los criterios de búsqueda, consulte [Búsqueda de detección y FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md). Para obtener más información acerca de los elementos de detección y enlace, vea Información [general sobre la detección](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md) de WCF  
  
## <a name="standard-endpoint-configuration"></a>Configuración de punto de conexión estándar  
 Los puntos de conexión estándar son puntos de conexión predefinidos que tienen valores predeterminados para una o varias propiedades (dirección, enlace o contrato) o uno o varios valores de propiedad que no se pueden modificar. .NET 4 se distribuye con 3 puntos de conexión estándar relacionados con la detección: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> y <xref:System.ServiceModel.Discovery.DynamicEndpoint>.  <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> es un extremo estándar pre-configurado para las operaciones de detección en un enlace de multidifusión de UDP. La clase <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> es un punto de conexión estándar pre-configurado para enviar mensajes de anuncio en un enlace de UDP. <xref:System.ServiceModel.Discovery.DynamicEndpoint> es un extremo estándar que usa la detección para buscar la dirección de extremo de un servicio detectado dinámicamente durante el tiempo de ejecución.  Los enlaces estándar se `endpoint` especifican con un elemento> <que contiene el atributo kind que especifica el tipo de extremo estándar que se va a agregar. En el siguiente ejemplo, se muestra cómo agregar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.  
  
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
  
 Los puntos de conexión `standardEndpoints` estándar se configuran en un elemento> <. El ejemplo siguiente muestra cómo habilitar y configurar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.  
  
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
  
 Una vez que haya agregado la configuración de `endpoint` punto final estándar, haga referencia a la configuración en el elemento> de <para cada extremo, como se muestra en el ejemplo siguiente.  
  
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
  
 A diferencia de los otros punto de conexión estándar usados en la detección, debe especificar un enlace y un contrato para <xref:System.ServiceModel.Discovery.DynamicEndpoint>. El ejemplo siguiente muestra cómo agregar y configurar <xref:System.ServiceModel.Discovery.DynamicEndpoint>.  
  
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
  
 Para obtener más información acerca de los puntos de conexión estándar, consulte [Puntos de conexión estándar](standard-endpoints.md).
