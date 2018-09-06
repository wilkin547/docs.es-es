---
title: 'Codificador de mensaje personalizado: codificador de texto personalizado'
ms.date: 03/30/2017
ms.assetid: 68ff5c74-3d33-4b44-bcae-e1d2f5dea0de
ms.openlocfilehash: aeb1690d7ead9116bd9c4afe3c64d65d8f51ad50
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43800705"
---
# <a name="custom-message-encoder-custom-text-encoder"></a>Codificador de mensaje personalizado: codificador de texto personalizado
Este ejemplo muestra cómo implementar un codificador de mensajes de texto personalizado mediante Windows Communication Foundation (WCF).  
  
> [!WARNING]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Text`  
  
 El <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> de WCF admite las codificaciones UTF-8, UTF-16 y Big Endean Unicode. El codificador de mensajes de texto personalizado en este ejemplo admite toda la codificación de caracteres admitida por la plataforma que puede ser necesaria para la interoperabilidad. El ejemplo está compuesto de un programa de consola de cliente (.exe), una biblioteca de servicios (.dll) hospedada por Internet Information Services (IIS) y una biblioteca (.dll) de codificador de mensajes de texto. El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta. La interfaz `ICalculator`, que expone las operaciones matemáticas (sumar, restar, multiplicar y dividir), define el contrato. El cliente realiza solicitudes sincrónicas a una operación matemática determinada y el servicio responde con el resultado. Tanto el cliente como el servicio utilizan `CustomTextMessageEncoder` en lugar del <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> predeterminado.  
  
 La implementación del codificador personalizado está compuesta de un generador de codificadores de mensajes, un codificador de mensajes, un elemento de enlace de la codificación de mensajes y un controlador de configuración. Muestra lo siguiente:  
  
-   Compilar un codificador personalizado y un generador de codificadores.  
  
-   Crear un elemento de enlace para un codificador personalizado.  
  
-   Utilizar la configuración de enlace personalizado para integrar los elementos de enlace personalizado.  
  
-   Desarrollar un controlador de configuración personalizado para permitir la configuración del archivo de un elemento de enlace personalizado.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Instale [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mediante el siguiente comando.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Para compilar la solución, siga las instrucciones de [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="message-encoder-factory-and-the-message-encoder"></a>Generador de codificadores de mensajes y el codificador de mensajes  
 Cuando se abre <xref:System.ServiceModel.ServiceHost> o el canal de cliente, el componente de tiempo de diseño `CustomTextMessageBindingElement` crea `CustomTextMessageEncoderFactory`. El generador crea `CustomTextMessageEncoder`. El codificador de mensajes funciona tanto en el modo de transmisión por secuencias como en el modo de almacenamiento en búfer. Utiliza respectivamente <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter> para leer y escribir mensajes respectivamente. En lugar de la optimizado lectores y escritores XML de WCF que admiten solo UTF-8, UTF-16 y Big-Endean Unicode estos lectores y escritores admiten toda la codificación compatible con la plataforma.  
  
 El ejemplo de código siguiente muestra CustomTextMessageEncoder.  
  
```csharp  
public class CustomTextMessageEncoder : MessageEncoder  
{  
    private CustomTextMessageEncoderFactory factory;  
    private XmlWriterSettings writerSettings;  
    private string contentType;  
  
    public CustomTextMessageEncoder(CustomTextMessageEncoderFactory factory)  
    {  
        this.factory = factory;  
  
        this.writerSettings = new XmlWriterSettings();  
        this.writerSettings.Encoding = Encoding.GetEncoding(factory.CharSet);  
        this.contentType = string.Format("{0}; charset={1}",   
            this.factory.MediaType, this.writerSettings.Encoding.HeaderName);  
    }  
  
    public override string ContentType  
    {  
        get  
        {  
            return this.contentType;  
        }  
    }  
  
    public override string MediaType  
    {  
        get   
        {  
            return factory.MediaType;  
        }  
    }  
  
