---
title: Usar contratos de mensaje
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message contracts [WCF]
ms.assetid: 1e19c64a-ae84-4c2f-9155-91c54a77c249
ms.openlocfilehash: 1b102b97c62df0bb8b031ded0f9165a11f8a8911
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600275"
---
# <a name="using-message-contracts"></a>Usar contratos de mensaje
Normalmente, al compilar aplicaciones de Windows Communication Foundation (WCF), los desarrolladores prestan mucha atención a las estructuras de datos y a los problemas de serialización y no tienen que preocuparse de la estructura de los mensajes en los que se transportan los datos. Para estas aplicaciones, la creación de contratos de datos para los parámetros o valores devueltos es fácil. (Para obtener más información, consulte [especificar transferencia de datos en contratos de servicio](specifying-data-transfer-in-service-contracts.md)).  
  
 Sin embargo, a veces el control completo sobre la estructura de un mensaje SOAP es tan importante como el control sobre su contenido. Esto es especialmente cierto cuando la interoperabilidad es importante o para controlar específicamente problemas de seguridad del mensaje o parte del mensaje. En estos casos, puede crear un *contrato de mensaje* que le permita especificar la estructura del mensaje SOAP preciso.  
  
 En este tema, se analiza la forma de usar los diversos atributos de contrato de mensaje para crear un contrato de mensaje específico para su operación.  
  
## <a name="using-message-contracts-in-operations"></a>Uso de contratos de mensaje en operaciones  
 WCF admite operaciones modeladas en el *estilo de llamada a procedimiento remoto (RPC)* o en el *estilo de mensajería*. En una operación de estilo de RPC, puede usar cualquier tipo serializable y tiene acceso a las características que están disponibles para las llamadas locales, como múltiples parámetros y `ref` y parámetros `out`. En este estilo, la forma de serialización elegida controla la estructura de los datos en los mensajes subyacentes y el tiempo de ejecución de WCF crea los mensajes para admitir la operación. Esto habilita a los desarrolladores que no están familiarizados con SOAP y los mensajes SOAP a crear y utilizar aplicaciones de servicio de manera rápida y sencilla.  
  
 El siguiente código de ejemplo muestra una operación de servicio modelada en el estilo RPC.  
  
```csharp  
[OperationContract]  
public BankingTransactionResponse PostBankingTransaction(BankingTransaction bt);  
```  
  
 Normalmente, un contrato de datos es suficiente para definir el esquema de los mensajes. Por ejemplo, en el ejemplo anterior, es suficiente para la mayoría de las aplicaciones si `BankingTransaction` y `BankingTransactionResponse` tienen contratos de datos para definir el contenido de los mensajes SOAP subyacentes. Para obtener más información sobre los contratos de datos, consulte [uso de contratos de datos](using-data-contracts.md).  
  
 Sin embargo, de vez en cuando es necesario controlar de manera precisa cómo la estructura del mensaje SOAP se transmite a través de la conexión. El escenario más común para esto es insertar encabezados SOAP personalizados. Otro escenario común es definir propiedades de seguridad para los encabezados y cuerpo del mensaje, es decir, decidir si estos elementos están firmados y cifrados digitalmente. Finalmente, algunas pilas de terceros de SOAP necesitan que los mensajes estén en un formato concreto. Las operaciones del estilo de mensajería proporcionan este control.  
  
 Una operación de estilo de mensajería tiene a lo sumo un parámetro y un valor devuelto donde ambos tipos son tipos de mensaje; es decir, serializan directamente en una estructura de mensaje SOAP especificada. Éste puede ser cualquier tipo marcado con <xref:System.ServiceModel.MessageContractAttribute> o el tipo <xref:System.ServiceModel.Channels.Message>. El siguiente ejemplo de código muestra una operación similar al estilo RCP anterior, pero que utiliza el estilo de mensajería.  
  
 Por ejemplo, si `BankingTransaction` y `BankingTransactionResponse` son ambos tipos que son contratos de mensaje, entonces, el código de las siguientes operaciones es válido.  
  
