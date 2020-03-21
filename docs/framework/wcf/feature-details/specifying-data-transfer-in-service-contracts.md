---
title: Especificación de transferencia de datos en contratos de servicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], data transfer
ms.assetid: 7c5a26c8-89c9-4bcb-a4bc-7131e6d01f0c
ms.openlocfilehash: e68ca46f9d2c562491063ae66754c469dbe0898e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184424"
---
# <a name="specifying-data-transfer-in-service-contracts"></a>Especificación de transferencia de datos en contratos de servicio
Windows Communication Foundation (WCF) se puede considerar como una infraestructura de mensajería. Las operaciones de servicio pueden recibir mensajes, procesarlos y enviarles mensajes. Los mensajes se describen mediante contratos de operaciones. Por ejemplo, considere el siguiente contrato:  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(string fromCity, string toCity);  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
  
    <OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
End Interface  
```  
  
 Aquí, la operación `GetAirfare` acepta un mensaje con información sobre `fromCity` y `toCity`y, a continuación, devuelve un mensaje que contiene un número.  
  
 En este tema se explican las varias maneras en las que un contrato de operación puede describir los mensajes.  
  
## <a name="describing-messages-by-using-parameters"></a>Descripción de mensajes mediante parámetros  
 La manera más simple de describir un mensaje consiste en utilizar una lista de parámetros y el valor devuelto. En el ejemplo anterior, los parámetros de cadena `fromCity` y `toCity` se utilizaron para describir el mensaje de solicitud y el valor devuelto flotante se utilizó para describir el mensaje de respuesta. Si el valor devuelto por sí solo no es suficiente para describir un mensaje de respuesta, se pueden utilizar parámetros out. Por ejemplo, la siguiente operación tiene `fromCity` y `toCity` en su mensaje de solicitud y un número junto con una divisa en su mensaje de respuesta:  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, out string currency);  
```  
  
```vb  
<OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
```  
  
 Además, puede utilizar parámetros de referencia para hacer que un parámetro forme parte tanto del mensaje de solicitud como del de respuesta. Los parámetros deben ser de tipos que se pueden serializar (convertidos a XML). De forma predeterminada, WCF <xref:System.Runtime.Serialization.DataContractSerializer> usa un componente denominado la clase para realizar esta conversión. Se admite la mayoría de datos primitivos (como `int`, `string`, `float`, y `DateTime`). Los tipos definidos por el usuario deben tener normalmente un contrato de datos. Para obtener más información, consulte Uso de [contratos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)de datos .  
  
```csharp
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
  
    [DataContract]  
    public class Itinerary  
    {  
        [DataMember]  
        public string fromCity;  
        [DataMember]  
        public string toCity;  
   }  
}  
```  
  
```vb  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
    <DataContract()>  
    Class Itinerary  
  
        <DataMember()>  
        Public fromCity As String  
        <DataMember()>  
        Public toCity As String  
    End Class  
End Interface  
```  
  
 En ocasiones, `DataContractSerializer` no es adecuado para serializar sus tipos. WCF admite un motor <xref:System.Xml.Serialization.XmlSerializer>de serialización alternativo, el , que también puede usar para serializar parámetros. <xref:System.Xml.Serialization.XmlSerializer> le permite utilizar más control sobre el XML resultante mediante atributos como el `XmlAttributeAttribute`. Para pasar a utilizar <xref:System.Xml.Serialization.XmlSerializer> para una operación determinada o para el servicio completo, aplique el atributo <xref:System.ServiceModel.XmlSerializerFormatAttribute> a una operación o un servicio. Por ejemplo:  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    [XmlSerializerFormat]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
}  
public class Itinerary  
{  
    public string fromCity;  
    public string toCity;  
    [XmlAttribute]  
    public bool isFirstClass;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    <XmlSerializerFormat>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
End Interface  
  
Class Itinerary  
  
