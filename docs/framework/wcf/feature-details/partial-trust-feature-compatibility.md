---
title: "Compatibilidad de caracter&#237;stica de confianza parcial | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a36a540b-1606-4e63-88e0-b7c59e0e6ab7
caps.latest.revision: 75
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 74
---
# Compatibilidad de caracter&#237;stica de confianza parcial
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] admite un subconjunto limitado de funcionalidad cuando se ejecuta en un entorno de confianza parcial. Las características admitidas en confianza parcial están diseñadas alrededor de un conjunto concreto de escenarios, tal y como se describe en el tema [Escenarios de implementación admitidos](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md).  
  
## Requisitos mínimos de permiso  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite un subconjunto de características en aplicaciones que se ejecutan bajo cualquiera de los conjuntos de permisos con nombre estándares:  
  
-   Permisos de nivel de confianza medio  
  
-   Permisos de zona de Internet  
  
 Al intentar usar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en aplicaciones de confianza parcial con permisos más restrictivos, pueden producirse excepciones de seguridad en tiempo de ejecución.  
  
## Contratos  
 Los contratos están sujetos a las restricciones siguientes cuando se ejecutan bajo confianza parcial:  
  
-   La clase de servicio que implementa la interfaz `[ServiceContract]` debe ser `public` y tener un constructor `public`. Si define los métodos `[OperationContract]`, éstos deben ser `public`. Si en su lugar implementa una interfaz `[ServiceContract]`, esas implementaciones de método pueden ser explícitas o `private`, siempre y cuando la interfaz `[ServiceContract]` sea `public`.  
  
-   Al usar el atributo `[ServiceKnownType]`, el método especificado debe ser `public`.  
  
-   Las clases `[MessageContract]` y sus miembros pueden ser `public`. Si la clase `[MessageContract]` se define en el ensamblado de aplicación puede ser `internal` y tener miembros `internal`.  
  
## Enlaces proporcionados por el sistema  
 <xref:System.ServiceModel.BasicHttpBinding> y <xref:System.ServiceModel.WebHttpBinding> se admiten totalmente en un entorno de confianza parcial.<xref:System.ServiceModel.WSHttpBinding> solo se admite para el modo de seguridad de transporte.  
  
 Los enlaces que utilizan transportes distintos a HTTP, como <xref:System.ServiceModel.NetTcpBinding>, <xref:System.ServiceModel.NetNamedPipeBinding>o <xref:System.ServiceModel.NetMsmqBinding>, no se admiten al ejecutarse en un entorno de confianza parcial.  
  
## Enlaces personalizados  
 Se pueden crear y usar enlaces personalizados en un entorno de confianza parcial, pero deben seguir las restricciones especificadas en esta sección.  
  
### Transportes  
 Los únicos elementos de enlace de transporte permitidos son <xref:System.ServiceModel.Channels.HttpTransportBindingElement> y <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.  
  
### Codificadores  
 Se permiten los codificadores siguientes:  
  
-   El codificador de texto \(<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>\).  
  
-   El codificador binario \(<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>\).  
  
-   El codificador del mensaje web \(<xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>\).  
  
 No se admiten los codificadores del mecanismo de optimización de transmisión del mensaje \(MTOM\).  
  
### Seguridad  
 Las aplicaciones de confianza parcial pueden utilizar las características de seguridad de nivel de transporte de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para proteger su comunicación. No se admite la seguridad de nivel de mensaje. Al configurar un enlace para que use la seguridad de nivel de mensaje, se produce una excepción en tiempo de ejecución.  
  
### Enlaces no admitidos  
 No se admiten los enlaces que utilizan mensajería confiable, transacciones o seguridad del nivel de mensaje.  
  
## Serialización  
 Tanto <xref:System.Runtime.Serialization.DataContractSerializer> como <xref:System.Xml.Serialization.XmlSerializer> se admiten en un entorno de confianza parcial. Sin embargo, el uso de <xref:System.Runtime.Serialization.DataContractSerializer> está sujeto a las condiciones siguientes:  
  
-   Todos los tipos `[DataContract]` serializables deben ser `public`.  
  