```csharp  
[OperationContract]  
BankingTransactionResponse Process(BankingTransaction bt);  
[OperationContract]  
void Store(BankingTransaction bt);  
[OperationContract]  
BankingTransactionResponse GetResponse();  
```  
  
 Sin embargo, el siguiente código no es válido:  
  
```csharp  
[OperationContract]  
bool Validate(BankingTransaction bt);  
// Invalid, the return type is not a message contract.  
[OperationContract]  
void Reconcile(BankingTransaction bt1, BankingTransaction bt2);  
// Invalid, there is more than one parameter.  
```  
  
 Una excepción se produce para cualquier operación que implique un tipo de contrato de mensaje y que no siga uno de los patrones válidos. Por supuesto, las operaciones que no implican tipos de contrato de mensaje no están sujetas a estas restricciones.  
  
 Si un tipo tiene un contrato de mensaje y un contrato de datos, solo su contrato de mensaje se tiene en cuenta cuando se utiliza el tipo en una operación.  
  
## <a name="defining-message-contracts"></a>Definición de contratos de mensaje  
 Para definir un contrato de mensaje para un tipo (es decir, definir la asignación entre el tipo y una envoltura SOAP), aplique <xref:System.ServiceModel.MessageContractAttribute> al tipo. A continuación, aplique <xref:System.ServiceModel.MessageHeaderAttribute> a esos miembros del tipo que desea convertir en encabezados SOAP y aplique <xref:System.ServiceModel.MessageBodyMemberAttribute> a esos miembros que desea convertir en partes del cuerpo de SOAP del mensaje.  
  
 El siguiente código proporcionan un ejemplo de uso de un contrato de mensaje.  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader] public DateTime transactionDate;  
  [MessageBodyMember] private Account sourceAccount;  
  [MessageBodyMember] private Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 Cuando se usa este tipo como parámetro de operación, se genera el siguiente sobre SOAP:  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
    <h:transactionDate xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">2012-02-16T16:10:00</h:transactionDate>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <BankingTransaction xmlns="http://tempuri.org/">  
      <amount>0</amount>  
      <sourceAccount xsi:nil="true"/>  
      <targetAccount xsi:nil="true"/>  
    </BankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
 Observe que `operation` y `transactionDate` aparecen como encabezados de SOAP y el cuerpo de SOAP está compuesto por un elemento contenedor `BankingTransaction` que contiene `sourceAccount`,`targetAccount` y `amount`.  
  
 Puede aplicar <xref:System.ServiceModel.MessageHeaderAttribute> y <xref:System.ServiceModel.MessageBodyMemberAttribute> a todos los campos, propiedades y eventos, sin tener en cuenta si son públicos, privados, protegidos o internos.  
  
 <xref:System.ServiceModel.MessageContractAttribute> permite especificar los atributos WrapperName y WrapperNamespace que controlan el nombre del elemento contenedor en el cuerpo del mensaje SOAP. De forma predeterminada el nombre del tipo de contrato de mensaje se usa para el contenedor y el espacio de nombres en el que se define el contrato de mensaje; `http://tempuri.org/` se usa como espacio de nombres predeterminado.  
  
> [!NOTE]
> Los atributos <xref:System.Runtime.Serialization.KnownTypeAttribute> se omiten en los contratos de mensaje. Si se requiere un <xref:System.Runtime.Serialization.KnownTypeAttribute>, colóquelo en la operación que esté utilizando el contrato de mensaje en cuestión.  
  