    public override MessageVersion MessageVersion  
    {  
        get   
        {  
            return this.factory.MessageVersion;  
        }  
    }  
  
    public override Message ReadMessage(ArraySegment<byte> buffer, BufferManager bufferManager, string contentType)  
    {     
        byte[] msgContents = new byte[buffer.Count];  
        Array.Copy(buffer.Array, buffer.Offset, msgContents, 0, msgContents.Length);  
        bufferManager.ReturnBuffer(buffer.Array);  
  
        MemoryStream stream = new MemoryStream(msgContents);  
        return ReadMessage(stream, int.MaxValue);  
    }  
  
    public override Message ReadMessage(Stream stream, int maxSizeOfHeaders, string contentType)  
    {  
        XmlReader reader = XmlReader.Create(stream);  
        return Message.CreateMessage(reader, maxSizeOfHeaders, this.MessageVersion);  
    }  
  
    public override ArraySegment<byte> WriteMessage(Message message, int maxMessageSize, BufferManager bufferManager, int messageOffset)  
    {  
        MemoryStream stream = new MemoryStream();  
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);  
        message.WriteMessage(writer);  
        writer.Close();  
  
        byte[] messageBytes = stream.GetBuffer();  
        int messageLength = (int)stream.Position;  
        stream.Close();  
  
        int totalLength = messageLength + messageOffset;  
        byte[] totalBytes = bufferManager.TakeBuffer(totalLength);  
        Array.Copy(messageBytes, 0, totalBytes, messageOffset, messageLength);  
  
        ArraySegment<byte> byteArray = new ArraySegment<byte>(totalBytes, messageOffset, messageLength);  
        return byteArray;  
    }  
  
    public override void WriteMessage(Message message, Stream stream)  
    {  
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);  
        message.WriteMessage(writer);  
        writer.Close();  
    }  
}  
```  
  
 El ejemplo de código siguiente muestra cómo compilar el generador de codificadores de mensajes.  
  
```csharp  
public class CustomTextMessageEncoderFactory : MessageEncoderFactory  
{  
    private MessageEncoder encoder;  
    private MessageVersion version;  
    private string mediaType;  
    private string charSet;  
  
    internal CustomTextMessageEncoderFactory(string mediaType, string charSet,  
        MessageVersion version)  
    {  
        this.version = version;  
        this.mediaType = mediaType;  
        this.charSet = charSet;  
        this.encoder = new CustomTextMessageEncoder(this);  
    }  
  
    public override MessageEncoder Encoder  
    {  
        get   
        {   
            return this.encoder;  
        }  
    }  
  
    public override MessageVersion MessageVersion  
    {  
        get   
        {   
            return this.version;  
        }  
    }  
  
    internal string MediaType  
    {  
        get  
        {  
            return this.mediaType;  
        }  
    }  
  
