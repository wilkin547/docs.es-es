---
title: Diseño de contratos de servicios
description: Obtenga información sobre los contratos de servicio, incluida la forma de crearlos, las operaciones y los tipos de datos disponibles, y otros aspectos de los contratos de servicio en la programación de WCF.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF]
ms.assetid: 8e89cbb9-ac84-4f0d-85ef-0eb6be0022fd
ms.openlocfilehash: 366157b86ed7c420aed9a3a70838b4d6cd1e451f
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245393"
---
# <a name="designing-service-contracts"></a>Diseño de contratos de servicios
En este tema se describe qué son los contratos de servicios, cómo se definen, qué operaciones están disponibles (y las implicaciones para los intercambios de mensajes subyacentes), qué tipos de datos se usan y otras cuestiones que le ayudan a diseñar operaciones que satisfagan adecuadamente los requisitos de su escenario.  
  
## <a name="creating-a-service-contract"></a>Crear un contrato de servicios  
 Los servicios exponen varias operaciones. En aplicaciones Windows Communication Foundation (WCF), defina las operaciones creando un método y marcándolos con el <xref:System.ServiceModel.OperationContractAttribute> atributo. A continuación, para crear un contrato de servicios, agrupe sus operaciones, declarándolas dentro de una interfaz marcada con el atributo <xref:System.ServiceModel.ServiceContractAttribute>, o bien definiéndolas en una clase marcada con el mismo atributo. (Para obtener un ejemplo básico, consulte [Cómo: definir un contrato de servicio](how-to-define-a-wcf-service-contract.md)).  
  
 Los métodos que no tienen un <xref:System.ServiceModel.OperationContractAttribute> atributo no son operaciones de servicio y no están expuestos por los servicios WCF.  
  
 Este tema describe los puntos de decisión siguientes al diseñar un contrato de servicios:  
  
- Si deben utilizarse clases o interfaces.  
  
- Cómo especificar los tipos de datos que desea intercambiar.  
  
- Los tipos de patrones de intercambio que puede utilizar.  
  
- Si puede hacer que los requisitos de seguridad explícitos sean parte del contrato.  
  
- Las restricciones para las entradas y salidas de la operación.  
  
## <a name="classes-or-interfaces"></a>Clases o interfaces  
 Tanto las clases como las interfaces representan una agrupación de funcionalidad y, por lo tanto, ambos se pueden utilizar para definir un contrato de servicio de WCF. Sin embargo, se recomienda que utilice las interfaces porque modelan directamente los contratos de servicios. Sin una implementación, las interfaces no hacen más que definir una agrupación de métodos con ciertas firmas. Implementar una interfaz de contrato de servicio y haber implementado un servicio WCF.  
  
 Todas las ventajas de las interfaces administradas se aplican a las interfaces de contrato de servicio:  
  
- Las interfaces del contrato de servicio pueden extender cualquier número de otras interfaces del contrato de servicio.  
  
- Una única clase puede implementar cualquier número de contratos de servicios implementando esas interfaces del contrato de servicio.  
  
- Puede modificar la implementación de un contrato de servicios cambiando la implementación de la interfaz, mientras el contrato de servicios sigue siendo el mismo.  
  
- Puede controlar la versión de su servicio implementando la interfaz antigua y la nueva. Los clientes antiguos se conectan a la versión original, mientras los clientes más nuevos pueden conectarse a la versión más nueva.  
  