    Public fromCity As String  
    Public toCity As String  
    <XmlSerializerFormat()>  
    Public isFirstClass As Boolean  
End Class  
```  
  
 Para obtener más información, consulte [Uso de la clase XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md). Recuerde que intercambiar manualmente a <xref:System.Xml.Serialization.XmlSerializer>, tal y como se muestra aquí, no se recomienda a menos que tenga razones concretas para hacerlo tal y como se detalla en ese tema.  
  
 Para aislar los nombres de parámetro .NET de los nombres de contrato, puede utilizar el atributo <xref:System.ServiceModel.MessageParameterAttribute> y utilizar la propiedad `Name` para establecer el nombre de contrato. Por ejemplo, el contrato de operación siguiente es equivalente al primer ejemplo de este tema.  
  
```csharp  
[OperationContract]  
public float GetAirfare(  
    [MessageParameter(Name="fromCity")] string originCity,  
    [MessageParameter(Name="toCity")] string destinationCity);  
```  
  
```vb  
<OperationContract()>  
  Function GetAirfare(<MessageParameter(Name := "fromCity")> fromCity As String, <MessageParameter(Name := "toCity")> toCity As String) As Double  
```  
  
## <a name="describing-empty-messages"></a>Descripción de mensajes vacíos  
 Un mensaje de solicitud vacío se puede describir no teniendo ninguna entrada ni parámetro de referencia. Por ejemplo, en C-:  
  
 `[OperationContract]`  
  
 `public int GetCurrentTemperature();`  
  
 Por ejemplo, en Visual Basic:  
  
 `<OperationContract()>`  
  
 `Function GetCurrentTemperature() as Integer`  
  
 Un mensaje de respuesta vacío se puede describir teniendo un tipo de valor devuelto `void` y ningún resultado ni parámetro de referencia. Por ejemplo en:  
  
```csharp  
[OperationContract]  
public void SetTemperature(int temperature);  
```  
  
```vb  
<OperationContract()>  
Sub SetTemperature(temperature As Integer)  
```  
  
 Esto es diferente de una operación unidireccional, como:  
  
```csharp  
[OperationContract(IsOneWay=true)]  
public void SetLightbulbStatus(bool isOn);  
```  
  
```vb  
<OperationContract(IsOneWay:=True)>  
Sub SetLightbulbStatus(isOne As Boolean)  
```  
  
 La operación `SetTemperatureStatus` devuelve un mensaje vacío. Puede devolver en su lugar un error si hay un problema al procesar un mensaje de entrada. La operación `SetLightbulbStatus` no devuelve nada. No hay ninguna manera de comunicar una condición de error de esta operación.  
  
## <a name="describing-messages-by-using-message-contracts"></a>Descripción de mensajes mediante el uso de contratos de mensaje  
 Puede desear utilizar un tipo único para representar el mensaje completo. Aunque es posible de utilizar un contrato de datos para este propósito, la manera recomendada para ello consiste en utilizar un contrato de mensaje; esto evita niveles innecesarios de ajuste en el XML resultante. Además, los contratos de mensaje le permiten ejercer más control sobre los mensajes resultantes. Por ejemplo, puede decidir qué partes de información deberían estar en el cuerpo del mensaje y cuáles deberían estar en los encabezados del mensaje. En el siguiente ejemplo se muestra el uso de contratos de mensaje.  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    GetAirfareResponse GetAirfare(GetAirfareRequest request);  
}  
  
[MessageContract]  
public class GetAirfareRequest  
{  
    [MessageHeader] public DateTime date;  
    [MessageBodyMember] public Itinerary itinerary;  
}  
  
[MessageContract]  
public class GetAirfareResponse  
{  
    [MessageBodyMember] public float airfare;  
    [MessageBodyMember] public string currency;  
}  
  
[DataContract]  
public class Itinerary  
{  
    [DataMember] public string fromCity;  
    [DataMember] public string toCity;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    Function GetAirfare(request As GetAirfareRequest) As GetAirfareResponse  
End Interface  
  
<MessageContract()>  
Public Class GetAirfareRequest  
    <MessageHeader()>
    Public Property date as DateTime  
    <MessageBodyMember()>  
    Public Property itinerary As Itinerary  
End Class  
  
<MessageContract()>  
Public Class GetAirfareResponse  
    <MessageBodyMember()>  
    Public Property airfare As Double  
    <MessageBodyMember()> Public Property currency As String  
End Class  
  
<DataContract()>  
Public Class Itinerary  
    <DataMember()> Public Property fromCity As String  
    <DataMember()> Public Property toCity As String  
End Class  
```  
  