## <a name="controlling-header-and-body-part-names-and-namespaces"></a>Controlar los nombres y espacios de nombres del encabezado y parte del cuerpo  
 En la representación de SOAP de un contrato de mensaje, cada encabezado y la parte del cuerpo se asigna a un elemento XML que tiene un nombre y un espacio de nombres.  
  
 De forma predeterminada, el espacio de nombres es igual que el espacio de nombres del contrato de servicio en el que el participa el mensaje y el nombre está determinado por el nombre de miembro al que se aplican los atributos <xref:System.ServiceModel.MessageHeaderAttribute> o <xref:System.ServiceModel.MessageBodyMemberAttribute>.  
  
 Puede cambiar estos valores predeterminados manipulando las propiedades <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> y <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> (en la clase primaria de los atributos de las clases <xref:System.ServiceModel.MessageHeaderAttribute> y <xref:System.ServiceModel.MessageBodyMemberAttribute>).  
  
 Considere la clase del siguiente ejemplo de código:  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader(Namespace="http://schemas.contoso.com/auditing/2005")] public bool IsAudited;  
  [MessageBodyMember(Name="transactionData")] public BankingTransactionData theData;  
}  
```  
  
 En este ejemplo, el encabezado `IsAudited` está en el espacio de nombres especificado en el código y un elemento XML representa la parte del cuerpo que representa el miembro `theData` con el nombre `transactionData`. A continuación se muestra el XML generado para este contrato de mensaje.  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:IsAudited xmlns:h="http://schemas.contoso.com/auditing/2005" xmlns="http://schemas.contoso.com/auditing/2005">false</h:IsAudited>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <AuditedBankingTransaction xmlns="http://tempuri.org/">  
      <transactionData/>  
    </AuditedBankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
## <a name="controlling-whether-the-soap-body-parts-are-wrapped"></a>Controlar si las partes de cuerpo de SOAP están ajustadas  
 De forma predeterminada, las partes de cuerpo de SOAP se serializan dentro de un elemento ajustado. Por ejemplo, el siguiente código muestra el elemento contenedor `HelloGreetingMessage` generado a partir del nombre del tipo <xref:System.ServiceModel.MessageContractAttribute> en el contrato del mensaje para el mensaje `HelloGreetingMessage`.  
  
[!code-csharp[MessageHeaderAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/messageheaderattribute/cs/services.cs#3)]
[!code-vb[MessageHeaderAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/messageheaderattribute/vb/services.vb#3)]  
  
 Para suprimir el elemento contenedor, establezca la propiedad <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> en `false`. Para controlar el nombre y el espacio de nombres del elemento contenedor, use las propiedades <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> y <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A>.  
  
> [!NOTE]
> Tener más de una parte de cuerpo de mensaje en mensajes que no se ajustan no es conforme a WS-I Basic Profile 1.1 y no se recomienda al diseñar nuevos contratos de mensaje. Sin embargo, puede ser necesario para tener más de una parte del cuerpo de mensaje sin ajustar en ciertos escenarios de interoperabilidad concretos. Si va a transmitir más de una parte de datos en un cuerpo del mensaje, se recomienda que use el modo predeterminado (ajustado). Tener más de un encabezado de mensaje en mensajes sin ajustar es completamente aceptable.  
  
## <a name="using-custom-types-inside-message-contracts"></a>Uso de tipos personalizados dentro de contratos de mensaje  
 Cada encabezado de mensaje individual y parte del cuerpo del mensaje se serializa (se convierte en XML) utilizando el motor de serialización elegido para el contrato de servicio donde se use el mensaje. El motor de serialización predeterminado, `XmlFormatter`, puede manejar cualquier tipo que tenga un contrato de datos, explícitamente (teniendo <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>) o implícitamente (siendo un tipo primitivo, teniendo <xref:System.SerializableAttribute?displayProperty=nameWithType>, etc.). Para obtener más información, consulte [uso de contratos de datos](using-data-contracts.md).  
  
 En el ejemplo anterior, `Operation` y los tipos `BankingTransactionData` deben tener un contrato de datos y `transactionDate` es serializable porque <xref:System.DateTime> es un primitivo (y, por ende, tiene un contrato de datos implícito).  
  
 Sin embargo, es posible cambiar a un motor de serialización diferente, `XmlSerializer`. Si realiza este cambio, debería asegurarse de que todos los tipos utilizados para los encabezados del mensaje y partes del cuerpo son serializables utilizando `XmlSerializer`.  
  
## <a name="using-arrays-inside-message-contracts"></a>Uso de matrices dentro de los contratos de mensaje  
 Puede utilizar matrices de elementos repetitivos en contratos de mensaje de dos maneras.  
  
 La primera consiste en utilizar <xref:System.ServiceModel.MessageHeaderAttribute> o <xref:System.ServiceModel.MessageBodyMemberAttribute> directamente en la matriz. En este caso, toda la matriz se serializa como un elemento (es decir, un encabezado o una parte del cuerpo) con múltiples elementos secundarios. Considere la clase del siguiente ejemplo:  
  
```csharp  
[MessageContract]  
public class BankingDepositLog  
{  
  [MessageHeader] public int numRecords;  
  [MessageHeader] public DepositRecord[] records;  
  [MessageHeader] public int branchID;  
}  
```  
  
 Esto resulta en encabezados SOAP similares a los siguientes.  
  
```xml  
<BankingDepositLog>  
<numRecords>3</numRecords>  
<records>  
  <DepositRecord>Record1</DepositRecord>  
  <DepositRecord>Record2</DepositRecord>  
  <DepositRecord>Record3</DepositRecord>  