> [!NOTE]
> Al heredar de otras interfaces del contrato de servicio, no puede invalidar las propiedades de operación, como el nombre o espacio de nombres. Si intenta hacerlo, crea una nueva operación en el contrato de servicios actual.  
  
 Para obtener un ejemplo del uso de una interfaz para crear un contrato de servicios, consulte [Cómo: crear un servicio con una interfaz de contrato](./feature-details/how-to-create-a-service-with-a-contract-interface.md).  
  
 Sin embargo, puede utilizar una clase para definir un contrato de servicios e implementar dicho contrato al mismo tiempo. La ventaja de crear sus servicios aplicando directamente <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> a la clase y los métodos en la clase, respectivamente, es la velocidad y la simplicidad. Las desventajas son que las clases administradas no admiten la herencia múltiple, y como resultado solo pueden implementar uno contrato de servicios a la vez. Además, cualquier modificación de las firmas de la clase o del método modifica el contrato público para ese servicio, lo que puede impedir que los clientes no modificados utilicen su servicio. Para obtener más información, consulte [implementación de contratos de servicio](implementing-service-contracts.md).  
  
 Para obtener un ejemplo en el que se usa una clase para crear un contrato de servicios e implementarlo al mismo tiempo, vea [Cómo: crear un servicio con una clase de contrato](./feature-details/how-to-create-a-wcf-contract-with-a-class.md).  
  
 En este punto, debería entender la diferencia entre definir su contrato de servicios utilizando una interfaz y utilizando una clase. El paso siguiente consiste en decidir qué datos se pueden intercambiar entre un servicio y sus clientes.  
  
## <a name="parameters-and-return-values"></a>Parámetros y valores devueltos  
 Cada operación devuelve un valor y un parámetro, incluso si estos no son más que `void`. Sin embargo, a diferencia de un método local, en el que puede pasar las referencias a los objetos de un objeto a otro, las operaciones del servicio no pasan las referencias a los objetos. En su lugar, pasan copias de los objetos.  
  
 Esto es significativo porque cada tipo utilizado en un parámetro o valor devuelto debe ser serializable; es decir, debe ser posible convertir un objeto de ese tipo en una secuencia de bytes y de una secuencia de bytes en un objeto.  
  
 Los tipos primitivos son serializables de forma predeterminada, como muchos tipos en .NET Framework.  
  
> [!NOTE]
> El valor de los nombres de parámetro en la firma de la operación forma parte del contrato y distingue entre mayúsculas y minúsculas. Si desea utilizar localmente el mismo nombre de parámetro pero modificar el nombre en los metadatos publicados, vea <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>.  
  
#### <a name="data-contracts"></a>Contratos de datos  
 Las aplicaciones orientadas a servicios como las aplicaciones de Windows Communication Foundation (WCF) están diseñadas para interoperar con el mayor número posible de aplicaciones cliente en plataformas de Microsoft y que no son de Microsoft. Para obtener la interoperabilidad más amplia posible, se recomienda que marque sus tipos con los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> para crear un contrato de datos, que es la parte del contrato de servicios que describe los datos que intercambian sus operaciones de servicio.  
  
 Los contratos de datos son contratos de estilo de participación: ningún tipo o miembro de datos se serializa a menos que aplique explícitamente el atributo de contrato de datos. Los contratos de datos no están relacionados con el ámbito de acceso del código administrado: los miembros de datos privados se pueden serializar y enviar a otra parte para obtener acceso a ellos públicamente. (Para obtener un ejemplo básico de un contrato de datos, consulte [Cómo: crear un contrato de datos básico para una clase o estructura](./feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)). WCF controla la definición de los mensajes SOAP subyacentes que habilitan la funcionalidad de la operación así como la serialización de los tipos de datos dentro y fuera del cuerpo de los mensajes. Siempre y cuando los tipos de datos sean serializables, no necesita pensar en la infraestructura de intercambio de mensajes subyacentes al diseñar las operaciones.  
  
 Aunque la aplicación WCF típica usa los <xref:System.Runtime.Serialization.DataContractAttribute> <xref:System.Runtime.Serialization.DataMemberAttribute> atributos y para crear contratos de datos para las operaciones, puede utilizar otros mecanismos de serialización. Los mecanismos estándares <xref:System.Runtime.Serialization.ISerializable>, <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.IXmlSerializable> trabajan para administrar la serialización de sus tipos de datos en los mensajes SOAP subyacentes que los llevan de una aplicación a otra. Puede emplear más estrategias de serialización si sus tipos de datos necesitan una compatibilidad especial. Para obtener más información sobre las opciones para la serialización de tipos de datos en aplicaciones WCF, vea [especificar transferencia de datos en contratos de servicio](./feature-details/specifying-data-transfer-in-service-contracts.md).  
  