    internal string CharSet  
    {  
        get  
        {  
            return this.charSet;  
        }  
    }  
}  
```  
  
## <a name="message-encoding-binding-element"></a>Elemento de enlace de codificación de mensajes  
 Los elementos de enlace permiten la configuración de la pila de tiempo de ejecución WCF. Para usar el codificador de mensajes personalizados en una aplicación de WCF, se requiere un elemento de enlace que crea el generador del codificador de mensajes con la configuración adecuada en el nivel adecuado de la pila de tiempo de ejecución.  
  
 `CustomTextMessageBindingElement` deriva de la clase base <xref:System.ServiceModel.Channels.BindingElement> y hereda de la clase <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>. Esto permite que otros componentes WCF reconocer este elemento de enlace como un elemento de enlace de codificación de mensajes. La implementación de <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> devuelve una instancia del generador de codificadores de mensajes coincidente con los valores adecuados.  
  
 `CustomTextMessageBindingElement` expone los valores para `MessageVersion`, `ContentType` y `Encoding` a través de las propiedades. El codificador admite tanto las versiones Soap11Addressing como Soap12Addressing1. El valor predeterminado es Soap11Addressing1. El valor predeterminado de `ContentType` se establece como "text/xml". La propiedad `Encoding` le permite establecer el valor de la codificación de caracteres deseada. El ejemplo de cliente y el servicio usa la codificación de caracteres ISO-8859-1 (Latin1), que no es compatible con la <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> de WCF.  
  
 El código siguiente muestra cómo crear mediante programación el enlace usando el codificador de mensajes de texto personalizado.  
  
```  
ICollection<BindingElement> bindingElements = new List<BindingElement>();  
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();  
CustomTextMessageBindingElement textBindingElement = new CustomTextMessageBindingElement();  
bindingElements.Add(textBindingElement);  
bindingElements.Add(httpBindingElement);  
CustomBinding binding = new CustomBinding(bindingElements);  
```  
  
## <a name="adding-metadata-support-to-the-message-encoding-binding-element"></a>Adición de compatibilidad de metadatos al elemento de enlace de la codificación de mensajes  
 Cualquier tipo que deriva de <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> es responsable de actualizar la versión del enlace SOAP en el documento WSDL generado para el servicio. Esto se hace implementando el método `ExportEndpoint` en la interfaz <xref:System.ServiceModel.Description.IWsdlExportExtension> y modificando a continuación el WSDL generado. En este ejemplo, `CustomTextMessageBindingElement` utiliza la lógica de exportación de WSDL desde `TextMessageEncodingBinidngElement`.  
  
 Para este ejemplo, la configuración del cliente se hace manualmente. No puede utilizar Svcutil.exe para generar la configuración del cliente porque `CustomTextMessageBindingElement` no exporta una aserción de directiva para describir su comportamiento. Generalmente debería implementar la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension> en un elemento de enlace personalizado para exportar una aserción de directiva personalizada que describa el comportamiento o la función implementada por el elemento de enlace. Para obtener un ejemplo de cómo exportar una aserción de directiva para un elemento de enlace personalizado, vea el [transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) ejemplo.  
  
## <a name="message-encoding-binding-configuration-handler"></a>Controlador de configuración de enlace de codificación de mensajes  
 La sección anterior muestra cómo utilizar mediante programación el codificador de mensajes de texto personalizado. `CustomTextMessageEncodingBindingSection` implementa un controlador de configuración que le permite especificar el uso de un codificador de mensajes de texto personalizado dentro de un archivo de configuración. La clase `CustomTextMessageEncodingBindingSection` se deriva de la clase <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>. La propiedad `BindingElementType` informa al sistema de configuración del tipo de elemento de enlace que se va a crear para esta sección.  
  
 Todos los valores definidos por `CustomTextMessageBindingElement` se exponen como propiedades en `CustomTextMessageEncodingBindingSection`. <xref:System.Configuration.ConfigurationPropertyAttribute> ayuda en la asignación de atributos de elemento de configuración para las propiedades y en la definición de valores predeterminados si el atributo no está definido. Después de cargar y aplicar los valores de la configuración a las propiedades del tipo, se llama al método <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A>, que convierte las propiedades en una instancia concreta de un elemento de enlace.  
  
 Este controlador de configuración asigna a la representación siguiente en App.config o Web.config para el servicio o cliente.  
  
```xml  
<customTextMessageEncoding encoding="utf-8" contentType="text/xml" messageVersion="Soap11Addressing1" />  
```  
  
 El ejemplo utiliza la codificación ISO-8859-1.  
  
 Para utilizar este controlador de configuración, se debe registrar utilizando el elemento de configuración siguiente.  
  
```xml  
<extensions>  
    <bindingElementExtensions>  
        <add name="customTextMessageEncoding" type="   
Microsoft.ServiceModel.Samples.CustomTextMessageEncodingBindingSection,   
                  CustomTextMessageEncoder" />  
    </bindingElementExtensions>  
</extensions>  
```  
  
## <a name="see-also"></a>Vea también
