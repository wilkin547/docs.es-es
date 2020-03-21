---
title: Configuración de enlaces para servicios Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
ms.openlocfilehash: e7ee1a8ce358c77e46db39af67bd9dc20114fb3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174828"
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a>Configuración de enlaces para servicios Windows Communication Foundation
Con frecuencia al crear una aplicación desea delegar las decisiones al administrador tras la implementación de la aplicación. Por ejemplo, a menudo no hay manera de conocer de antemano qué será una dirección de servicio o un URI. En lugar de incluir una dirección en el código, es preferible permitir a un administrador hacerlo después de crear un servicio. Esta flexibilidad se logra a través de la configuración.  
  
> [!NOTE]
> Utilice la herramienta de utilidad de metadatos de `/config` [ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) con el modificador para crear rápidamente archivos de configuración.  
  
## <a name="major-sections"></a>Secciones principales  
 El esquema de configuración de Windows Communication Foundation`serviceModel`(WCF) incluye las tres secciones principales siguientes ( , `bindings`, y `services`):  
  
```xml  
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
  
### <a name="servicemodel-elements"></a>Elementos ServiceModel  
 Puede usar la sección delimitada por el `system.ServiceModel` elemento para configurar un tipo de servicio con uno o varios puntos de conexión, así como la configuración de un servicio. Cada extremo se puede configurar a continuación con una dirección, un contrato y un enlace. Para obtener más información acerca de los puntos de conexión, consulte Información general sobre la [creación de puntos](endpoint-creation-overview.md)de conexión . Si no se especifica ningún extremo, el tiempo de ejecución agrega extremos predeterminados. Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](./samples/simplified-configuration-for-wcf-services.md).  
  
 Un enlace especifica transportes (HTTP, TCP, canalizaciones, Message Queuing) y protocolos (seguridad, confiabilidad, flujos de transacción) y está compuesto de elementos de enlace, cada uno de los cuales especifica un aspecto sobre cómo un punto de conexión se comunica con el mundo.  
  
 Por ejemplo, especificar [ \<](../configure-apps/file-schema/wcf/basichttpbinding.md) el elemento de>basicHttpBinding indica que se debe usar HTTP como transporte para un punto de conexión. Se utiliza para conectar el extremo en tiempo de ejecución cuando se abre el servicio utilizando este extremo.  
  
 Hay dos tipos de enlaces: predefinidos y personalizados. Los enlaces predefinidos contienen combinaciones útiles de elementos que se utilizan en escenarios comunes. Para obtener una lista de tipos de enlace predefinidos que proporciona WCF, vea [enlaces proporcionados por](system-provided-bindings.md)el sistema . Si ninguna colección de enlace predefinido tiene la combinación correcta de características que una aplicación de servicio necesita, puede construir enlaces personalizados para satisfacer los requisitos de la aplicación. Para obtener más información acerca de los enlaces personalizados, vea [ \<customBinding>](../configure-apps/file-schema/wcf/custombinding.md).  
  
 Los cuatro ejemplos siguientes ilustran las configuraciones de enlace más comunes utilizadas para configurar un servicio WCF.  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a>Especificar un punto de conexión para usar un tipo de enlace  
 El primer ejemplo muestra cómo especificar un extremo configurado con una dirección, un contrato y un enlace.  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!-- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
```  
  
 En este ejemplo, el atributo de `name` indica para qué tipo de servicio es la configuración. Al crear un servicio en su código con el contrato `HelloWorld`, se inicializa con todos los extremos definidos en la configuración del ejemplo. Si el ensamblado implementa solo un `name` contrato de servicio, el atributo se puede omitir porque el servicio usa el único tipo disponible. El atributo toma una cadena, que debe tener el formato `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`  
  
 El atributo `address` especifica el URI que otros extremos utilizan para comunicarse con servicio. El URI puede ser una ruta de acceso absoluta o relativa. Si se proporciona una dirección relativa, se espera que el host proporcione una dirección base que sea adecuada para el esquema de transporte usado en el enlace. Si no se configura una dirección, se supone que la dirección base es la dirección para ese punto de conexión.  
  
 El atributo `contract` especifica el contrato que este punto de conexión está exponiendo. El tipo de implementación de servicio debe implementar el tipo de contrato. Si una implementación de servicio implementa un tipo de contrato único, entonces se puede omitir esta propiedad.  
  
 El atributo `binding` selecciona un enlace predefinido o personalizado para utilizarlo para este punto de conexión concreto. Un extremo que no selecciona explícitamente un enlace utiliza la selección de enlace predeterminada, que es `BasicHttpBinding`.  
  