 Para obtener más información, consulte Uso de [contratos](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)de mensajes .  
  
 En el ejemplo anterior, la clase <xref:System.Runtime.Serialization.DataContractSerializer> se sigue utilizando de forma predeterminada. La clase <xref:System.Xml.Serialization.XmlSerializer> también se puede usar con contratos de mensaje. Para ello, aplique el atributo <xref:System.ServiceModel.XmlSerializerFormatAttribute> a la operación o al contrato y utilice tipos compatibles con la clase <xref:System.Xml.Serialization.XmlSerializer> en los encabezados del mensaje y miembros del cuerpo.  
  
## <a name="describing-messages-by-using-streams"></a>Descripción de mensajes mediante el uso de secuencias  
 Otra manera de describir mensajes en operaciones consiste en usar la clase <xref:System.IO.Stream> o una de sus clases derivadas en un contrato de operación o como miembro del cuerpo del contrato de mensaje (debe ser el único miembro en este caso). Para los mensajes entrantes, el tipo debe ser `Stream`; no puede utilizar clases derivadas.  
  
 En lugar de invocar el serializador, WCF recupera datos de una secuencia y los coloca directamente en un mensaje saliente, o recupera datos de un mensaje entrante y los coloca directamente en una secuencia. En el siguiente ejemplo se muestra la forma de utilizar secuencias.  
  
```csharp  
[OperationContract]  
public Stream DownloadFile(string fileName);  
```  
  
```vb  
<OperationContract()>  
Function DownloadFile(fileName As String) As String  
```  
  
 No puede combinar datos que no sean de secuencia y datos de `Stream` en un cuerpo de mensaje único. Utilice un contrato de mensaje para colocar los datos adicionales en encabezados de mensaje. El ejemplo siguiente muestra el uso incorrecto de secuencias al definir el contrato de operación.  
  
```csharp  
//Incorrect:  
// [OperationContract]  
// public void UploadFile (string fileName, Stream fileData);  
```  
  
```vb  
'Incorrect:  
    '<OperationContract()>  
    Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
```  
  
 El ejemplo siguiente muestra el uso correcto de los flujos al definir un contrato de operación.  
  
```csharp  
[OperationContract]  
public void UploadFile (UploadFileMessage message);  
//code omitted  
[MessageContract]  
public class UploadFileMessage  
{  
    [MessageHeader] public string fileName;  
    [MessageBodyMember] public Stream fileData;  
}  
```  
  
```vb  
<OperationContract()>  
Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
'Code Omitted  
<MessageContract()>  
Public Class UploadFileMessage  
   <MessageHeader()>  
    Public Property fileName As String  
    <MessageBodyMember()>  
    Public Property fileData As Stream  
End Class  
```  
  
 Para obtener más información, consulte [Datos grandes y streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).  
  
## <a name="using-the-message-class"></a>Uso de la clase de mensajes  
 Para tener control completo de programación sobre los mensajes enviados o recibidos, puede utilizar directamente la clase <xref:System.ServiceModel.Channels.Message>, tal y como se muestra en el siguiente código de ejemplo.  
  
```csharp  
[OperationContract]  
public void LogMessage(Message m);  
```  
  
```vb  
<OperationContract()>  
Sub LogMessage(m As Message)  
```  
  