#### <a name="mapping-parameters-and-return-values-to-message-exchanges"></a>Asignar los parámetros y los valores devueltos a los intercambios de mensajes  
 Las operaciones de servicio están soportadas por un intercambio subyacente de mensajes SOAP que transfiere los datos de la aplicación, además de los datos requeridos por la aplicación para soportar cierta seguridad estándar, transacción y características relacionadas con la sesión. Como este es el caso, la firma de una operación de servicio dicta un determinado *patrón de intercambio de mensajes* (MEP) subyacente que puede admitir la transferencia de datos y las características que requiere una operación. Puede especificar tres patrones en el modelo de programación de WCF: patrones de mensajes de solicitud/respuesta, unidireccionales y dúplex.  
  
##### <a name="requestreply"></a>Solicitud/Respuesta  
 Un patrón de solicitud/respuesta es uno en el que un remitente de la solicitud (una aplicación cliente) recibe una respuesta con la que está relacionada la solicitud. Este es el MEP predeterminado porque admite una operación en la que uno o más parámetros se pasan a la operación y se devuelve un valor de retorno al autor de llamada. Por ejemplo, en el ejemplo de código de C# siguiente, se muestra una operación de servicio básica que toma una cadena y devuelve una cadena.  
  
```csharp  
[OperationContractAttribute]  
string Hello(string greeting);  
```  
  
 A continuación, se muestra el código equivalente en Visual Basic.  
  
```vb  
<OperationContractAttribute()>  
Function Hello (ByVal greeting As String) As String  
```  
  
 Esta firma de operación dicta la forma del intercambio de mensajes subyacente. Si no existía ninguna correlación, WCF no puede determinar para qué operación está previsto el valor devuelto.  
  
 Tenga en cuenta que, a menos que especifique un patrón de mensaje subyacente diferente, incluso las operaciones de servicio que devuelven `void` ( `Nothing` en Visual Basic) son intercambios de mensajes de solicitud/respuesta. El resultado para su operación es que a menos que un cliente invoque de forma asincrónica la operación, el cliente detiene el procesamiento hasta que se reciba el mensaje de retorno, aunque ese mensaje esté normalmente vacío. En el ejemplo de código de C# siguiente, se muestra una operación que no regresa hasta que el cliente ha recibido un mensaje vacío como respuesta.  
  
```csharp  
[OperationContractAttribute]  
void Hello(string greeting);  
```  
  
 A continuación, se muestra el código equivalente en Visual Basic.  
  
```vb  
<OperationContractAttribute()>  
Sub Hello (ByVal greeting As String)  
```  
  
 El ejemplo anterior puede desacelerar rendimiento del cliente y la receptividad si la operación tarda mucho tiempo en realizarse, pero hay ventajas para las operaciones de solicitud/respuesta incluso cuando devuelven `void`. La más obvia es que los errores SOAP pueden devolverse en el mensaje de respuesta, lo que indica que se ha producido alguna condición de error relacionada con el servicio, bien en la comunicación bien en el procesamiento. Los errores SOAP que se especifican en un contrato de servicios se pasan a la aplicación cliente como un objeto <xref:System.ServiceModel.FaultException%601>, donde el parámetro de tipo es el tipo especificado en el contrato de servicios. Esto facilita la notificación de las condiciones de error en los servicios WCF. Para obtener más información sobre las excepciones, los errores de SOAP y el control de errores, vea [especificar y controlar errores en contratos y servicios](specifying-and-handling-faults-in-contracts-and-services.md). Para ver un ejemplo de un servicio de solicitud/respuesta y un cliente, consulte [Cómo: crear un contrato de solicitud-respuesta](./feature-details/how-to-create-a-request-reply-contract.md). Para obtener más información sobre los problemas con el patrón de solicitud-respuesta, vea [servicios de solicitud-respuesta](./feature-details/request-reply-services.md).  
  