</records>  
<branchID>20643</branchID>  
</BankingDepositLog>  
```  
  
 Como alternativa se puede utilizar <xref:System.ServiceModel.MessageHeaderArrayAttribute>. En este caso, cada elemento de matriz se serializa independientemente y, por tanto, cada elemento de matriz tiene un encabezado, similar a lo siguiente.  
  
```xml  
<numRecords>3</numRecords>  
<records>Record1</records>  
<records>Record2</records>  
<records>Record3</records>  
<branchID>20643</branchID>  
```  
  
 El nombre predeterminado para las entradas de la matriz es el nombre del miembro al que se aplican los atributos <xref:System.ServiceModel.MessageHeaderArrayAttribute>.  
  
 El atributo <xref:System.ServiceModel.MessageHeaderArrayAttribute> hereda de <xref:System.ServiceModel.MessageHeaderAttribute>. Tiene el mismo conjunto de características como los atributos que no son de matriz, por ejemplo, es posible establecer el orden, nombre y espacio de nombres de una matriz de encabezados de la misma manera que se establece para un encabezado único. Al utilizar la propiedad `Order` en una matriz, se aplica a toda la matriz.  
  
 Solo puede aplicar <xref:System.ServiceModel.MessageHeaderArrayAttribute> a las matrices, no a las colecciones.  
  
## <a name="using-byte-arrays-in-message-contracts"></a>Uso de las matrices de bytes en contratos de mensaje  
 Las matrices de bytes, cuando se usan con los atributos que no son de matriz (<xref:System.ServiceModel.MessageBodyMemberAttribute> y <xref:System.ServiceModel.MessageHeaderAttribute>), no se tratan como matrices, sino como un tipo primitivo especial representado como datos con codificación Base64 en el XML resultante.  
  
 Al utilizar las matrices de bytes con el atributo de matriz <xref:System.ServiceModel.MessageHeaderArrayAttribute>, los resultados dependen del serializador que se utilice. Con el serializador predeterminado, la matriz se representa como una entrada individual para cada byte. Sin embargo, cuando se selecciona`XmlSerializer`, (usando <xref:System.ServiceModel.XmlSerializerFormatAttribute> en el contrato de servicio) las matrices de bytes se tratan como datos Base64 independientemente de si se utilizan los atributos que son de matriz o los que no son de matriz.  
  
## <a name="signing-and-encrypting-parts-of-the-message"></a>Firmado y cifrado de partes del mensaje  
 Un contrato de mensaje puede indicar si los encabezados y/o cuerpo del mensaje deberían estar firmados y cifrados digitalmente.  
  
 Esto se hace estableciendo la propiedad <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType> en los atributos de las clases <xref:System.ServiceModel.MessageHeaderAttribute> y <xref:System.ServiceModel.MessageBodyMemberAttribute>. La propiedad es una enumeración del tipo <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType> y se puede establecer como <xref:System.Net.Security.ProtectionLevel.None> (sin cifrado ni firma), <xref:System.Net.Security.ProtectionLevel.Sign> (solo firma digital) o <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (cifrado y firma digital). De manera predeterminada, es <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.  
  
 Para que estas características de seguridad funcionen, debe configurar correctamente el enlace y los comportamientos. Si utiliza estas características de seguridad sin la configuración apropiada (por ejemplo, intentando firmar un mensaje sin proporcionar sus credenciales), una excepción se producirá en el momento de la validación.  
  
 Para los encabezados de mensajes, el nivel de protección se determina individualmente para cada encabezado.  
  
 Para las partes del cuerpo del mensaje, el nivel de protección puede verse como el "nivel de protección mínimo". El cuerpo tiene solo un nivel de protección, independientemente del número de partes del cuerpo. El nivel de protección del cuerpo lo determina el valor de propiedad <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A> más alto de todas las partes del cuerpo. Sin embargo, debería establecer el nivel de protección de cada parte del cuerpo en el nivel de protección mínimo real necesario.  
  
 Considere la clase del siguiente ejemplo de código:  
  
```csharp  
[MessageContract]  
public class PatientRecord  
{  
   [MessageHeader(ProtectionLevel=None)] public int recordID;  
   [MessageHeader(ProtectionLevel=Sign)] public string patientName;  
   [MessageHeader(ProtectionLevel=EncryptAndSign)] public string SSN;  
   [MessageBodyMember(ProtectionLevel=None)] public string comments;  
   [MessageBodyMember(ProtectionLevel=Sign)] public string diagnosis;  
   [MessageBodyMember(ProtectionLevel=EncryptAndSign)] public string medicalHistory;  
}  
```  
  
 En este ejemplo, el encabezado `recordID` no está protegido, `patientName` está `signed`, y `SSN` está cifrado y firmado. Al menos una parte del cuerpo, `medicalHistory`, tiene <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> aplicado y, de este modo, el cuerpo del mensaje completo se cifra y firma, aun cuando las partes del cuerpo de comentarios y diagnóstico especifican niveles de protección inferiores.  
  
## <a name="soap-action"></a>Acción de SOAP  
 SOAP y los estándares de los servicios Web relacionados definen una propiedad llamada `Action` que puede estar presente en cada mensaje SOAP enviado. Las propiedades <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> y <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> de la operación controlan el valor de esta propiedad.  
  
## <a name="soap-header-attributes"></a>Atributos de encabezado SOAP  
 El estándar de SOAP define los siguientes atributos que pueden existir en un encabezado:  
  
- `Actor/Role` (`Actor` en SOAP 1.1, `Role` en SOAP 1.2)  
  
- `MustUnderstand`  
  
- `Relay`  
  
 El atributo `Actor` o `Role` especifica el Identificador uniforme de recursos (URI) del nodo para el que está dirigido un encabezado determinado. El atributo `MustUnderstand` especifica si el nodo que procesa el encabezado debe entenderlo. El atributo `Relay` especifica si el encabezado se va a retransmitir a los nodos descendentes. WCF no realiza ningún procesamiento de estos atributos en los mensajes entrantes, salvo el `MustUnderstand` atributo, como se especifica en la sección "versiones de contrato de mensaje" más adelante en este tema. Sin embargo, le permite leer y escribir estos atributos según sea necesario, como en la siguiente descripción.  
  
 Al enviar un mensaje, no se emiten estos atributos de forma predeterminada. Esto se puede cambiar de dos formas: Primero, puede establecer de manera estática los atributos en cualquier valor que desee cambiando las propiedades <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType> y <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType>, tal y como se muestra en el siguiente ejemplo de código. (Observe que no hay propiedad `Role`; establecer la propiedad <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A> emite el atributo `Role` si usa SOAP 1.2).  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader(Actor="http://auditingservice.contoso.com", MustUnderstand=true)] public bool IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
```  
  
 La segunda manera de controlar estos atributos es de manera dinámica, mediante código. Puede lograr esto ajustando el tipo de encabezado deseado en el tipo <xref:System.ServiceModel.MessageHeader%601> (asegúrese de no confundir este tipo con la versión no genérica) y usando el tipo junto con la clase <xref:System.ServiceModel.MessageHeaderAttribute>. A continuación, puede usar las propiedades de la clase <xref:System.ServiceModel.MessageHeader%601> para establecer los atributos SOAP, tal y como se muestra en el siguiente ejemplo de código.  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public MessageHeader<bool> IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
