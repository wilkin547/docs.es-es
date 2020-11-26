---
title: Compatibilidad de característica de confianza parcial
ms.date: 03/30/2017
ms.assetid: a36a540b-1606-4e63-88e0-b7c59e0e6ab7
ms.openlocfilehash: baf7758bc83419a68f900aa51233006ecb61d8e0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247998"
---
# <a name="partial-trust-feature-compatibility"></a>Compatibilidad de característica de confianza parcial

Windows Communication Foundation (WCF) admite un subconjunto limitado de funcionalidad cuando se ejecuta en un entorno de confianza parcial. Las características admitidas en confianza parcial están diseñadas alrededor de un conjunto concreto de escenarios, tal y como se describe en el tema [Supported Deployment Scenarios](supported-deployment-scenarios.md) .  
  
## <a name="minimum-permission-requirements"></a>Requisitos mínimos de permiso  

 WCF admite un subconjunto de características en aplicaciones que se ejecutan en cualquiera de los siguientes conjuntos de permisos con nombre estándar:  
  
- Permisos de nivel de confianza medio  
  
- Permisos de zona de Internet  
  
 Si se intenta usar WCF en aplicaciones de confianza parcial con permisos más restrictivos, pueden producirse excepciones de seguridad en tiempo de ejecución.  
  
## <a name="contracts"></a>Contratos  

 Los contratos están sujetos a las restricciones siguientes cuando se ejecutan bajo confianza parcial:  
  
- La clase de servicio que implementa la interfaz `[ServiceContract]` debe ser `public` y tener un constructor `public` . Si define los métodos `[OperationContract]` , éstos deben ser `public`. Si en su lugar implementa una interfaz `[ServiceContract]` , esas implementaciones de método pueden ser explícitas o `private`, siempre y cuando la interfaz `[ServiceContract]` sea `public`.  
  
- Al usar el atributo `[ServiceKnownType]` , el método especificado debe ser `public`.  
  
- Las clases`[MessageContract]` y sus miembros pueden ser `public`. Si la clase `[MessageContract]` se define en el ensamblado de aplicación puede ser `internal` y tener miembros `internal` .  
  
## <a name="system-provided-bindings"></a>Enlaces proporcionados por el sistema  

 <xref:System.ServiceModel.BasicHttpBinding> y <xref:System.ServiceModel.WebHttpBinding> se admiten totalmente en un entorno de confianza parcial. <xref:System.ServiceModel.WSHttpBinding> solo se admite para el modo de seguridad de transporte.  
  
 Los enlaces que utilizan transportes distintos a HTTP, como <xref:System.ServiceModel.NetTcpBinding>, <xref:System.ServiceModel.NetNamedPipeBinding>o <xref:System.ServiceModel.NetMsmqBinding>, no se admiten al ejecutarse en un entorno de confianza parcial.  
  
## <a name="custom-bindings"></a>Enlaces personalizados  

 Se pueden crear y usar enlaces personalizados en un entorno de confianza parcial, pero deben seguir las restricciones especificadas en esta sección.  
  
### <a name="transports"></a>Transportes  

 Los únicos elementos de enlace de transporte permitidos son <xref:System.ServiceModel.Channels.HttpTransportBindingElement> y <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.  
  
### <a name="encoders"></a>Codificadores  

 Se permiten los codificadores siguientes:  
  
- El codificador de texto (<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>).  
  
- El codificador binario (<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>).  
  
- El codificador del mensaje web (<xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>).  
  
 No se admiten los codificadores del mecanismo de optimización de transmisión del mensaje (MTOM).  
  
### <a name="security"></a>Seguridad  

 Las aplicaciones de confianza parcial pueden utilizar las características de seguridad de nivel de transporte de WCF para proteger su comunicación. No se admite la seguridad de nivel de mensaje. Al configurar un enlace para que use la seguridad de nivel de mensaje, se produce una excepción en tiempo de ejecución.  
  
### <a name="unsupported-bindings"></a>Enlaces no admitidos  

 No se admiten los enlaces que utilizan mensajería confiable, transacciones o seguridad del nivel de mensaje.  
  
## <a name="serialization"></a>Serialización  

 Tanto <xref:System.Runtime.Serialization.DataContractSerializer> como <xref:System.Xml.Serialization.XmlSerializer> se admiten en un entorno de confianza parcial. Sin embargo, el uso de <xref:System.Runtime.Serialization.DataContractSerializer> está sujeto a las condiciones siguientes:  
  
- Todos los tipos `[DataContract]` serializables deben ser `public`.  
  