##### <a name="one-way"></a>Unidireccional  
 Si el cliente de una aplicación de servicio WCF no debe esperar a que se complete la operación y no procesa los errores de SOAP, la operación puede especificar un patrón de mensaje unidireccional. Una operación unidireccional es aquella en la que un cliente invoca una operación y continúa el procesamiento después de que WCF escriba el mensaje en la red. Normalmente, esto significa que, salvo que los datos que se están enviando en el mensaje saliente sean extremadamente grandes, el cliente sigue ejecutándose de manera prácticamente inmediata (a menos que se produzca un error al enviar los datos). Este tipo de patrón de intercambio de mensajes soporta el comportamiento como evento de un cliente a una aplicación de servicio.  
  
 Un intercambio de mensajes en el que se envía un mensaje y no se recibe ninguno no puede soportar una operación de servicio que especifique un valor devuelto distinto de `void`; en este caso se inicia una excepción <xref:System.InvalidOperationException>.  
  
 Por lo tanto, ningún mensaje de retorno significa que no puede haber ningún error SOAP devuelto para indicar cualquier error en el procesamiento o la comunicación. (La comunicación de información de error cuando las operaciones son operaciones unidireccionales requiere un patrón de intercambio de mensajes dúplex.)  
  
 Para especificar un intercambio de mensajes unidireccional para una operación que devuelve `void`, establezca la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `true`, como en el ejemplo de código de C# siguiente.  
  
```csharp  
[OperationContractAttribute(IsOneWay=true)]  
void Hello(string greeting);  
```  
  
 A continuación, se muestra el código equivalente en Visual Basic.  
  
```vb  
<OperationContractAttribute(IsOneWay := True)>  
Sub Hello (ByVal greeting As String)  
```  
  
 Este método es idéntico al ejemplo de solicitud/respuesta anterior, pero estableciendo la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `true` significa que, aunque el método es idéntico, la operación de servicio no envía un mensaje de retorno y los clientes devuelven inmediatamente una vez el mensaje saliente se ha entregado al nivel del canal. Para obtener un ejemplo, vea [Cómo: crear un contrato unidireccional](./feature-details/how-to-create-a-one-way-contract.md). Para obtener más información sobre el patrón unidireccional, vea [servicios unidireccionales](./feature-details/one-way-services.md).  
  
##### <a name="duplex"></a>Dúplex  
 Un patrón dúplex se caracteriza por la capacidad tanto del servicio y como del cliente para enviarse mensajes entre sí independientemente de si se está utilizando una mensajería unidireccional o de solicitud/respuesta. Esta forma de comunicación bidireccional es útil para los servicios que deben comunicarse directamente con el cliente, o para proporcionar una experiencia asincrónica a cada lado de un intercambio de mensajes, incluido el comportamiento similar a un evento.  
  
 El patrón dúplex es ligeramente más complejo que los patrones de solicitud/respuesta o unidireccionales debido al mecanismo adicional para comunicarse con el cliente.  
  
 Para diseñar un contrato dúplex, también debe diseñar un contrato de devolución de llamada y asignar el tipo de ese contrato de devolución de llamada a la propiedad <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> del atributo <xref:System.ServiceModel.ServiceContractAttribute> que marca el contrato de servicio.  
  
 Para implementar un patrón dúplex, debe crear una segunda interfaz que contenga las declaraciones de método a las que se llaman en el cliente.  
  
 Para obtener un ejemplo de creación de un servicio y un cliente que tiene acceso a ese servicio, consulte [Cómo: crear un contrato dúplex](./feature-details/how-to-create-a-duplex-contract.md) y [Cómo: obtener acceso a los servicios con un contrato dúplex](./feature-details/how-to-access-services-with-a-duplex-contract.md). Para obtener un ejemplo funcional, vea [dúplex](./samples/duplex.md). Para obtener más información acerca de los problemas de uso de contratos dúplex, vea [servicios dúplex](./feature-details/duplex-services.md).  
  