// application code:  
BankingTransaction bt = new BankingTransaction();  
bt.IsAudited = new MessageHeader<bool>();  
bt.IsAudited.Content = false; // Set IsAudited header value to "false"  
bt.IsAudited.Actor="http://auditingservice.contoso.com";  
bt.IsAudited.MustUnderstand=true;  
```  
  
 Si utiliza los mecanismos de control dinámico y estático, los ajustes estáticos se utilizan como valores predeterminados, pero pueden invalidarse después mediante el uso del mecanismo dinámico, tal y como se muestra en el código siguiente.  
  
```csharp  
[MessageHeader(MustUnderstand=true)] public MessageHeader<Person> documentApprover;  
// later on in the code:  
BankingTransaction bt = new BankingTransaction();  
bt.documentApprover = new MessageHeader<Person>();  
bt.documentApprover.MustUnderstand = false; // override the static default of 'true'  
```  
  
 Se permite la creación de encabezados repetidos con control de atributo dinámico, tal y como se muestra en el código siguiente.  
  
```csharp  
[MessageHeaderArray] public MessageHeader<Person> documentApprovers[];  
```  
  
 En el lado receptor, solo se pueden leer estos atributos de SOAP si se utiliza la clase <xref:System.ServiceModel.MessageHeader%601> para el encabezado en el tipo. Examine las propiedades `Actor`, `Relay` o `MustUnderstand` de un encabezado del tipo <xref:System.ServiceModel.MessageHeader%601> para detectar los valores de atributos en el mensaje recibido.  
  
 Cuando se recibe un mensaje y después se devuelve, los valores de atributo de SOAP solo son de ida y vuelta para encabezados de tipo <xref:System.ServiceModel.MessageHeader%601>.  
  
## <a name="order-of-soap-body-parts"></a>Orden de partes de cuerpo de SOAP  
 En algunas circunstancias, puede que tenga que controlar el orden de partes del cuerpo. De forma predeterminada, el orden de los elementos del cuerpo es alfabético, pero puede controlarse mediante la propiedad <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>. Esta propiedad tiene la misma semántica que la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType>, salvo el comportamiento en escenarios de herencia (en contratos de mensaje, los miembros de cuerpo de tipo base no están ordenados antes de los miembros de cuerpo de tipo derivado). Para obtener más información, vea orden de los [miembros de datos](data-member-order.md).  
  
 En el siguiente ejemplo, `amount` vendría normalmente primero porque es primero alfabéticamente. Sin embargo, la propiedad <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A> lo coloca en la tercera posición.  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember(Order=1)] public Account sourceAccount;  
  [MessageBodyMember(Order=2)] public Account targetAccount;  
  [MessageBodyMember(Order=3)] public int amount;  
}  
```  
  
