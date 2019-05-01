---
title: Configuración simplificada
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 13cf8bd46ef3aabb011cb2ddd207963235468662
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967900"
---
# <a name="simplified-configuration"></a>Configuración simplificada
Configuración de servicios de Windows Communication Foundation (WCF) puede ser una tarea compleja. Existen muchas opciones diferentes y no siempre es fácil determinar qué configuración es necesaria. Aunque los archivos de configuración aumentan la flexibilidad de los servicios de WCF, también son el origen de muchos difícil encontrar problemas. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] aborda estos problemas y proporciona una forma de reducir el tamaño y la complejidad de la configuración del servicio.  
  
## <a name="simplified-configuration"></a>Configuración simplificada  
 En los archivos de configuración de servicio WCF, el <`system.serviceModel`> sección contiene un <`service`> (elemento) para cada servicio hospedado. El <`service`> elemento contiene una colección de <`endpoint`> elementos que especifican los extremos expuestos para cada servicio y, opcionalmente, un conjunto de comportamientos de servicio. El <`endpoint`> elementos especifican la dirección, enlace y el contrato expuestos por el punto de conexión y, opcionalmente, configuración de enlace y los comportamientos de extremo. El <`system.serviceModel`> sección también contiene un <`behaviors`> elemento que le permite especificar comportamientos de servicio o punto de conexión. El ejemplo siguiente se muestra el <`system.serviceModel`> sección de un archivo de configuración.  
  
```  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true">  
        <serviceDebug includeExceptionDetailInFaults="false">  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] facilita la configuración de un servicio WCF que sea más fácil al eliminar el requisito para el <`service`> elemento. Si no se agrega un <`service`> sección o agregar los puntos de conexión en un <`service`> sección y el servicio no define mediante programación ningún extremo, a continuación, un conjunto de puntos de conexión predeterminados se agregan automáticamente a su servicio, uno para cada uno dirección base del servicio y para cada contrato implementado por el servicio. En cada uno de estos puntos de conexión, la dirección del punto de conexión corresponde a la dirección base, el esquema de la dirección base determina el enlace y el contrato es el implementado por el servicio. Si no necesita especificar ningún extremo o comportamientos del servicio, ni realizar ningún cambio de configuración de enlaces, no necesita especificar ningún archivo de configuración de servicio. Si un servicio implementa dos contratos y el host habilita transportes HTTP y TCP, el host de servicio crea cuatro extremos predeterminados, uno para cada contrato al usar cada transporte. Para crear extremos predeterminados, el host de servicio debe conocer qué enlaces hay que utilizar. Estos valores se especifican en un <`protocolMappings`> sección dentro de la <`system.serviceModel`> sección. El <`protocolMappings`> sección contiene una lista de esquemas de protocolos de transporte asignada a los tipos de enlaces. El host de servicio usa las direcciones base que se le han transmitido para determinar qué enlace debe usar. En el ejemplo siguiente se usa el <`protocolMappings`> elemento.  
  
> [!WARNING]
>  Al cambiar los elementos de la configuración predeterminada, como los enlaces o los comportamientos, puede afectar a los servicios definidos en los niveles inferiores de la jerarquía de configuración, dado que podrían usar dichos enlaces y comportamientos predeterminados. Por lo tanto, siempre que cambien los enlaces y comportamientos predeterminados, es necesario tener en cuenta de que estos cambios podrían afectar a otros servicios de la jerarquía.  
  
> [!NOTE]
>  Los servicios hospedados en Internet Information Services (IIS) o en el Servicio de activación de procesos de Windows (WAS) usan el directorio virtual como su dirección base.  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 En el ejemplo anterior, un punto de conexión con una dirección base que se inicia con el esquema de "http" utiliza el objeto <xref:System.ServiceModel.BasicHttpBinding>. Un extremo con una dirección base que se inicia con el esquema "net.tcp" usa <xref:System.ServiceModel.NetTcpBinding>. Puede invalidar la configuración en un archivo App.config o Web.config local.  
  
 Cada elemento dentro de la <`protocolMappings`> sección debe especificar un esquema y un enlace. Opcionalmente, puede indicar un `bindingConfiguration` atributo que especifica una configuración de enlace dentro de la <`bindings`> sección del archivo de configuración. Si no se especifica `bindingConfiguration`, se utiliza la configuración de enlace anónima del tipo de enlace adecuado.  
  
 Los comportamientos de servicio se configuran para los extremos predeterminados mediante el uso anónimo <`behavior`> dentro de secciones <`serviceBehaviors`> secciones. Cualquiera sin nombre <`behavior`> elementos dentro de <`serviceBehaviors`> se utilizan para configurar comportamientos del servicio. Por ejemplo, el siguiente archivo de configuración habilita la publicación de metadatos del servicio para todos los servicios dentro del host.  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 Los comportamientos de extremo se configuran mediante el uso anónimo <`behavior`> dentro de secciones <`serviceBehaviors`> secciones.  
  
 El siguiente ejemplo es un archivo de configuración equivalente al del principio de este tema que utiliza el modelo de configuración simplificado.  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
>  Esta característica se relaciona únicamente con la configuración de servicio de WCF, no con la configuración de cliente. La mayoría de las veces, la configuración de cliente de WCF se generará mediante una herramienta como svcutil.exe o la adición de una referencia de servicio desde Visual Studio. Si está configurando manualmente un cliente WCF deberá agregar un \<cliente > elemento a la configuración y especificar los extremos que desea llamar.  
  
## <a name="see-also"></a>Vea también

- [Configuración de servicios mediante archivos de configuración](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)
- [Configuración de enlaces para los servicios](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [Configuración de enlaces proporcionados por el sistema](../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Configuración de servicios](../../../docs/framework/wcf/configuring-services.md)
- [Configuración de servicios WCF](configuring-services.md)
- [Configuración de servicios WCF en el código](../../../docs/framework/wcf/configuring-wcf-services-in-code.md)