-   Todos los campos `[DataMember]` serializables o propiedades en un tipo `[DataContract]` deben ser públicos y de lectura\/escritura. No se admite la serialización y deserialización de los campos [readonly](http://go.microsoft.com/fwlink/?LinkID=98854) al ejecutar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en una aplicación de confianza parcial.  
  
-   El modelo de programación `[Serializable]`\/ISerializable no se admite en un entorno de confianza parcial.  
  
-   Los tipos conocidos se deben especificar mediante código o configuración del nivel de equipo \(machine.config\). Los tipos conocidos no se pueden especificar en la configuración del nivel de de aplicación por razones de seguridad.  
  
-   Los tipos que implementan <xref:System.Runtime.Serialization.IObjectReference> inician una excepción en un entorno de confianza parcial.  
  
 Consulte la sección relativa a la serialización en el tema [Procedimientos recomendados de confianza parcial](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) para obtener más información sobre la seguridad al usar <xref:System.Runtime.Serialization.DataContractSerializer> de manera segura en una aplicación de confianza parcial.  
  
### Tipos de colección  
 Algunos tipos de colección implementan <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.Collections.IEnumerable>. Los ejemplos incluyen tipos que implementan <xref:System.Collections.Generic.ICollection%601>. Tales tipos pueden implementar una implementación `public` de `GetEnumerator()`y una implementación explícita de `GetEnumerator()`. En este caso, <xref:System.Runtime.Serialization.DataContractSerializer> invoca la implementación `public` de `GetEnumerator()`y no la implementación explícita de `GetEnumerator()`. Si ninguna de las implementaciones de `GetEnumerator()` es `public` y todas son implementaciones explícitas, <xref:System.Runtime.Serialization.DataContractSerializer> invoca a `IEnumerable.GetEnumerator()`.  
  
 Para los tipos de colección cuando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se está ejecutando en un entorno de confianza parcial, si ninguna de las implementaciones `GetEnumerator()` es `public`, o ninguna de ellas es  una implementación de interfaz explícita, se producirá una excepción de seguridad.  
  
### NetDataContractSerializer  
 <xref:System.Collections.Generic.List%601> no admite muchos tipos de colección de .NET Framework, como <xref:System.Collections.ArrayList>, <xref:System.Collections.Generic.Dictionary%602>, <xref:System.Collections.Hashtable> y <xref:System.Runtime.Serialization.NetDataContractSerializer>, en un entorno de confianza parcial. Estos tipos tienen el atributo `[Serializable]` establecido y, tal y como se explicó previamente en la sección acerca de la serialización, este atributo no se admite en confianza parcial.<xref:System.Runtime.Serialization.DataContractSerializer> trata las colecciones de una manera especial y, por lo tanto, puede resolver esta restricción, pero <xref:System.Runtime.Serialization.NetDataContractSerializer> no tiene ningún mecanismo para evitarla.  
  
 <xref:System.DateTimeOffset> no admite el tipo <xref:System.Runtime.Serialization.NetDataContractSerializer> en confianza parcial.  
  
 No se puede usar un suplente con <xref:System.Runtime.Serialization.NetDataContractSerializer> \(mediante el mecanismo <xref:System.Runtime.Serialization.SurrogateSelector>\) cuando se ejecuta con confianza parcial. Observe que esta restricción se aplica al uso de un suplente, no a su serialización.  
  
## Habilitación de comportamientos habituales que se van a ejecutar  
 Los comportamientos de servicio o de extremo que no están marcados con el atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute> \(APTCA\) y que se agregan a la sección [\<commonBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) de un archivo de configuración no se ejecutan cuando la aplicación se ejecuta en un entorno de confianza parcial y no se inicia ninguna excepción cuando esto ocurre. Para forzar la ejecución de los comportamientos habituales, debe realizar una de las siguientes opciones:  
  
-   Marcar el comportamiento habitual con el atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute> de modo que pueda ejecutarse cuando se implementa como una aplicación de confianza parcial. Tenga en cuenta que puede establecerse una entrada de registro en el equipo para evitar que se ejecuten los ensamblados marcados con APTCA. .  
  
-   Asegurarse de implementar la aplicación como una aplicación de confianza total en la que los usuarios no pueden modificar los valores de la seguridad de acceso del código para ejecutar la aplicación en un entorno de confianza parcial. De poder hacerlo, el comportamiento no se ejecutaría y no se iniciaría ninguna excepción. Para asegurarse, consulte la opción **levelfinal** mediante [Caspol.exe \(Code Access Security Policy Tool\)](../../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md).  
  
 [!INCLUDE[crexample](../../../../includes/crexample-md.md)] un comportamiento común, consulte [Cómo bloquear extremos en la empresa](../../../../docs/framework/wcf/extending/how-to-lock-down-endpoints-in-the-enterprise.md).  
  
## Configuración  
 Con una sola excepción, el código de confianza parcial solo puede cargar secciones de configuración de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en el archivo `app.config` local. Para cargar las secciones de configuración de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que hacen referencia a las secciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en machine.config o en un archivo web.config raíz requiere ConfigurationPermission \(sin restricciones\). Sin este permiso, las referencias a las secciones de configuración de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \(comportamientos, enlaces\) fuera del archivo de configuración local producen una excepción cuando se carga la configuración.  
  
 La única excepción es la configuración de tipos conocidos para la serialización, tal y como se describe en la sección relativa a la serialización de este tema.  
  
> [!IMPORTANT]
>  Las extensiones de configuración solo se admiten cuando se ejecutan bajo plena confianza.  
  
## Diagnóstico  
  
### Registro de eventos  
 El registro de eventos limitado se admite bajo confianza parcial. En el registro de eventos solo se registran los errores de activación de servicio y los errores de registro de seguimiento\/mensajes. El número máximo de eventos que se pueden registrar por proceso es 5, para evitar que se escriban demasiados mensajes en el registro de eventos.  
  
### Registro de mensajes  
 El registro de mensajes no funciona cuando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se ejecuta en un entorno de confianza parcial. Si está habilitado bajo confianza parcial, no produce un error en la activación del servicio, pero no se registra ningún mensaje.  
  
### Traza  
 La funcionalidad de seguimiento restringido está disponible al ejecutarse en un entorno de confianza parcial. En el elemento \<`listeners`\> del archivo de configuración, los únicos tipos que puede agregar son <xref:System.Diagnostics.TextWriterTraceListener> y el nuevo <xref:System.Diagnostics.EventSchemaTraceListener>. El uso del <xref:System.Diagnostics.XmlWriterTraceListener> estándar puede producir registros incompletos o incorrectos.  
  
 Los orígenes de seguimiento admitidos son:  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.Runtime.Serialization>  
  
-   <xref:System.IdentityModel.Claims>, <xref:System.IdentityModel.Policy>, <xref:System.IdentityModel.Selectors> y <xref:System.IdentityModel.Tokens>.  
  
 No se admiten los siguientes orígenes de seguimiento:  
  
-   CardSpace  
  
-   <xref:System.IO.Log>  
  
-   <xref:System.ServiceModel.Internal.TransactionBridge>  
  
 No se deben especificar los siguientes miembros de la enumeración <xref:System.Diagnostics.TraceOptions>:  
  
-   <xref:System.Diagnostics.TraceOptions>  
  
-   <xref:System.Diagnostics.TraceOptions.ProcessID>  
  
 Al utilizar el seguimiento en un entorno de confianza parcial, asegúrese de que la aplicación tiene los permisos necesarios para almacenar el resultado del agente de escucha de seguimiento. Por ejemplo, al utilizar <xref:System.Diagnostics.TextWriterTraceListener> para escribir el resultado de seguimiento en un archivo de texto, asegúrese de que la aplicación tiene el FileIOPermission necesario exigido para escribir correctamente en el archivo de seguimiento.  
  
> [!NOTE]
>  Para evitar inundar los archivos de seguimiento con errores duplicados, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deshabilita el seguimiento del recurso o acción después del primer error de seguridad. Hay un seguimiento de excepción para cada acceso erróneo a recurso la primera vez que se realiza un intento de tener acceso al recurso o realizar la acción.  
  
## Host de servicio de WCF  
 El host de servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admite la confianza parcial. Si desea usar un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con confianza parcial, no use la plantilla de proyecto de biblioteca de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] para crear el servicio. En su lugar, cree un nuevo sitio web en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], eligiendo la plantilla de sitio web de servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], que puede hospedar el servicio en un servidor web en el que se admita la confianza parcial de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Otras limitaciones  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generalmente se limita a las consideraciones de seguridad impuestas en él por la aplicación de hospedaje. Por ejemplo, si [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se hospeda en una Aplicación Explorador de XAML \(XBAP\), está sujeto a las limitaciones de XBAP, como se describe en [Seguridad de confianza parcial en Windows Presentation Foundation](http://go.microsoft.com/fwlink/?LinkId=89138).  
  
 Las características adicionales siguientes no están habilitadas al ejecutar indigo2 en un entorno de confianza parcial:  
  
-   Instrumental de administración de Windows \(WMI\)  
  
-   El registro de eventos solo está parcialmente habilitado \(consulte la explicación en la sección **Diagnósticos**\).  
  
-   Contadores de rendimiento  
  
 El uso de características [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que no se admiten en un entorno de confianza parcial puede producir excepciones en tiempo de ejecución.  
  
## Características no enumeradas  
 La mejor manera de detectar que una parte de la información o acción no está disponible al ejecutarse en un entorno de confianza parcial es intentar tener acceso al recurso o realizar la acción dentro de un bloque `try`, y, a continuación, `catch` el error. Para evitar inundar los archivos de seguimiento con errores duplicados, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deshabilita el seguimiento del recurso o acción después del primer error de seguridad. Hay un seguimiento de excepción para cada acceso erróneo a recurso la primera vez que se realiza un intento de tener acceso al recurso o realizar la acción.  
  
## Vea también  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>   
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>   
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>   
 [Escenarios de implementación admitidos](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)   
 [Procedimientos recomendados de confianza parcial](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md)