## <a name="message-contract-versioning"></a>Versiones de contratos de mensaje  
 De vez en cuando, puede necesitar cambiar los contratos de mensaje. Por ejemplo, una nueva versión de su aplicación puede agregar un encabezado adicional a un mensaje. A continuación, al enviar de la nueva versión a la anterior, el sistema debe tratar con un encabezado adicional, así como un encabezado de menos al ir en la otra dirección.  
  
 Las siguientes reglas se aplican a los encabezados de versiones:  
  
- WCF no objeto a los encabezados que faltan; los miembros correspondientes se dejan con sus valores predeterminados.  
  
- WCF también omite encabezados adicionales inesperados. La única excepción a esta regla es si el encabezado adicional tiene un atributo `MustUnderstand` establecido en `true` en el mensaje SOAP entrante. En este caso, se produce una excepción porque no se puede procesar ningún encabezado que deba entenderse.  
  
 Los cuerpos de mensajes tienen reglas de versión similares; se omiten las partes de cuerpo de mensaje adicionales y que faltan.  
  
## <a name="inheritance-considerations"></a>Consideraciones sobre la herencia  
 Un tipo de contrato de mensaje puede heredar de otro tipo, con tal de que el tipo base también tenga un contrato de mensaje.  
  
 Al crear u obtener acceso a un mensaje utilizando un tipo de contrato de mensaje que hereda de otros tipos de contrato de mensaje, se aplican las reglas siguientes:  
  