> [!CAUTION]
> Cuando un servicio recibe un mensaje dúplex, examina el elemento `ReplyTo` en ese mensaje entrante para determinar dónde enviar la respuesta. Si no se protege el canal que se utiliza para recibir el mensaje, un cliente que no es de confianza podría enviar un mensaje malintencionado con un equipo de destino `ReplyTo`, provocando una denegación de servicio (DoS) de ese equipo de destino.  
  
##### <a name="out-and-ref-parameters"></a>Parámetros out y ref  
 En la mayoría de los casos, puede usar `in` los parámetros ( `ByVal` en Visual Basic) y `out` `ref` los parámetros ( `ByRef` en Visual Basic). Dado que tanto el parámetro `out` como `ref` indican que los datos son devueltos por una operación, una firma de operación como la siguiente especifica que se requiere una operación de solicitud/respuesta aunque la firma de la operación devuelva `void`.  
  
```csharp  
[ServiceContractAttribute]  
public interface IMyContract  
{  
  [OperationContractAttribute]  
  public void PopulateData(ref CustomDataType data);  
}  
```  
  
 A continuación, se muestra el código equivalente en Visual Basic.  
  
```vb  
<ServiceContractAttribute()> _  
Public Interface IMyContract  
  <OperationContractAttribute()> _  
  Public Sub PopulateData(ByRef data As CustomDataType)  
End Interface  
```  
  
 Las únicas excepciones son esos casos en los que su firma tiene una estructura determinada. Por ejemplo, solo puede utilizar el enlace <xref:System.ServiceModel.NetMsmqBinding> para comunicarse con los clientes si el método usado para declarar una operación devuelve `void`; no puede haber ningún valor de salida, tanto si se trata de un valor devuelto, `ref`, o bien un parámetro `out`.  
  
 Además, la utilización de los parámetros `out` o `ref` requiere que la operación tenga un mensaje de respuesta subyacente para devolver el objeto modificado. Si su operación es unidireccional, se inicia una excepción <xref:System.InvalidOperationException> en tiempo de ejecución.  
  
### <a name="specify-message-protection-level-on-the-contract"></a>Especificar el nivel de protección del mensaje en el contrato  
 Al diseñar su contrato, también debe decidir el nivel de protección del mensaje de los servicios que implementa su contrato. Esto solo es necesario si la seguridad del mensaje se aplica al enlace en el extremo del contrato. Si el enlace tiene la seguridad desactivada (es decir, si el enlace proporcionado por el sistema establece <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType> en el valor <xref:System.ServiceModel.SecurityMode.None?displayProperty=nameWithType>) no tiene que decidir sobre el nivel de protección del mensaje para el contrato. En la mayoría de los casos, los enlaces proporcionados por el sistema a los que se aplica la seguridad del nivel de mensaje, ofrecen un nivel de protección suficiente que hace innecesario el nivel de protección para cada operación o mensaje.  
  
 El nivel de protección es un valor que especifica si los mensajes (o partes del mensaje) que soportan un servicio están firmados, firmados y cifrados, o si se envían sin firmar o cifrar. El nivel de protección se puede establecer en varios ámbitos: en el nivel del servicio, para una operación determinada, para un mensaje dentro de esa operación, o una parte del mensaje. Los valores establecidos en un ámbito se convierten en el valor predeterminado para los ámbitos menores a menos que se invalide explícitamente. Si una configuración de enlace no puede proporcionar el nivel de protección mínimo necesario para el contrato, se produce una excepción. Y cuando ningún valor de nivel de protección se establece explícitamente en el contrato, la configuración de enlace controla el nivel de protección para todos los mensajes si el enlace tiene seguridad de mensajes. Este es el comportamiento predeterminado.  
  