 Se trata de un escenario avanzado, que se describe en detalle en [Uso de la clase de mensaje](../../../../docs/framework/wcf/feature-details/using-the-message-class.md).  
  
## <a name="describing-fault-messages"></a>Descripción de mensajes de error  
 Además de los mensajes que son descritos por el valor devuelto y los parámetros de referencia o salida, cualquier operación que no sea unidireccional puede devolver al menos dos posibles mensajes: su mensaje de respuesta normal y un mensaje de error. Considere el contrato de operación siguiente.  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
```  
  
```vb  
<OperationContract()>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime)  
```  
  
 Esta operación puede devolver un mensaje normal que contenga un número `float` o un mensaje de error que contenga un código de error y una descripción. Puede lograr esto generando una <xref:System.ServiceModel.FaultException> en su implementación del servicio.  
  
 Puede especificar posibles mensajes de error adicionales utilizando el atributo <xref:System.ServiceModel.FaultContractAttribute>. Los errores adicionales se han de poder serializar mediante el <xref:System.Runtime.Serialization.DataContractSerializer>, tal y como se muestra en el código de ejemplo siguiente.  
  
```csharp  
[OperationContract]  
[FaultContract(typeof(ItineraryNotAvailableFault))]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
  
//code omitted  
  
[DataContract]  
public class ItineraryNotAvailableFault  
{  
    [DataMember]  
    public bool IsAlternativeDateAvailable;  
  
    [DataMember]  
    public DateTime alternativeSuggestedDate;  
}  
```  
  
```vb  
<OperationContract()>  
<FaultContract(GetType(ItineraryNotAvailableFault))>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime) As Double  
  
'Code Omitted  
<DataContract()>  
Public Class  
  <DataMember()>  
  Public Property IsAlternativeDateAvailable As Boolean  
  <DataMember()>  
  Public Property alternativeSuggestedDate As DateTime  
End Class  
```  
  
 Estos errores adicionales se pueden generar mediante la generación de una <xref:System.ServiceModel.FaultException%601> del tipo de contrato de datos adecuado. Para obtener más información, consulte [Control de excepciones y errores](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).  
  
 No puede utilizar la clase <xref:System.Xml.Serialization.XmlSerializer> para describir los errores. El <xref:System.ServiceModel.XmlSerializerFormatAttribute> no tiene efecto en contratos de error.  
  
## <a name="using-derived-types"></a>Uso de tipos derivados  
 Puede desear utilizar un tipo base en una operación o un contrato de mensaje y, a continuación, utilizar un tipo derivado al invocar verdaderamente la operación. En este caso, debe utilizar el atributo <xref:System.ServiceModel.ServiceKnownTypeAttribute> o algún mecanismo alternativo para permitir el uso de tipos derivados. Considere la siguiente operación.  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
```  
  
```vb
<OperationContract()>  
    Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
```  
  
 Suponga que dos tipos, `Book` y `Magazine`, derivan de `LibraryItem`. Para utilizar estos tipos en la operación `IsLibraryItemAvailable`, puede cambiar la operación tal y como sigue:  
  
 `[OperationContract]`  
  
 `[ServiceKnownType(typeof(Book))]`  
  
 `[ServiceKnownType(typeof(Magazine))]`  
  
 `public bool IsLibraryItemAvailable(LibraryItem item);`  
  
 Alternativamente, puede utilizar el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute> cuando el <xref:System.Runtime.Serialization.DataContractSerializer> predeterminado se esté utilizando, tal y como se muestra en el código de ejemplo siguiente.  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
  
// code omitted
  
[DataContract]  
[KnownType(typeof(Book))]  
[KnownType(typeof(Magazine))]  
public class LibraryItem  
{  
    //code omitted  
}  
```  
  
```vb  
<OperationContract()>  
Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
  
