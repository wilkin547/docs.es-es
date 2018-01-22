---
title: "Configuración de servicios mediante archivos de configuración"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 93dc8119e76f5c9cbff5c91a7e5d0cde3b0072f2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="configuring-services-using-configuration-files"></a>Configuración de servicios mediante archivos de configuración
Configurar un servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] con un archivo de configuración le da la flexibilidad de proporcionar datos de extremo y comportamiento del servicio en el punto de implementación en lugar de hacerlo en la fase de diseño. En este tema se describen las principales técnicas disponibles.  
  
 Se puede configurar un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] mediante la tecnología de configuración [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] . Por lo general, los elementos XML se agregan al archivo Web.config para un sitio de Internet Information Services (IIS) que hospeda un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] . Los elementos le permiten cambiar detalles como las direcciones de extremos (las direcciones reales utilizadas para comunicarse con el servicio) equipo a equipo. Además, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] incluye varios elementos proporcionados por el sistema que le permiten seleccionar rápidamente las características más básicas de un servicio. A partir de [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] incluye un nuevo modelo de configuración predeterminado que simplifica los requisitos de configuración de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] . Si no se proporciona ninguna configuración de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para un servicio concreto, el tiempo de ejecución lo configurará automáticamente con varios extremos estándar y un enlace/comportamiento predeterminado. En la práctica, escribir la configuración es una parte principal de la programación de aplicaciones de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Configurar enlaces para los servicios](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md). [!INCLUDE[crlist](../../../includes/crlist-md.md)] de los elementos más usados, consulte [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)] los puntos de conexión, enlaces y comportamientos predeterminados, consulte [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!IMPORTANT]
>  Al implementar escenarios en paralelo con dos versiones diferentes de un servicio, es necesario especificar los nombres parciales de los ensamblados a los que se hace referencia en los archivos de configuración. Esto se debe a que el archivo de configuración se comparte entre todas las versiones de un servicio y se podrían estar ejecutando con versiones diferentes de .NET Framework.  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a>System.Configuration: Web.config y App.config  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] utiliza el sistema de configuración System.Configuration de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
 Al configurar un servicio en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], utilice un archivo Web.config o un archivo App.config para especificar los valores. El entorno de hospedaje determina la elección realizada del nombre del archivo de configuración para el servicio. Si está utilizando IIS para hospedar su servicio, utilice un archivo Web.config. Si está utilizando cualquier otro entorno de hospedaje, utilice un archivo App.config.  
  
 En [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], el archivo denominado App.config se utiliza para crear el archivo de configuración final. El nombre final realmente utilizado para la configuración depende del nombre de ensamblado. Por ejemplo, un ensamblado denominado "Cohowinery.exe" tiene un nombre final de archivo de configuración de "Cohowinery.exe.config". Sin embargo, solo necesita modificar el archivo App.config. Los cambios realizados en ese archivo se realizan automáticamente en tiempo de compilación en el archivo final de configuración de la aplicación.  
  
 Al utilizar un archivo App.config, el sistema de configuración combina el archivo App.config con el contenido del archivo Machine.config cuando se inicia la aplicación y se aplica la configuración. Este mecanismo permite definir los valores de equipo en el archivo Machine.config. El archivo App.config se puede utilizar para reemplazar los valores del archivo Machine.config; también puede bloquear los valores en el archivo Machine.config para que se utilicen. En el caso de Web.config, el sistema de configuración combina los archivos Web.config de todos los directorios que conducen al directorio de la aplicación en la configuración que se aplica. [!INCLUDE[crabout](../../../includes/crabout-md.md)] la configuración y las prioridades de los valores, vea temas sobre el espacio de nombres <xref:System.Configuration> .  
  
## <a name="major-sections-of-the-configuration-file"></a>Secciones principales del archivo de configuración  
 Las secciones principales del archivo de configuración incluyen los elementos siguientes.  
  
```xml  
<system.ServiceModel>  
  
   <services>  
   <!—- Define the service endpoints. This section is optional in the new  
    default configuration model in .NET Framework 4. -->  
      <service>  
         <endpoint/>  
      </service>  
   </services>  
  
   <bindings>  
   <!-- Specify one or more of the system-provided binding elements,  
    for example, <basicHttpBinding> -->   
   <!-- Alternatively, <customBinding> elements. -->  
      <binding>  
      <!-- For example, a <BasicHttpBinding> element. -->  
      </binding>  
   </bindings>  
  
   <behaviors>  
   <!-- One or more of the system-provided or custom behavior elements. -->  
      <behavior>  
      <!-- For example, a <throttling> element. -->  
      </behavior>  
   </behaviors>  
  
</system.ServiceModel>  
```  
  
> [!NOTE]
>  Las secciones de enlaces y comportamientos son opcionales y solo se incluyen si son necesarias.  
  
