---
title: Ejemplo de configuración
ms.date: 03/30/2017
ms.assetid: 75515b4a-8d70-44c8-99e0-7423df41380e
ms.openlocfilehash: 5ac72db1fce0862381cd614499b5db4b9d95b2d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183916"
---
# <a name="configuration-sample"></a>Ejemplo de configuración
En este ejemplo se muestra el uso de un archivo de configuración para hacer que un servicio se pueda detectar.  
  
> [!NOTE]
> En este ejemplo se implementa la detección en la configuración. Para obtener un ejemplo que implementa la detección en el código, vea [Básico](../../../../docs/framework/wcf/samples/basic-sample.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Configuration`  
  
## <a name="service-configuration"></a>Configuración de servicio  
 El archivo de configuración de este ejemplo muestra dos características:  
  
- Hacer que el servicio se pueda detectar a través de un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> estándar.  
  
- Ajustar la información relacionada con la detección para el extremo de la aplicación del servicio y ajustar algunos de los valores relacionados con la detección en el extremo estándar.  
  
 Para habilitar la detección, se deben realizar algunas modificaciones en el archivo de configuración de la aplicación para el servicio:  
  
- Un extremo de detección se debe agregar al elemento `<service>`. Se trata de un punto de conexión <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> estándar. Este es un punto de conexión del sistema que el tiempo de ejecución asocia al servicio de detección. El servicio de descarga realiza escuchas de los mensajes en este extremo.  
  
- Se agrega un comportamiento `<serviceDiscovery>` a la sección `<serviceBehaviors>`. Esto permite detectar el servicio en tiempo de ejecución runtime y utiliza el punto de conexión de la detección mencionado previamente para realizar escuchas de `Probe` de detección y mensajes `Resolve`. Con estas dos incorporaciones, el servicio se puede detectar en el punto de conexión de detección especificado.  
  
 El siguiente fragmento de código muestra un servicio con un punto de conexión de la aplicación y un punto de conexión de detección definidos:  
  
```xml
<services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
          <endpoint name="udpDiscovery"
                    kind="udpDiscoveryEndpoint"
                endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
```  
  
 Para beneficiarse de los anuncios, tendrá que agregar un extremo de anuncio. Para ello, modifique el archivo de configuración según se muestra en el código siguiente.  
  
```xml  
<serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
```  
  
 Al agregar un punto de conexión de anuncio al comportamiento del servicio de detección, se crea un cliente de anuncio predeterminado para el servicio. Esto garantiza que el servicio enviará un anuncio en línea y sin conexión cuando el servicio se abra y se cierre respectivamente.  
  
 Este archivo de configuración supera esos pasos sencillos al modificar comportamientos adicionales. Es posible controlar la información relacionada con la detección utilizando extremos concretos. Es decir, un usuario puede controlar si se puede detectar un punto de conexión y también puede marcar ese punto de conexión con metadatos XML personalizados y la propiedad <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A>. Para ello, el usuario debe agregar una propiedad `behaviorConfiguration` al extremo de la aplicación. En este caso, la siguiente propiedad se agrega al extremo de la aplicación.  
  
`behaviorConfiguration="endpointBehaviorConfiguration"`  
  
 Ahora, a través del elemento de configuración de comportamiento, puede controlar los atributos relacionados con la detección. En este caso, se agregan dos ámbitos al extremo de la aplicación.  
  
```xml  
<endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>
        </endpointBehaviors>  
```  
  
 Para obtener más información acerca de los ámbitos, vea [Buscar y Buscar criterios de detección](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).  
  
 También puede controlar detalles concretos del punto de conexión de la detección. Esto se hace a través de <xref:System.ServiceModel.Configuration.StandardEndpointsSection>. En este ejemplo, se modifica la versión del protocolo utilizada además de agregar un atributo `maxResponseDelay` en el siguiente ejemplo de código.  
  
```xml  
<standardEndpoints>  
   <udpDiscoveryEndpoint>  
      <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />
   </udpDiscoveryEndpoint>  
</standardEndpoints>  
```  
  
 Lo siguiente es el archivo de configuración completo usado en este ejemplo:  
  
```xml  
<configuration>  
    <system.serviceModel>  
  
      <services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
         <!-- Define the discovery endpoint -->
<endpoint name="udpDiscovery" kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
  
      <behaviors>  
  
        <serviceBehaviors>  
          <behavior name="calculatorServiceBehavior">  
  
            <!-- Add an announcement endpoint -->  
            <serviceDiscovery>  
              <announcementEndpoints>  
                <endpoint kind="udpAnnouncementEndpoint"/>  
              </announcementEndpoints>  
            </serviceDiscovery>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <!-- Add scopes used to identify the service -->  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>
        </endpointBehaviors>  
  
      </behaviors>  
  
      <standardEndpoints>  
        <udpDiscoveryEndpoint>  
         <!-- Configure the UDP discovery endpoint -->  
          <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />
        </udpDiscoveryEndpoint>  
      </standardEndpoints>  
  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client-configuration"></a>Configuración del cliente  
 En el archivo de configuración de la aplicación para el cliente, para la detección se usa el `standardEndpoint` de tipo `dynamicEndpoint`, según se muestra en el fragmento de configuración siguiente.  
  
```xml  
<client>  
   <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
   <endpoint name="calculatorEndpoint"  
             binding="wsHttpBinding"  
             contract="ICalculatorService"  
             kind ="dynamicEndpoint"  
             endpointConfiguration="dynamicEndpointConfiguration">  
   </endpoint>  
</client>  
```  
  
 Cuando un cliente utiliza un `dynamicEndpoint`, el tiempo de ejecución realiza la detección automáticamente. Durante la detección se usan varias opciones de configuración, como las definidas en la sección `discoveryClientSettings`, que especifica el tipo de extremo de detección que se usará:  
  
```xml  
<endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
```  
  
 Los criterios de búsqueda que se usan para buscar servicios:  
  
```xml  
<!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
<findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
   <scopes>  
      <add scope="http://www.microsoft.com/building42/floor1"/>  
   </scopes>  
   <!-- These extensions are sent from the client to the service as part of the probe message -->  
   <extensions>  
      <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
   </extensions>  
</findCriteria>  
```  
  
 Este ejemplo extiende esta característica y modifica el objeto <xref:System.ServiceModel.Discovery.FindCriteria> utilizado por el cliente, así como algunas propiedades del `updDiscoveryEndpoint` estándar que se usa en la detección. Los <xref:System.ServiceModel.Discovery.FindCriteria> se modifican para utilizar un ámbito y un algoritmo `scopeMatchBy` concreto, así como los criterios de terminación personalizados. Además, el ejemplo también muestra el modo en que un cliente puede enviar elementos XML mediante mensajes `Probe`. Por último, se realizan algunos cambios en <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, como la versión del protocolo utilizado y los valores específicos del UDP, como se muestra en el siguiente archivo de configuración.  
  
```xml  
<udpDiscoveryEndpoint>
        <!-- Specify the discovery protocol version and UDP transport settings. -->
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>
      </udpDiscoveryEndpoint>  
```  
  
 Lo siguiente es el archivo de configuración de cliente completo usado en este ejemplo.  
  
```xml  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
      <endpoint name="calculatorEndpoint"  
                binding="wsHttpBinding"  
                contract="ICalculatorService"  
                kind ="dynamicEndpoint"  
                endpointConfiguration="dynamicEndpointConfiguration">  
      </endpoint>  
    </client>  
  
    <standardEndpoints>  
  
      <dynamicEndpoint>
        <standardEndpoint name="dynamicEndpointConfiguration">  
          <discoveryClientSettings>  
            <!-- Controls where the discovery happens. In this case, Probe message is sent over UdpDiscoveryEndpoint. -->  
            <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
  
            <!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
            <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>  
              <!-- These extensions are sent from the client to the service as part of the probe message -->  
              <extensions>  
                <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
              </extensions>  
            </findCriteria>  
          </discoveryClientSettings>  
        </standardEndpoint>
      </dynamicEndpoint>  
  
      <udpDiscoveryEndpoint>
        <!-- Specify the discovery protocol version and UDP transport settings. -->
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>
      </udpDiscoveryEndpoint>  
  
    </standardEndpoints>  
  
  </system.serviceModel>  
```  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1. Este ejemplo utiliza los extremos HTTP y para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas. Para obtener más información, consulte [Configuración de HTTP y HTTPS.](../feature-details/configuring-http-and-https.md) Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas. Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2. Compile la solución.  
  
3. Ejecute el ejecutable de servicio desde el directorio de compilación.  
  
4. Ejecute la aplicación cliente. Observe que el cliente puede localizar el servicio.  