'Code Omitted  
<DataContract()>  
<KnownType(GetType(Book))>  
<KnownType(GetType(Magazine))>  
Public Class LibraryItem  
  'Code Omitted  
End Class  
```  
  
 Puede utilizar el atributo <xref:System.Xml.Serialization.XmlIncludeAttribute> al usar el <xref:System.Xml.Serialization.XmlSerializer>.  
  
 Puede aplicar el atributo <xref:System.ServiceModel.ServiceKnownTypeAttribute> a una operación o al servicio completo. Acepta un tipo o el nombre del método para llamar para obtener una lista de tipos conocidos, como el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute>. Para obtener más información, vea [Tipos conocidos](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)de contrato de datos .  
  
## <a name="specifying-the-use-and-style"></a>Especificación del uso y estilo  
 Al describir servicios mediante el lenguaje de descripción de servicios Web (WSDL), los dos estilos utilizados comúnmente son Documento y llamada a procedimiento remoto (RPC). En el estilo Documento, el cuerpo del mensaje completo se describe utilizando el esquema, y el WSDL describe las diversas partes del cuerpo del mensaje haciendo referencia a elementos dentro de ese esquema. En el estilo RPC, el WSDL hace referencia a un tipo de esquema para cada parte del mensaje en lugar de a un elemento. En algunos casos, tiene que seleccionar manualmente uno de estos estilos. Puede hacer esto aplicando el atributo <xref:System.ServiceModel.DataContractFormatAttribute> y estableciendo la propiedad `Style` (cuando se esté usando <xref:System.Runtime.Serialization.DataContractSerializer>), o estableciendo el `Style` en el atributo <xref:System.ServiceModel.XmlSerializerFormatAttribute> (al usar el <xref:System.Xml.Serialization.XmlSerializer>).  
  
 Además, <xref:System.Xml.Serialization.XmlSerializer> admite dos formas de XML serializado: `Literal` y `Encoded`. `Literal` es la forma más aceptada y es el único formato que <xref:System.Runtime.Serialization.DataContractSerializer> admite. `Encoded` es un formato heredado descrito en la sección 5 de la especificación SOAP, y no se recomienda para los nuevos servicios. Para cambiar al modo `Encoded`, establezca la propiedad `Use` en el atributo <xref:System.ServiceModel.XmlSerializerFormatAttribute> en `Encoded`.  
  
 En la mayoría de los casos, no debería cambiar la configuración predeterminada para el `Style` ni las propiedades `Use`.  
  
## <a name="controlling-the-serialization-process"></a>Control del proceso de serialización  
 Puede hacer varias cosas para personalizar la manera en la que se serializan los datos.  
  
### <a name="changing-server-serialization-settings"></a>Cambio de los ajustes de serialización del servidor  
 Cuando el <xref:System.Runtime.Serialization.DataContractSerializer> predeterminado se está utilizando, puede controlar algunos aspectos del proceso de serialización en el servicio aplicando el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> al servicio. Específicamente, puede utilizar la propiedad `MaxItemsInObjectGraph` para establecer la cuota que limita el número máximo de objetos que <xref:System.Runtime.Serialization.DataContractSerializer> deserializa. Puede usar la propiedad `IgnoreExtensionDataObject` para desactivar la característica de control de versiones de ida y vuelta. Para obtener más información sobre las cuotas, vea [Consideraciones de seguridad para datos](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md). Para obtener más información acerca de los viajes de ida y vuelta, consulte [Contratos](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)de datos compatibles con reenvío .  
  
```csharp  
[ServiceBehavior(MaxItemsInObjectGraph=100000)]  
public class MyDataService:IDataService  
{  
    public DataPoint[] GetData()  
    {  
       // Implementation omitted  
    }  
}  
```  
  
```vb  
<ServiceBehavior(MaxItemsInObjectGraph:=100000)>  
Public Class MyDataService Implements IDataService  
  
    Function GetData() As DataPoint()  
         ‘ Implementation omitted  
    End Function  