- Todos los encabezados del mensaje en la jerarquía de la herencia se unen para formar el conjunto completo de encabezados del mensaje.  
  
- Todas las partes del cuerpo del mensaje en la jerarquía de la herencia se unen para formar el cuerpo del mensaje completo. Las partes del cuerpo se ordenan de acuerdo con las reglas de clasificación normales (mediante la propiedad <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> y, a continuación, alfabéticamente), sin importar su lugar en la jerarquía de herencia. Se desaconseja en gran medida usar la herencia de contrato de mensaje donde las partes del cuerpo del mensaje tienen lugar en varios niveles del árbol de herencia. Si una clase base y una clase derivada definen un encabezado o una parte del cuerpo con el mismo nombre, el miembro de la clase más base se utiliza para almacenar el valor de ese encabezado o parte del cuerpo.  
  
 Considere las clases del siguiente ejemplo de código:  
  
```csharp  
[MessageContract]  
public class PersonRecord  
{  
  [MessageHeader(Name="ID")] public int personID;  
  [MessageBodyMember] public string patientName;  
}  
  
[MessageContract]  
public class PatientRecord : PersonRecord  
{  
  [MessageHeader(Name="ID")] public int patientID;  
  [MessageBodyMember] public string diagnosis;  
}  
```  
  
 La clase `PatientRecord` describe un mensaje con un encabezado denominado `ID`. El encabezado corresponde a `personID` y no al miembro `patientID`, porque se elige el miembro más base. Por lo tanto, el campo `patientID` es inútil en este caso. El cuerpo del mensaje contiene el elemento `diagnosis` seguido del elemento `patientName`, porque ése es el orden alfabético. Observe que el ejemplo muestra un patrón que se desaconseja fuertemente: la base y los contratos de mensaje derivados tienen partes del cuerpo del mensaje.  
  
## <a name="wsdl-considerations"></a>Consideraciones sobre WSDL  
 Al generar un lenguaje de descripción de servicios Web (WSDL) a partir de un servicio que usa contratos de mensaje, es importante recordar que no todas las características de contratos de mensaje se reflejan en el WSDL resultante. Considere los siguientes puntos:  
  
- WSDL no puede expresar el concepto de una matriz de encabezados. Al crear los mensajes con una matriz de encabezados utilizando <xref:System.ServiceModel.MessageHeaderArrayAttribute>, el WSDL resultante refleja solo un encabezado en lugar de la matriz.  
  
- El documento WSDL resultante puede que no refleje alguna información de protección.  
  
- El tipo de mensaje generado en el WSDL tiene el mismo nombre que el nombre de clase del tipo de contrato de mensaje.  
  
- Al utilizar el mismo contrato del mensaje en varias operaciones, se generan varios tipos de mensaje en el documento WSDL. Los nombres se hacen únicos sumando los números "2", "3", etc., para los usos subsiguientes. Al importar el WSDL, varios tipos de contrato de mensaje se crean y son idénticos salvo por sus nombres.  
  