### <a name="the-services-element"></a>El \<services > elemento  
 El elemento `services` contiene las especificaciones para todos los servicios que la aplicación hospeda. A partir del modelo de configuración simplificado de [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], esta sección es opcional.  
  
 [\<services>](../../../docs/framework/configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a>El \<servicio > elemento  
 Cada elemento service tiene estos atributos:  
  
-   `name`. Especifica el tipo que proporciona una implementación de un contrato de servicios. Este es un nombre completo que consta del espacio de nombres, un punto y el nombre del tipo. Por ejemplo, `"MyNameSpace.myServiceType"`.  
  
-   `behaviorConfiguration`. Especifica el nombre de uno de los elementos `behavior` encontrados en el elemento `behaviors` . El comportamiento especificado rige las acciones como si el servicio permitiese la suplantación. Si su valor es el nombre vacío o no se proporciona ningún atributo `behaviorConfiguration` , se agrega al servicio el conjunto predeterminado de comportamientos de servicio.  
  
-   [\<service>](../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a>El \<extremo > elemento  
 Cada extremo requiere una dirección, un enlace y un contrato, que están representados por los atributos siguientes:  
  
-   `address`. Especifica el Identificador uniforme de recursos (URI) del servicio, que puede ser una dirección absoluta o una relativa a la dirección base del servicio. Si está establecido en una cadena vacía, indica que el extremo está disponible en la dirección base que se especifica al crear <xref:System.ServiceModel.ServiceHost> para el servicio.  
  
-   `binding`. Normalmente especifica un enlace proporcionado por el sistema como <xref:System.ServiceModel.WSHttpBinding>, pero también puede especificar un enlace definido por el usuario. El enlace especificado determina el tipo de transporte, seguridad y codificación utilizados y si se admiten o habilitan sesiones confiables, transacciones, o la transmisión por secuencias.  
  
-   `bindingConfiguration`. Si se deben modificar los valores predeterminados de un enlace, esto se puede hacer configurando el elemento de `binding` adecuado en el elemento `bindings` . Este atributo debería recibir el mismo valor que el atributo `name` del elemento de `binding` que se utiliza para cambiar los valores predeterminados. Si no se proporciona ningún nombre, o no se especifica ningún atributo `bindingConfiguration` en el enlace, se usa el enlace predeterminado del tipo de enlace en el extremo.  
  
-   `contract`. Especifica la interfaz que define el contrato. Ésta es la interfaz implementada en el tipo de Common Language Runtime (CLR) especificado por el atributo `name` del elemento `service` .  
  
-   [\<punto de conexión > referencia del elemento](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)  
  
### <a name="the-bindings-element"></a>El \<enlaces > elemento  
 El elemento `bindings` contiene las especificaciones para todos los enlaces que puede utilizar cualquier extremo definido en cualquier servicio.  
  
 [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a>El \<enlace > elemento  
 El elemento `binding` contenidos en el elemento `bindings` pueden ser uno de los enlaces proporcionados por el sistema (consulte [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md)) o un enlace personalizado (consulte [Custom Bindings](../../../docs/framework/wcf/extending/custom-bindings.md)). El elemento `binding` tiene un atributo `name` que pone en correlación el enlace con el extremo especificado en el atributo `bindingConfiguration` del elemento `endpoint` . Si no se especifica ningún nombre, dicho enlace corresponde al enlace predeterminado de ese tipo de enlace.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]configurar los servicios y clientes, consulte [configuración de Windows Communication Foundation Applications](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).  
  
 [\<binding>](../../../docs/framework/misc/binding.md)  
  
### <a name="the-behaviors-element"></a>El \<comportamientos > elemento  
 Éste es un elemento contenedor para los elementos `behavior` que definen los comportamientos de un servicio.  
  
 [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a>La \<comportamiento > elemento  
 Cada elemento `behavior` lo identifica un atributo `name` y proporciona un comportamiento proporcionado por el sistema como <`throttling`> o bien, un comportamiento personalizado. Si no se especifica ningún nombre, dicho elemento de comportamiento corresponde al servicio predeterminado o al comportamiento de extremo.  
  
 [\<behavior>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a>Uso de las configuraciones de comportamientos y enlaces  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hace fácil compartir las configuraciones entre extremos utilizando un sistema de referencia en la configuración. En lugar de asignar directamente los valores de configuración a un extremo, los valores de configuración relacionados con el enlace se agrupan en elementos `bindingConfiguration` de la sección `<binding>` . Una configuración de enlace es un grupo con nombre de valores en un enlace. Entonces, los extremos pueden hacer referencia a `bindingConfiguration` por nombre.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
 <system.serviceModel>  
  <bindings>  
    <basicHttpBinding>  
     <binding name="myBindingConfiguration1" closeTimeout="00:01:00" />  
     <binding name="myBindingConfiguration2" closeTimeout="00:02:00" />  
     <binding closeTimeout="00:03:00" />  <!—- Default binding for basicHttpBinding -->  
    </basicHttpBinding>  
     </bindings>  
     <services>  
      <service name="MyNamespace.myServiceType">  
       <endpoint   
          address="myAddress" binding="basicHttpBinding"   
          bindingConfiguration="myBindingConfiguration1"  
          contract="MyContract"  />  
       <endpoint   
          address="myAddress2" binding="basicHttpBinding"   
          bindingConfiguration="myBindingConfiguration2"  
          contract="MyContract" />  
       <endpoint   
          address="myAddress3" binding="basicHttpBinding"   
          contract="MyContract" />  
       </service>  
      </services>  
    </system.serviceModel>  
</configuration>  
```  
  
 El `name` de la `bindingConfiguration` se establece en el elemento `<binding>` . El `name` debe ser una cadena única dentro del ámbito del tipo de enlace, en este caso el [< basicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), o un valor vacío para hacer referencia al enlace predeterminado. El extremo vincula a la configuración estableciendo el atributo `bindingConfiguration` en esta cadena.  
  
 Una `behaviorConfiguration` se implementa de la misma manera, tal y como se muestra en el ejemplo siguiente.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myBehavior">  
           <callbackDebug includeExceptionDetailInFaults="true" />  
         </behavior>  
      </endpointBehaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
  
    </behaviors>  
    <services>  
     <service name="NewServiceType">  
       <endpoint   
          address="myAddress3" behaviorConfiguration="myBehavior"  
          binding="basicHttpBinding"  
          contract="MyContract" />  
      </service>  
    </services>  
   </system.serviceModel>  
</configuration>  
```  
  
 Observe que el conjunto predeterminado de comportamientos de servicio se agrega al servicio. Este sistema permite a los extremos compartir configuraciones comunes sin volver a definir la configuración. Si se requiere el ámbito de equipo, cree el comportamiento de enlace o configuración en Machine.config. Los valores de configuración están disponibles en todos los archivos App.config. [Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) facilita la creación de configuraciones.  
  
## <a name="behavior-merge"></a>Combinación de comportamientos  
 La característica de combinación de comportamientos simplifica la administración de los comportamientos cuando se desea el uso coherente de un conjunto de comportamientos comunes. Esta característica permite especificar comportamientos en niveles diferentes de la jerarquía de configuración y hacer que los servicios hereden los comportamientos de varios niveles de la jerarquía de configuración. Para mostrar cómo funciona, supongamos que tiene el siguiente diseño de directorio virtual en IIS:  
  
 ~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc  
  
 Y el archivo ~\Web.config tiene el siguiente contenido:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 Y tiene un archivo Web.config secundario ubicado en ~\Child\Web.config con el siguiente contenido:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 El servicio ubicado en ~\Child\Service.svc se comportará como si tuviese los comportamientos de serviceMetadata y serviceDebug. El servicio ubicado en ~\Service.svc tendrá solo el comportamiento de serviceDebug. Lo que sucede es que se combinan las dos colecciones de comportamientos con el mismo nombre (en este caso, la cadena vacía).  
  
 También puede borrar colecciones de comportamientos mediante el \<borrar > etiquetar y quitar comportamientos individuales de la colección utilizando la \<quitar > etiqueta. Por ejemplo, las dos configuraciones siguientes hacen que el servicio secundario tenga únicamente el comportamiento de serviceMetadata:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <remove name="serviceDebug"/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <clear/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 La combinación de comportamientos se lleva a cabo para colecciones de comportamientos sin nombre, como se muestra arriba, y colecciones de comportamientos con nombre.  
  
 La combinación de comportamientos funciona en el entorno de hospedaje de IIS, en el cual los archivos Web.config se combinan jerárquicamente con el archivo Web.config raíz y machine.config. Pero también funciona en el entorno de la aplicación, donde machine.config se puede combinar con el archivo App.config.  
  
 La combinación de comportamientos se aplica a comportamientos de extremo y comportamientos de servicio en la configuración.  
  
 Si una colección de comportamientos secundarios contiene un comportamiento que ya se encuentra en la colección de comportamientos primarios, el comportamiento secundario invalida el primario. Por tanto, si una colección de comportamientos primarios tuviese `<serviceMetadata httpGetEnabled="False" />` y una colección de comportamientos secundarios tuviese `<serviceMetadata httpGetEnabled="True" />`, el comportamiento secundario invalidaría el comportamiento primario en la colección de comportamientos y httpGetEnabled sería "true".  
  
## <a name="see-also"></a>Vea también  
 [Configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md)  
 [Configurar aplicaciones de Windows Communication Foundation](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 [\<service>](../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
 [\<binding>](../../../docs/framework/misc/binding.md)
