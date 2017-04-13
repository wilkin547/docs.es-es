---
title: "Configuraci&#243;n de enlaces para servicios Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "configuración de enlace [WCF]"
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# Configuraci&#243;n de enlaces para servicios Windows Communication Foundation
Con frecuencia al crear una aplicación desea delegar las decisiones al administrador tras la implementación de la aplicación.Por ejemplo, a menudo no hay manera de conocer de antemano qué será una dirección de servicio o un URI.En lugar de incluir una dirección en el código, es preferible permitir a un administrador hacerlo después de crear un servicio.Esta flexibilidad se logra a través de la configuración.  
  
> [!NOTE]
>  Utilice [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con el modificador `/config` para crear rápidamente archivos de configuración.  
  
## Secciones principales  
 El esquema de configuración [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] incluye las tres secciones principales siguientes \(`serviceModel`, `bindings`y `services`\):  
  
```  
<configuration>  
    <system.serviceModel>  
        <bindings>  
        </bindings>  
        <services>  
        </services>  
        <behaviors>  
        </behaviors>  
    </system.serviceModel>  
</configuration>  
```  
  
### Elementos ServiceModel  
 Puede utilizar la sección limitada por el elemento `system.ServiceModel` para configurar un tipo de servicio con uno o más extremos, así como los valores para un servicio.Cada extremo se puede configurar a continuación con una dirección, un contrato y un enlace.[!INCLUDE[crabout](../../../includes/crabout-md.md)] los extremos, vea [Información general acerca de la creación de puntos finales](../../../docs/framework/wcf/endpoint-creation-overview.md).Si no se especifica ningún extremo, el runtime agrega extremos predeterminados.[!INCLUDE[crabout](../../../includes/crabout-md.md)] los extremos, enlaces y comportamientos predeterminados, vea [Configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 Un enlace especifica transportes \(HTTP, TCP, canalizaciones, Message Queuing\) y protocolos \(seguridad, confiabilidad, flujos de transacción\) y está compuesto de elementos de enlace, cada uno de los cuales especifica un aspecto sobre cómo un extremo se comunica con el mundo.  
  
 Por ejemplo, especificar el elemento [\<basicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) indica que se utilice http como el transporte para un extremo.Se utiliza para conectar el extremo en tiempo de ejecución cuando se abre el servicio utilizando este extremo.  
  
 Hay dos tipos de enlaces: predefinidos y personalizados.Los enlaces predefinidos contienen combinaciones útiles de elementos que se utilizan en escenarios comunes.Para obtener una lista de tipos de enlace predefinidos que [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proporciona, vea [Enlaces proporcionados por el sistema](../../../docs/framework/wcf/system-provided-bindings.md).Si ninguna colección de enlace predefinida tiene la combinación correcta de características que una aplicación de servicio necesita, puede construir enlaces personalizados para satisfacer los requisitos de la aplicación.[!INCLUDE[crabout](../../../includes/crabout-md.md)] los enlaces personalizados, vea [\<customBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
 Los cuatro ejemplos siguientes muestran las configuraciones de enlace más comunes utilizadas para preparar un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
#### Especificar un extremo para usar un tipo de enlace  
 El primer ejemplo muestra cómo especificar un extremo configurado con una dirección, un contrato y un enlace.  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!—- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />  
  </endpoint>  
</service>  
```  
  
 En este ejemplo, el atributo de `name` indica para qué tipo de servicio es la configuración.Al crear un servicio en su código con el contrato `HelloWorld`, se inicializa con todos los extremos definidos en la configuración del ejemplo.Si el ensamblado implementa sólo uno contrato de servicios, se puede omitir el atributo `name` porque el servicio utiliza el único tipo disponible.El atributo toma una cadena, que debe tener el formato `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`  
  
 El atributo `address` especifica el URI que otros extremos utilizan para comunicarse con servicio.El URI puede ser una ruta de acceso absoluta o relativa.Si se proporciona una dirección relativa, se espera que el host proporcione una dirección base que sea adecuada para el esquema de transporte usado en el enlace.Si no se configura una dirección, se supone que la dirección base es la dirección para ese extremo.  
  
 El atributo `contract` especifica el contrato que este extremo está exponiendo.El tipo de implementación de servicio debe implementar el tipo de contrato.Si una implementación de servicio implementa un tipo de contrato único, entonces se puede omitir esta propiedad.  
  
 El atributo `binding` selecciona un enlace predefinido o personalizado para utilizarlo para este extremo concreto.Un extremo que no selecciona explícitamente un enlace utiliza la selección de enlace predeterminada, que es `BasicHttpBinding`.  
  
#### Modificar un enlace predefinido  
 En el ejemplo siguiente, se modifica un enlace predefinido.Se puede utilizar a continuación para configurar cualquier extremo en el servicio.El enlace se modifica estableciendo el valor <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> en 1 segundo.Observe que la propiedad devuelve un objeto <xref:System.TimeSpan>.  
  
 Ese enlace alterado se encuentra en la sección de enlaces.Este enlace alterado se puede usar al crear cualquier extremo estableciendo el atributo `binding` en el elemento `endpoint`.  
  
> [!NOTE]
>  Si asigna un nombre determinado al enlace, el atributo `bindingConfiguration` especificado en el extremo de servicio debe coincidir con él.  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />  
  </endpoint>  
</service>  
<bindings>  
    <basicHttpBinding   
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## Configurar un comportamiento para aplicarlo a un servicio  
 En el ejemplo siguiente, un comportamiento concreto se configura para el tipo de servicio.El elemento `ServiceMetadataBehavior` permite a la herramienta [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) consultar el servicio y generar los documentos de Lenguaje de descripción de servicios Web \(WSDL\) de los metadatos.  
  
> [!NOTE]
>  Si asigna un nombre determinado al comportamiento, el atributo `behaviorConfiguration` especificado en el servicio o en la sección de extremo debe coincidir con él.  
  
```  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />   
    </behavior>  
</behaviors>  
<services>  
    <service   
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
       <endpoint   
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />  
       </endpoint>  
    </service>  
</services>  
```  
  
 La configuración anterior permite a un cliente llamar y obtener los metadatos del servicio con tipo "HelloWorld".  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## Especificar un servicio con dos extremos usando valores de enlace diferentes  
 En este último ejemplo, dos extremos se configuran para el tipo de servicio `HelloWorld`.Cada extremo usa un atributo `bindingConfiguration` personalizado diferente del mismo tipo de enlace \(cada uno modifica el atributo `basicHttpBinding`\).  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout"  
    </endpoint>  
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure"  
     </endpoint>  
</service>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
 Puede obtener el mismo comportamiento usando la configuración predeterminada si agrega una sección `protocolMapping` y configura los enlaces, tal y como se muestra en el ejemplo siguiente.  
  
```xml  
<protocolMapping>  
    <add scheme=”http” binding=”basicHttpBinding” bindingConfiguration=”shortTimeout” />  
    <add scheme=”https” binding=”basicHttpBinding” bindingConfiguration=”Secure” />  
</protocolMapping>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
## Vea también  
 [Configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md)   
 [Enlaces proporcionados por el sistema](../../../docs/framework/wcf/system-provided-bindings.md)   
 [Información general acerca de la creación de puntos finales](../../../docs/framework/wcf/endpoint-creation-overview.md)   
 [Utilización de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)