- Todos los campos `[DataMember]` serializables o propiedades en un tipo `[DataContract]` deben ser públicos y de lectura/escritura. No se admite la serialización y deserialización de campos de [solo lectura](https://go.microsoft.com/fwlink/?LinkID=98854) cuando se ejecuta WCF en una aplicación de confianza parcial.  
  
- El modelo de programación `[Serializable]`/ISerializable no se admite en un entorno de confianza parcial.  
  
- Los tipos conocidos se deben especificar mediante código o configuración del nivel de equipo (machine.config). Los tipos conocidos no se pueden especificar en la configuración del nivel de de aplicación por razones de seguridad.  
  
- Los tipos que implementan <xref:System.Runtime.Serialization.IObjectReference> inician una excepción en un entorno de confianza parcial.  
  
 Consulte la sección relativa a la serialización en el tema [Partial Trust Best Practices](partial-trust-best-practices.md) para obtener más información sobre la seguridad al usar <xref:System.Runtime.Serialization.DataContractSerializer> de manera segura en una aplicación de confianza parcial.  
  
### <a name="collection-types"></a>Tipos de colección  

 Algunos tipos de colección implementan <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.Collections.IEnumerable>. Los ejemplos incluyen tipos que implementan <xref:System.Collections.Generic.ICollection%601>. Tales tipos pueden implementar una implementación `public` de `GetEnumerator()`y una implementación explícita de `GetEnumerator()`. En este caso, <xref:System.Runtime.Serialization.DataContractSerializer> invoca la implementación `public` de `GetEnumerator()`y no la implementación explícita de `GetEnumerator()`. Si ninguna de las implementaciones de `GetEnumerator()` es `public` y todas son implementaciones explícitas, <xref:System.Runtime.Serialization.DataContractSerializer> invoca a `IEnumerable.GetEnumerator()`.  
  
 En el caso de los tipos de colección cuando WCF se está ejecutando en un entorno de confianza parcial, si ninguna de las `GetEnumerator()` implementaciones es `public` , o ninguna de ellas son implementaciones de interfaz explícitas, se produce una excepción de seguridad.  
  
### <a name="netdatacontractserializer"></a>NetDataContractSerializer  

 <xref:System.Collections.Generic.List%601>no admite muchos tipos de colección de .NET Framework, como <xref:System.Collections.ArrayList>, <xref:System.Collections.Generic.Dictionary%602> , <xref:System.Collections.Hashtable> y <xref:System.Runtime.Serialization.NetDataContractSerializer> , en un entorno de confianza parcial. Estos tipos tienen el atributo `[Serializable]` establecido y, tal y como se explicó previamente en la sección acerca de la serialización, este atributo no se admite en confianza parcial. <xref:System.Runtime.Serialization.DataContractSerializer> trata las colecciones de una manera especial y, por lo tanto, puede resolver esta restricción, pero <xref:System.Runtime.Serialization.NetDataContractSerializer> no tiene ningún mecanismo para evitarla.  
  
 <xref:System.DateTimeOffset> no admite el tipo <xref:System.Runtime.Serialization.NetDataContractSerializer> en confianza parcial.  
  
 No se puede usar un suplente con <xref:System.Runtime.Serialization.NetDataContractSerializer> (mediante el mecanismo <xref:System.Runtime.Serialization.SurrogateSelector> ) cuando se ejecuta con confianza parcial. Observe que esta restricción se aplica al uso de un suplente, no a su serialización.  
  
## <a name="enabling-common-behaviors-to-run"></a>Habilitación de comportamientos habituales que se van a ejecutar  

 Los comportamientos de servicio o de extremo que no están marcados con el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo (APTCA) que se agregan a la [\<commonBehaviors>](../../configure-apps/file-schema/wcf/commonbehaviors.md) sección de un archivo de configuración no se ejecutan cuando la aplicación se ejecuta en un entorno de confianza parcial y no se produce ninguna excepción cuando esto ocurre. Para forzar la ejecución de los comportamientos habituales, debe realizar una de las siguientes opciones:  
  
- Marcar el comportamiento habitual con el atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute> de modo que pueda ejecutarse cuando se implementa como una aplicación de confianza parcial. Tenga en cuenta que puede establecerse una entrada de registro en el equipo para evitar que se ejecuten los ensamblados marcados con APTCA. .  
  
- Asegurarse de implementar la aplicación como una aplicación de confianza total en la que los usuarios no pueden modificar los valores de la seguridad de acceso del código para ejecutar la aplicación en un entorno de confianza parcial. De poder hacerlo, el comportamiento no se ejecutaría y no se iniciaría ninguna excepción. Para asegurarse de esto, vea la opción **LevelFinal** mediante [Caspol.exe (herramienta de la Directiva de seguridad de acceso del código)](../../tools/caspol-exe-code-access-security-policy-tool.md).  
  
 Para obtener un ejemplo de un comportamiento común, consulte [Cómo: bloquear puntos de conexión en la empresa](../extending/how-to-lock-down-endpoints-in-the-enterprise.md).  
  
## <a name="configuration"></a>Configuración  

 Con una excepción, el código de confianza parcial solo puede cargar secciones de configuración de WCF en el `app.config` archivo local. Para cargar las secciones de configuración de WCF que hacen referencia a las secciones de WCF en machine.config o en un archivo de web.config raíz, se requiere ConfigurationPermission (Unrestricted). Sin este permiso, las referencias a las secciones de configuración de WCF (comportamientos, enlaces) fuera del archivo de configuración local producen una excepción cuando se carga la configuración.  
  
 La única excepción es la configuración de tipos conocidos para la serialización, tal y como se describe en la sección relativa a la serialización de este tema.  
  
> [!IMPORTANT]
> Las extensiones de configuración solo se admiten cuando se ejecutan bajo plena confianza.  
  
## <a name="diagnostics"></a>Diagnóstico  
  
### <a name="event-logging"></a>Registro de eventos  

 El registro de eventos limitado se admite bajo confianza parcial. En el registro de eventos solo se registran los errores de activación de servicio y los errores de registro de seguimiento/mensajes. El número máximo de eventos que se pueden registrar por proceso es 5, para evitar que se escriban demasiados mensajes en el registro de eventos.  
  
### <a name="message-logging"></a>Registro de mensajes  

 El registro de mensajes no funciona cuando se ejecuta WCF en un entorno de confianza parcial. Si está habilitado bajo confianza parcial, no produce un error en la activación del servicio, pero no se registra ningún mensaje.  
  
### <a name="tracing"></a>Seguimiento  

 La funcionalidad de seguimiento restringido está disponible al ejecutarse en un entorno de confianza parcial. En el `listeners` elemento <> del archivo de configuración, los únicos tipos que puede Agregar son <xref:System.Diagnostics.TextWriterTraceListener> y el nuevo <xref:System.Diagnostics.EventSchemaTraceListener> . El uso del <xref:System.Diagnostics.XmlWriterTraceListener> estándar puede producir registros incompletos o incorrectos.  
  
 Los orígenes de seguimiento admitidos son:  
  
- <xref:System.ServiceModel>  
  
- <xref:System.Runtime.Serialization>  
  
- <xref:System.IdentityModel.Claims>, <xref:System.IdentityModel.Policy>, <xref:System.IdentityModel.Selectors> y <xref:System.IdentityModel.Tokens>.  
  
 No se admiten los siguientes orígenes de seguimiento:  
  
- CardSpace  
  
- <xref:System.IO.Log>  

- [System. ServiceModel. Internal. TransactionBridge](/previous-versions/aa346556(v=vs.110))]
  
 No se deben especificar los siguientes miembros de la enumeración <xref:System.Diagnostics.TraceOptions> :  
  