#### <a name="modifying-a-predefined-binding"></a>Modificar un enlace predefinido  
 En el ejemplo siguiente, se modifica un enlace predefinido. Se puede utilizar a continuación para configurar cualquier extremo en el servicio. El enlace se modifica estableciendo el valor <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> en 1 segundo. Observe que la propiedad devuelve un objeto <xref:System.TimeSpan>.  
  
 Ese enlace alterado se encuentra en la sección de enlaces. Este enlace alterado se puede usar al crear cualquier punto de conexión estableciendo el atributo `binding` en el elemento `endpoint`.  
  
> [!NOTE]
> Si asigna un nombre determinado al enlace, el atributo `bindingConfiguration` especificado en el punto de conexión de servicio debe coincidir con él.  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
<bindings>  
    <basicHttpBinding
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## <a name="configuring-a-behavior-to-apply-to-a-service"></a>Configurar un comportamiento para aplicarlo a un servicio  
 En el ejemplo siguiente, un comportamiento concreto se configura para el tipo de servicio. El `ServiceMetadataBehavior` elemento se utiliza para habilitar la herramienta de utilidad de metadatos de [ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) para consultar el servicio y generar documentos WSDL (Web Services Description Language) a partir de los metadatos.  
  
> [!NOTE]
> Si asigna un nombre determinado al comportamiento, el atributo `behaviorConfiguration` especificado en el servicio o en la sección de punto de conexión debe coincidir con él.  
  
```xml  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />
    </behavior>  
</behaviors>  
<services>  
    <service
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">
       <endpoint
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />
    </service>  
</services>  
```  
  
 La configuración anterior permite a un cliente llamar y obtener los metadatos del servicio con tipo "HelloWorld".  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## <a name="specifying-a-service-with-two-endpoints-using-different-binding-values"></a>Especificar un servicio con dos extremos usando valores de enlace diferentes  
 En este último ejemplo, dos extremos se configuran para el tipo de servicio `HelloWorld`. Cada extremo usa `bindingConfiguration` un atributo personalizado diferente del mismo `basicHttpBinding`tipo de enlace (cada uno modifica el archivo ).  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout" />
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure" />
</service>  
<bindings>  
    <basicHttpBinding
        name="shortTimeout"  
        timeout="00:00:00:01"
     />  
     <basicHttpBinding
        name="Secure">  
        <Security mode="Transport" />  
     </basicHttpBinding>
</bindings>  
```  
  
 Puede obtener el mismo comportamiento usando la configuración predeterminada si agrega una sección `protocolMapping` y configura los enlaces, tal y como se muestra en el ejemplo siguiente.  
  
```xml  
<protocolMapping>  
    <add scheme="http" binding="basicHttpBinding" bindingConfiguration="shortTimeout" />  
    <add scheme="https" binding="basicHttpBinding" bindingConfiguration="Secure" />  
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
  
## <a name="see-also"></a>Consulte también

- [Configuración simplificada](simplified-configuration.md)
- [Enlaces proporcionados por el sistema](system-provided-bindings.md)
- [Información general acerca de la creación de puntos finales](endpoint-creation-overview.md)
- [Utilización de enlaces para configurar servicios y clientes](using-bindings-to-configure-services-and-clients.md)