End Interface  
```  
  
### <a name="serialization-behaviors"></a>Comportamientos de serialización  
 Dos comportamientos están disponibles <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> en <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> WCF, el y el que se conectan automáticamente en función de qué serializador está en uso para una operación determinada. Dado que se aplican automáticamente estos comportamientos, normalmente no tiene que estar al tanto sobre ellos.  
  
 Sin embargo, `DataContractSerializerOperationBehavior` tiene `MaxItemsInObjectGraph`, `IgnoreExtensionDataObject`, y las propiedades `DataContractSurrogate` que puede utilizar para personalizar el proceso de serialización. Las primeras dos propiedades tienen el mismo significado que se mencionó en la sección anterior. Puede utilizar la propiedad `DataContractSurrogate` para habilitar suplentes del contrato de datos, que son un mecanismo eficaz para personalizar y extender el proceso de serialización. Para obtener más información, consulte Suplentes de [contratos](../../../../docs/framework/wcf/extending/data-contract-surrogates.md)de datos .  
  
 Puede utilizar el `DataContractSerializerOperationBehavior` para personalizar la serialización de cliente y servidor. El ejemplo siguiente muestra cómo aumentar la cuota `MaxItemsInObjectGraph` en el cliente.  
  
```csharp  
ChannelFactory<IDataService> factory = new ChannelFactory<IDataService>(binding, address);  
foreach (OperationDescription op in factory.Endpoint.Contract.Operations)  
{  
    DataContractSerializerOperationBehavior dataContractBehavior =  
                op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
    if (dataContractBehavior != null)  
    {  
        dataContractBehavior.MaxItemsInObjectGraph = 100000;  
    }  
}  
IDataService client = factory.CreateChannel();  
```  
  
```vb  
Dim factory As ChannelFactory(Of IDataService) = New ChannelFactory(Of IDataService)(binding, address)  
For Each op As OperationDescription In factory.Endpoint.Contract.Operations  
        Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
        If dataContractBehavior IsNot Nothing Then  
            dataContractBehavior.MaxItemsInObjectGraph = 100000  
        End If  
     Next  
    Dim client As IDataService = factory.CreateChannel  
```  
  
El siguiente es el código equivalente en el servicio, en el caso autohospedado:
  
```csharp  
ServiceHost serviceHost = new ServiceHost(typeof(IDataService))  
foreach (ServiceEndpoint ep in serviceHost.Description.Endpoints)  
{  
foreach (OperationDescription op in ep.Contract.Operations)  
{  
        DataContractSerializerOperationBehavior dataContractBehavior =  
           op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
        if (dataContractBehavior != null)  
        {  
            dataContractBehavior.MaxItemsInObjectGraph = 100000;  
        }  
}  
}  
serviceHost.Open();  
```  
  
```vb  
Dim serviceHost As ServiceHost = New ServiceHost(GetType(IDataService))  
        For Each ep As ServiceEndpoint In serviceHost.Description.Endpoints  
            For Each op As OperationDescription In ep.Contract.Operations  
                Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
  
                If dataContractBehavior IsNot Nothing Then  
                    dataContractBehavior.MaxItemsInObjectGraph = 100000  
                End If  
            Next  
        Next  
        serviceHost.Open()  