- <xref:System.Diagnostics.TraceOptions.Callstack?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceOptions.ProcessId?displayProperty=nameWithType>  
  
 Al utilizar el seguimiento en un entorno de confianza parcial, asegúrese de que la aplicación tiene los permisos necesarios para almacenar el resultado del agente de escucha de seguimiento. Por ejemplo, al utilizar <xref:System.Diagnostics.TextWriterTraceListener> para escribir el resultado de seguimiento en un archivo de texto, asegúrese de que la aplicación tiene el FileIOPermission necesario exigido para escribir correctamente en el archivo de seguimiento.  
  
> [!NOTE]
> Para evitar inundar los archivos de seguimiento con errores duplicados, WCF deshabilita el seguimiento del recurso o de la acción después del primer error de seguridad. Hay un seguimiento de excepción para cada acceso erróneo a recurso la primera vez que se realiza un intento de tener acceso al recurso o realizar la acción.  
  
## <a name="wcf-service-host"></a>Host de servicio de WCF  

 El host de servicio WCF no admite la confianza parcial. Si desea usar un servicio WCF en confianza parcial, no use la plantilla de proyecto Biblioteca de servicios WCF de Visual Studio para compilar el servicio. En su lugar, cree un nuevo sitio web en Visual Studio; para ello, elija la plantilla sitio web del servicio WCF, que puede hospedar el servicio en un servidor Web en el que se admita la confianza parcial de WCF.  
  
## <a name="other-limitations"></a>Otras limitaciones  

  WCF generalmente se limita a las consideraciones de seguridad impuestas por la aplicación de hospedaje. Por ejemplo, si WCF se hospeda en una aplicación de explorador XAML (XBAP), está sujeto a las limitaciones de XBAP, como se describe en [Windows Presentation Foundation la seguridad de confianza parcial](/dotnet/desktop/wpf/wpf-partial-trust-security).  
  
 Las características adicionales siguientes no están habilitadas al ejecutar indigo2 en un entorno de confianza parcial:  
  
- Instrumental de administración de Windows (WMI)  
  
- El registro de eventos solo está parcialmente habilitado (consulte la explicación en la sección **Diagnósticos** ).  
  
- Contadores de rendimiento  
  
 El uso de las características de WCF que no se admiten en un entorno de confianza parcial puede producir excepciones en tiempo de ejecución.  
  
## <a name="unlisted-features"></a>Características no enumeradas  

 La mejor manera de detectar que una parte de la información o acción no está disponible al ejecutarse en un entorno de confianza parcial es intentar tener acceso al recurso o realizar la acción dentro de un bloque `try` , y, a continuación, `catch` el error. Para evitar inundar los archivos de seguimiento con errores duplicados, WCF deshabilita el seguimiento del recurso o de la acción después del primer error de seguridad. Hay un seguimiento de excepción para cada acceso erróneo a recurso la primera vez que se realiza un intento de tener acceso al recurso o realizar la acción.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [Escenarios de implementación admitidos](supported-deployment-scenarios.md)
- [Procedimientos recomendados de confianza parcial](partial-trust-best-practices.md)
