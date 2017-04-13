---
title: "Configuraci&#243;n simplificada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Configuraci&#243;n simplificada
Configurar los servicios de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] puede ser una tarea compleja.  Existen muchas opciones diferentes y no siempre es fácil determinar qué configuración es necesaria.  Aunque los archivos de configuración aumentan la flexibilidad de los servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], también son el origen de muchos problemas difíciles de detectar.  [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] aborda estos problemas y proporciona una forma de reducir el tamaño y la complejidad de la configuración del servicio.  
  
## Configuración simplificada  
 En los archivos de configuración de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], la sección \<`system.serviceModel`\> contiene un elemento \<`service`\> para cada servicio hospedado.  El elemento `service` contiene una recopilación de elementos \<`endpoint`\> que especifican los extremos expuestos para cada servicio y, opcionalmente, un conjunto de comportamientos del servicio.  Los elementos \<`endpoint`\> especifican la dirección, el enlace y el contrato expuestos por el extremo y, opcionalmente, la configuración de enlace y los comportamientos de los extremos.  La sección \<`system.serviceModel`\> también contiene un elemento \<`behaviors`\> que le permite especificar los comportamientos de los servicios o los extremos.  En el ejemplo siguiente, se muestra la sección \<`system.serviceModel`\> de un archivo de configuración.  
  
```  
system.serviceModel>  
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
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] facilita la configuración de un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] eliminando el requisito del elemento \<`service`\>.  Si no agrega ninguna sección \<`service`\> ni ningún extremo en una sección \<`service`\> y el servicio no define ningún extremo mediante programación, entonces se agrega automáticamente al servicio un conjunto de extremos predeterminados, uno para cada dirección base del servicio y para cada contrato implementado por el servicio.  En cada uno de estos extremos, la dirección del extremo corresponde a la dirección base, el esquema de la dirección base determina el enlace y el contrato es el implementado por el servicio.  Si no necesita especificar ningún extremo o comportamientos del servicio, ni realizar ningún cambio de configuración de enlaces, no necesita especificar ningún archivo de configuración de servicio.  Si un servicio implementa dos contratos y el host habilita transportes HTTP y TCP, el host de servicio crea cuatro extremos predeterminados, uno para cada contrato al usar cada transporte.  Para crear extremos predeterminados, el host de servicio debe conocer qué enlaces hay que utilizar.  Esta configuración se especifica en una sección \<`protocolMappings`\> dentro de la sección \<`system.serviceModel`\>.  La sección \<`protocolMappings`\> contiene una lista de esquemas de protocolos de transporte asignada a los tipos de enlaces.  El host de servicio usa las direcciones base que se le han transmitido para determinar qué enlace debe usar.  El ejemplo siguiente usa el elemento \<`protocolMappings`\>.  
  
> [!WARNING]
>  Al cambiar los elementos de la configuración predeterminada, como los enlaces o los comportamientos, puede afectar a los servicios definidos en los niveles inferiores de la jerarquía de configuración, dado que podrían usar dichos enlaces y comportamientos predeterminados.  Por lo tanto, siempre que cambien los enlaces y comportamientos predeterminados, es necesario tener en cuenta de que estos cambios podrían afectar a otros servicios de la jerarquía.  
  
> [!NOTE]
>  Los servicios hospedados en Internet Information Services \(IIS\) o en el Servicio de activación de procesos de Windows \(WAS\) usan el directorio virtual como su dirección base.  
  
```  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
  
```  
  
 En el ejemplo anterior, un extremo con una dirección base que se inicia con el esquema de "http" utiliza el objeto <xref:System.ServiceModel.BasicHttpBinding>.  Un extremo con una dirección base que se inicia con el esquema "net.tcp" usa <xref:System.ServiceModel.NetTcpBinding>.  Puede invalidar la configuración en un archivo App.config o Web.config local.  
  
 Cada elemento dentro de la sección \<`protocolMappings`\> debe especificar un esquema y un enlace.  Opcionalmente, puede indicar un atributo `bindingConfiguration` que especifique una configuración de enlace dentro de la sección \<`bindings`\> del archivo de configuración.  Si no se especifica `bindingConfiguration`, se utiliza la configuración de enlace anónima del tipo de enlace adecuado.  
  
 Los comportamientos del servicio se configuran para los extremos predeterminados mediante secciones \<`behavior`\> anónimas dentro de secciones \<`serviceBehaviors`\>.  Todos los elementos \<`behavior`\> sin nombre dentro de \<`serviceBehaviors`\> se utilizan para configurar comportamientos del servicio.  Por ejemplo, el siguiente archivo de configuración habilita la publicación de metadatos del servicio para todos los servicios dentro del host.  
  
```  
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
  
 Los comportamientos de los extremos se configuran mediante secciones \<`behavior`\> anónimas dentro de secciones \<`serviceBehaviors`\>.  
  
 El siguiente ejemplo es un archivo de configuración equivalente al del principio de este tema que utiliza el modelo de configuración simplificado.  
  
```  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <bindings>  
       <basicHttpBinding>  
          <binding maxBufferSize="100"  
                   maxReceiveBufferSize="100" />  
       </basicHttpBinding>  
    </bindings>    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->  
    <!-- The service behavior with name="" will be picked up by the service -->  
    <protocolMapping>  
      <add scheme="http"     binding="basicHttpBinding" / </protocolMapping>  
  </system.serviceModel>  
```  
  
> [!IMPORTANT]
>  Esta característica se relaciona únicamente con la configuración de servicio de WCF, no con la configuración de cliente.  La mayoría de las veces, la configuración de cliente de WCF se generará mediante una herramienta como svcutil.exe o la adición de una referencia de servicio desde Visual Studio.  Si está configurando manualmente un cliente de WCF, deberá agregar un elemento \<client\> a la configuración y especificar los extremos que desee llamar.  
  
## Vea también  
 [Configuración de servicios mediante archivos de configuración](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)   
 [Configurar enlaces para los servicios](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Configuración de servicios](../../../docs/framework/wcf/configuring-services.md)   
 [Configuring Windows Communication Foundation Applications](http://msdn.microsoft.com/es-es/13cb368e-88d4-4c61-8eed-2af0361c6d7a)   
 [Configurar servicios WCF en el código](../../../docs/framework/wcf/configuring-wcf-services-in-code.md)