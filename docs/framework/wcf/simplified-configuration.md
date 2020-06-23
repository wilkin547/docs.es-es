---
title: Configuración simplificada
description: Obtenga información acerca de la configuración simplificada de los servicios WCF. .NET Framework 4.6.1 proporciona una manera de reducir el tamaño y la complejidad de la configuración del servicio.
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: defaf536d5a5b9f1479271c0976b43e9b1eb5bc4
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246043"
---
# <a name="simplified-configuration"></a>Configuración simplificada
La configuración de servicios de Windows Communication Foundation (WCF) puede ser una tarea compleja. Existen muchas opciones diferentes y no siempre es fácil determinar qué configuración es necesaria. Aunque los archivos de configuración aumentan la flexibilidad de los servicios WCF, también son el origen de muchos problemas difíciles de encontrar. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] aborda estos problemas y proporciona una forma de reducir el tamaño y la complejidad de la configuración del servicio.  
  
## <a name="simplified-configuration"></a>Configuración simplificada  
 En los archivos de configuración del servicio WCF, la `system.serviceModel` sección <> contiene un `service` elemento de> de <para cada servicio hospedado. El `service` elemento <> contiene una colección de `endpoint` elementos de> <que especifican los extremos expuestos para cada servicio y, opcionalmente, un conjunto de comportamientos de servicio. Los elementos de> de <`endpoint` especifican la dirección, el enlace y el contrato expuestos por el extremo y, opcionalmente, la configuración de enlace y los comportamientos de extremo. La `system.serviceModel` sección <> contiene también un elemento de> de <`behaviors` que le permite especificar comportamientos de servicio o de extremo. En el ejemplo siguiente se muestra la `system.serviceModel` sección <> de un archivo de configuración.  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
        <serviceDebug includeExceptionDetailInFaults="false" />  
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
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]facilita la configuración de un servicio WCF mediante la eliminación del requisito del `service` elemento de> de <. Si no agrega un <`service`> sección o agrega puntos de conexión en una <`service`> sección y el servicio no define ningún extremo mediante programación, se agrega automáticamente un conjunto de extremos predeterminados al servicio, uno para cada dirección base del servicio y para cada contrato implementado por el servicio. En cada uno de estos puntos de conexión, la dirección del punto de conexión corresponde a la dirección base, el esquema de la dirección base determina el enlace y el contrato es el implementado por el servicio. Si no necesita especificar ningún extremo o comportamientos del servicio, ni realizar ningún cambio de configuración de enlaces, no necesita especificar ningún archivo de configuración de servicio. Si un servicio implementa dos contratos y el host habilita transportes HTTP y TCP, el host de servicio crea cuatro extremos predeterminados, uno para cada contrato al usar cada transporte. Para crear extremos predeterminados, el host de servicio debe conocer qué enlaces hay que utilizar. Esta configuración se especifica en una <`protocolMappings`> sección dentro de la `system.serviceModel` sección <>. La `protocolMappings` sección <> contiene una lista de esquemas de protocolos de transporte asignados a tipos de enlace. El host de servicio usa las direcciones base que se le han transmitido para determinar qué enlace debe usar. En el ejemplo siguiente se usa el `protocolMappings` elemento <>.  
  
> [!WARNING]
> Al cambiar los elementos de la configuración predeterminada, como los enlaces o los comportamientos, puede afectar a los servicios definidos en los niveles inferiores de la jerarquía de configuración, dado que podrían usar dichos enlaces y comportamientos predeterminados. Por lo tanto, siempre que cambien los enlaces y comportamientos predeterminados, es necesario tener en cuenta de que estos cambios podrían afectar a otros servicios de la jerarquía.  
  
> [!NOTE]
> Los servicios hospedados en Internet Information Services (IIS) o en el Servicio de activación de procesos de Windows (WAS) usan el directorio virtual como su dirección base.  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 En el ejemplo anterior, un punto de conexión con una dirección base que se inicia con el esquema de "http" utiliza el objeto <xref:System.ServiceModel.BasicHttpBinding>. Un extremo con una dirección base que se inicia con el esquema "net.tcp" usa <xref:System.ServiceModel.NetTcpBinding>. Puede invalidar la configuración en un archivo App.config o Web.config local.  
  
 Cada elemento dentro de la `protocolMappings` sección <> debe especificar un esquema y un enlace. Opcionalmente, puede especificar un `bindingConfiguration` atributo que especifique una configuración de enlace dentro de la `bindings` sección <> del archivo de configuración. Si no se especifica `bindingConfiguration`, se utiliza la configuración de enlace anónima del tipo de enlace adecuado.  
  
 Los comportamientos de servicio se configuran para los extremos predeterminados mediante el uso de <anónimas `behavior`> secciones dentro de <`serviceBehaviors` secciones>. Los `behavior` elementos de> de <sin nombre dentro de <`serviceBehaviors`> se usan para configurar los comportamientos del servicio. Por ejemplo, el siguiente archivo de configuración habilita la publicación de metadatos del servicio para todos los servicios dentro del host.  
  
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
  
 Los comportamientos de extremo se configuran mediante <anónimas `behavior`> secciones dentro de <`serviceBehaviors` secciones de>.  
  
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
> Esta característica se relaciona únicamente con la configuración de servicio de WCF, no con la configuración de cliente. La mayoría de las veces, la configuración de cliente de WCF se generará mediante una herramienta como svcutil.exe o la adición de una referencia de servicio desde Visual Studio. Si está configurando manualmente un cliente de WCF, deberá agregar un \<client> elemento a la configuración y especificar los extremos que desee llamar.  
  
## <a name="see-also"></a>Vea también

- [Configuración de servicios mediante archivos de configuración](configuring-services-using-configuration-files.md)
- [Configuración de enlaces para los servicios](configuring-bindings-for-wcf-services.md)
- [Configuración de enlaces proporcionados por el sistema](./feature-details/configuring-system-provided-bindings.md)
- [Configuración de servicios](configuring-services.md)
- [Configuración de servicios WCF](configuring-services.md)
- [Configurar servicios WCF en el código](configuring-wcf-services-in-code.md)