```  
  
 En el caso de hospedaje mediante web, debe crear una nueva clase derivada `ServiceHost` y utilizar un generador de host de servicio para conectarla.  
  
### <a name="controlling-serialization-settings-in-configuration"></a>Control de los ajustes de serialización en la configuración  
 El `MaxItemsInObjectGraph` e `IgnoreExtensionDataObject` se pueden controlar a través de la configuración utilizando el extremo `dataContractSerializer` o comportamiento de servicio, tal y como se muestra en el ejemplo siguiente.  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="LargeQuotaBehavior">  
                    <dataContractSerializer  
                      maxItemsInObjectGraph="100000" />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <client>  
            <endpoint address="http://example.com/myservice"  
                  behaviorConfiguration="LargeQuotaBehavior"  
                binding="basicHttpBinding" bindingConfiguration=""
                            contract="IDataService"  
                name="" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="shared-type-serialization-object-graph-preservation-and-custom-serializers"></a>Serialización de tipo compartido, preservación de gráfico de objeto y serializadores personalizados  
 <xref:System.Runtime.Serialization.DataContractSerializer> serializa utilizando nombres de contrato de datos y no nombres de tipo .NET. Esto es coherente con los principios de la arquitectura orientada a servicios y permite un gran grado de flexibilidad; los tipos .NET pueden cambiar sin afectar al contrato de conexión. En algún caso aislado, puede que desee serializar nombres de tipo .NET reales, introduciendo, de este modo, un acoplamiento robusto entre el cliente y el servidor, similar a la tecnología remota de .NET Framework. Esto no es una práctica recomendada, excepto en casos raros que suelen producirse al migrar a WCF desde la comunicación remota de .NET Framework. En este caso, debe utilizar la clase <xref:System.Runtime.Serialization.NetDataContractSerializer>, en lugar de la clase <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 El <xref:System.Runtime.Serialization.DataContractSerializer> serializa normalmente gráficos de objetos como árboles de objeto. Es decir, si se hace referencia al mismo objeto más de una vez, se serializa más de una vez. Por ejemplo, considere una instancia `PurchaseOrder` que tiene dos campos de tipo Dirección llamados `billTo` y `shipTo`. Si ambos campos están establecidos en la misma instancia de Dirección, hay dos instancias de Dirección idénticas después de la serialización y deserialización. Esto se hace porque no hay ninguna manera interoperable estándar de representar gráficos de objetos en XML (excepto para el estándar codificado SOAP heredado disponible en el <xref:System.Xml.Serialization.XmlSerializer>, tal y como se describe en la sección anterior en `Style` y `Use`). Serializar gráficos de objetos como árboles tiene ciertas desventajas, como, por ejemplo, que los gráficos con referencias circulares no se pueden serializar. De vez en cuando, es necesario intercambiar a serialización de gráficos de objetos verdadera, incluso aunque no sea interoperable. Esto se puede realizar mediante el uso del <xref:System.Runtime.Serialization.DataContractSerializer> construido mediante el parámetro `preserveObjectReferences` establecido en `true`.  
  
 De vez en cuando, los serializadores integrados no son suficientes para su escenario. En la mayoría de los casos, puede seguir utilizando la abstracción <xref:System.Runtime.Serialization.XmlObjectSerializer> desde la que se derivan <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.NetDataContractSerializer>.  
  
 Los tres casos anteriores (preservación de tipo .NET, preservación de gráfico de objetos y serialización basada en `XmlObjectSerializer` completamente personalizada) necesitan que se conecte un serializador personalizado. Para ello, realice los pasos siguientes:  
  
1. Escriba su propio comportamiento que deriva del <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>.  
  
2. Invalide los dos métodos `CreateSerializer` para devolver su propio serializador (<xref:System.Runtime.Serialization.NetDataContractSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer> con `preserveObjectReferences` establecido en `true` o su propio <xref:System.Runtime.Serialization.XmlObjectSerializer> personalizado).  
  
3. Antes de abrir el host de servicio o crear un canal de cliente, elimine el comportamiento <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> existente y conecte la clase derivada personalizada que cree en los pasos anteriores.  
  
 Para obtener más información acerca de los conceptos de serialización avanzada, vea [Serialización y deserialización](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).  
  
## <a name="see-also"></a>Consulte también

- [Utilización de la clase XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)
- [Cómo habilitar la transmisión](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)
- [Creación de un contrato de datos básicos para una clase o estructura](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