> [!IMPORTANT]
> Decidir si establecer explícitamente varios ámbitos de un contrato en un nivel de protección inferior al nivel de protección completo de <xref:System.Net.Security.ProtectionLevel.EncryptAndSign?displayProperty=nameWithType> generalmente es una decisión que canjea cierto grado de seguridad por un aumento del rendimiento. En estos casos, las decisiones girarán en torno a las operaciones y al valor de los datos que intercambian. Para obtener más información, vea [proteger los servicios](securing-services.md).  
  
 Por ejemplo, el ejemplo de código siguiente no establece la propiedad <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> o <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel%2A> en el contrato.  
  
```csharp  
[ServiceContract]  
public interface ISampleService  
{  
  [OperationContractAttribute]  
  public string GetString();  
  
  [OperationContractAttribute]  
  public int GetInt();
}  
```  
  
 A continuación, se muestra el código equivalente en Visual Basic.  
  
```vb  
<ServiceContractAttribute()> _  
Public Interface ISampleService  
  
  <OperationContractAttribute()> _  
  Public Function GetString()As String  
  
  <OperationContractAttribute()> _  
  Public Function GetData() As Integer  
  
End Interface  
```  
  
 Al interactuar con una implementación `ISampleService` en un punto de conexión con un <xref:System.ServiceModel.WSHttpBinding> predeterminado (el <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>predeterminado, que es <xref:System.ServiceModel.SecurityMode.Message>), todos los mensajes se cifran y firman dado que es el nivel de protección predeterminado. No obstante, cuando se usa un servicio `ISampleService` con un <xref:System.ServiceModel.BasicHttpBinding> predeterminado (el <xref:System.ServiceModel.SecurityMode> predeterminado, que es <xref:System.ServiceModel.SecurityMode.None>), todos los mensajes se envían como texto, ya que no existe seguridad para este enlace y, por lo tanto, se pasa por alto el nivel de protección (es decir, los mensajes ni se cifran ni se firman). Si se cambia el <xref:System.ServiceModel.SecurityMode> a <xref:System.ServiceModel.SecurityMode.Message>, estos mensajes se cifrarían y firmarían (dado que ése sería el nivel de protección predeterminado del enlace).  
  
 Si desea especificar explícitamente o ajustar los requisitos de protección para su contrato, establezca la propiedad <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> (o cualquier de las propiedades `ProtectionLevel` en un ámbito menor) en el nivel que requiera su contrato de servicios. En este caso, utilizando un valor explícito exige al enlace que soporte ese valor como mínimo para el ámbito utilizado. Por ejemplo, el ejemplo de código siguiente especifica explícitamente un valor <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel%2A>, para la operación `GetGuid`.  
  
```csharp  
[ServiceContract]  
public interface IExplicitProtectionLevelSampleService  
{  
  [OperationContractAttribute]  
  public string GetString();  
  
  [OperationContractAttribute(ProtectionLevel=ProtectionLevel.None)]  
  public int GetInt();
  [OperationContractAttribute(ProtectionLevel=ProtectionLevel.EncryptAndSign)]  
  public int GetGuid();
}  
```  
  
 A continuación, se muestra el código equivalente en Visual Basic.  
  
```vb  
<ServiceContract()> _
Public Interface IExplicitProtectionLevelSampleService
    <OperationContract()> _
    Public Function GetString() As String
    End Function
  
    <OperationContract(ProtectionLevel := ProtectionLevel.None)> _
    Public Function GetInt() As Integer
    End Function
  
    <OperationContractAttribute(ProtectionLevel := ProtectionLevel.EncryptAndSign)> _
    Public Function GetGuid() As Integer
    End Function
  
End Interface  
```  
  
 Un servicio que implementa este contrato `IExplicitProtectionLevelSampleService` y tiene un extremo que utiliza el <xref:System.ServiceModel.WSHttpBinding> predeterminado (el <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>predeterminado, que es <xref:System.ServiceModel.SecurityMode.Message>) tiene el comportamiento siguiente:  
  