## <a name="soap-encoding-considerations"></a>Consideraciones sobre la codificación SOAP  
 WCF permite usar el estilo de codificación SOAP heredado de XML; sin embargo, no se recomienda su uso. Al utilizar este estilo (estableciendo la propiedad `Use` como `Encoded` en el <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType> aplicado al contrato de servicio), las siguientes consideraciones adicionales se aplican:  
  
- No se admiten los encabezados del mensaje; esto significa que el atributo <xref:System.ServiceModel.MessageHeaderAttribute> y el atributo de matriz <xref:System.ServiceModel.MessageHeaderArrayAttribute> son incompatibles con la codificación SOAP.  
  
- Si no se ajusta el contrato del mensaje, esto es, si la propiedad <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> está establecida como `false`, el contrato de mensaje solo puede tener una parte del cuerpo.  
  
- El nombre del elemento contenedor para el contrato del mensaje de solicitud debe coincidir con el nombre de la operación. Utilice la propiedad `WrapperName` del contrato del mensaje para ello.  
  
- El nombre del elemento contenedor del contrato del mensaje de respuesta debe ser igual que el nombre de la operación con el sufijo “Respuesta” agregado. Utilice la propiedad <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> del contrato del mensaje para ello.  
  
- La codificación SOAP conserva las referencias a objetos. Por ejemplo, considere el fragmento de código siguiente:  
  
    ```csharp  
    [MessageContract(WrapperName="updateChangeRecord")]  
    public class ChangeRecordRequest  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    [MessageContract(WrapperName="updateChangeRecordResponse")]  
    public class ChangeRecordResponse  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    // application code:  
    ChangeRecordRequest cr = new ChangeRecordRequest();  
    Person p = new Person("John Doe");  
    cr.changedBy=p;  
    cr.changedFrom=p;  
    cr.changedTo=p;  
    ```  
  
 Después de serializar el mensaje mediante codificación SOAP, `changedFrom` y `changedTo` no contienen sus propias copias de `p`; en su lugar, señalan la copia que está dentro del elemento `changedBy`.  
  
## <a name="performance-considerations"></a>Consideraciones de rendimiento  
 Cada encabezado del mensaje y la parte del cuerpo del mensaje se serializa independientemente de las otras. Por tanto, los mismos espacios de nombres se pueden declarar de nuevo para cada encabezado y parte del cuerpo. Para mejorar el rendimiento, sobre todo en lo que se refiere al tamaño del mensaje en la conexión, consolide varios encabezados y partes de cuerpo en un único encabezado o parte del cuerpo. Por ejemplo, en lugar del siguiente código:  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public Account sourceAccount;  
  [MessageBodyMember] public Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 Utilice este código:  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public OperationDetails details;  
}  
  
[DataContract]  
public class OperationDetails  
{  
  [DataMember] public Account sourceAccount;  
  [DataMember] public Account targetAccount;  
  [DataMember] public int amount;  
}  
```  
  
### <a name="event-based-asynchronous-and-message-contracts"></a>Contratos de mensaje y asincrónicos basados en eventos  
 Las directrices de diseño del modelo asincrónico basado en eventos afirman que si se devuelve más de un valor, uno de los valores se devuelve como propiedad `Result` y los demás se devuelven como propiedades del objeto <xref:System.EventArgs>. De esto resulta que si un cliente importa metadatos mediante opciones de comando asincrónicas basadas en eventos y la operación devuelve más de un valor, el objeto <xref:System.EventArgs> predeterminado devuelve un valor como propiedad `Result` y el resto son propiedades del objeto <xref:System.EventArgs>.  
  
 Si desea recibir el objeto del mensaje como propiedad `Result` y que los valores devueltos sean propiedades de ese objeto, utilice la opción de comando `/messageContract`. Esto genera una firma que devuelve el mensaje de respuesta como la propiedad `Result` del objeto <xref:System.EventArgs>. Todos los valores de devolución internos se convierten, pues, en propiedades del objeto de mensaje de respuesta.  
  
## <a name="see-also"></a>Vea también

- [Utilización de contratos de datos](using-data-contracts.md)
- [Diseño e implementación de servicios](../designing-and-implementing-services.md)