- Los mensajes de operación `GetString` se cifran y firman.  
  
- Los mensajes de operación `GetInt` se envían como texto sin cifrar ni firmar (es decir, texto sin formato).  
  
- La operación `GetGuid`<xref:System.Guid?displayProperty=nameWithType> se devuelve en un mensaje que se cifra y se firma.  
  
 Para obtener más información acerca de los niveles de protección y cómo usarlos, vea [Descripción del nivel de protección](understanding-protection-level.md). Para obtener más información acerca de la seguridad, consulte protección de los [servicios](securing-services.md).  
  
##### <a name="other-operation-signature-requirements"></a>Otros requisitos de firma de operación  
 Algunas características de aplicación requieren un tipo determinado de firma de la operación. Por ejemplo, el enlace <xref:System.ServiceModel.NetMsmqBinding> soporta los servicios duraderos y clientes, en los que una aplicación se puede reiniciar en el medio de la comunicación y se puede retomar donde se dejó sin olvidarse ningún mensaje. (Para obtener más información, vea [colas en WCF](./feature-details/queues-in-wcf.md)). Sin embargo, las operaciones duraderas deben tomar solo un `in` parámetro y no tener ningún valor devuelto.  
  
 Otro ejemplo es el uso de los tipos <xref:System.IO.Stream> en operaciones. Puesto que el parámetro <xref:System.IO.Stream> incluye el cuerpo completo del mensaje, si una entrada o una salida (es decir, parámetro `ref`, parámetro `out` o valor devuelto) es del tipo <xref:System.IO.Stream>, debe ser la única entrada o salida especificada en su operación. Además, el parámetro o el tipo devuelto debe ser <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> o <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType>. Para obtener más información sobre las secuencias, consulte [datos y streaming de gran tamaño](./feature-details/large-data-and-streaming.md).  
  
##### <a name="names-namespaces-and-obfuscation"></a>Nombres, espacios de nombres y ofuscación  
 Los nombres y espacios de nombres de los tipos de .NET en la definición de contratos y operaciones son significativos cuando los contratos se convierten en WSDL y cuando los mensajes de contrato se crean y envían. Por lo tanto, es muy recomendable que los nombres y espacios de nombres de los contratos de servicio se establezcan explícitamente mediante las propiedades `Name` y `Namespace` de todos los atributos de contrato auxiliares, como <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute>, <xref:System.Runtime.Serialization.DataContractAttribute>, <xref:System.Runtime.Serialization.DataMemberAttribute> y otros atributos de contrato.  
  
 Una de las consecuencias es que, si no se establecen explícitamente los nombres y espacios de nombres, el uso de la ofuscación de IL en el ensamblado modifica los nombres y espacios de nombres del tipo de contrato y, por lo tanto, los intercambios de conexión y WSDL modificados generan errores. Si no establece los nombres y espacios de nombres de contrato explícitamente pero tiene pensado utilizar la ofuscación, use los atributos <xref:System.Reflection.ObfuscationAttribute> y <xref:System.Reflection.ObfuscateAssemblyAttribute> para evitar la modificación de los nombres y espacios de nombres del tipo de contrato.  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para crear un contrato de solicitud-respuesta](./feature-details/how-to-create-a-request-reply-contract.md)
- [Procedimiento para crear un contrato unidireccional](./feature-details/how-to-create-a-one-way-contract.md)
- [Procedimiento para crear un contrato dúplex](./feature-details/how-to-create-a-duplex-contract.md)
- [Especificación de transferencia de datos en contratos de servicio](./feature-details/specifying-data-transfer-in-service-contracts.md)
- [Especificación y administración de errores en contratos y servicios](specifying-and-handling-faults-in-contracts-and-services.md)
- [Uso de sesiones](using-sessions.md)
- [Operaciones sincrónicas y asincrónicas](synchronous-and-asynchronous-operations.md)
- [Reliable Services](reliable-services.md)
- [Servicios y transacciones](services-and-transactions.md)
