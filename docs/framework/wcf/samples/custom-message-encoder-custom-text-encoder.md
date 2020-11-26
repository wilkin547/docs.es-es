---
title: 'Codificador de mensajes personalizado: codificador de texto personalizado'
description: Use este ejemplo para implementar un codificador de mensajes de texto personalizado mediante WCF. Este codificador admite todas las codificaciones de caracteres compatibles con la plataforma para la interoperabilidad.
ms.date: 03/30/2017
ms.assetid: 68ff5c74-3d33-4b44-bcae-e1d2f5dea0de
ms.openlocfilehash: 89f0bf09ba6408e24f642a67f2e7ac8243608dcb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240971"
---
# <a name="custom-message-encoder-custom-text-encoder"></a>Codificador de mensajes personalizado: codificador de texto personalizado

Este ejemplo muestra cómo implementar un codificador de mensajes de texto personalizado mediante Windows Communication Foundation (WCF).

> [!WARNING]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Text`

<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>De WCF solo admite las codificaciones UTF-8, UTF-16 y Big-Endian Unicode. El codificador de mensajes de texto personalizado en este ejemplo es compatible con todas las codificaciones de caracteres compatibles con la plataforma que pueden ser necesarias para la interoperabilidad. El ejemplo está compuesto de un programa de consola de cliente (. exe), una biblioteca de servicios (. dll) hospedada por Internet Information Services (IIS) y una biblioteca de codificador de mensajes de texto (. dll). El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta. La interfaz `ICalculator`, que expone las operaciones matemáticas (sumar, restar, multiplicar y dividir), define el contrato. El cliente realiza solicitudes sincrónicas a una operación matemática determinada y el servicio responde con el resultado. Tanto el cliente como el servicio utilizan `CustomTextMessageEncoder` en lugar del <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> predeterminado.

La implementación del codificador personalizado está compuesta de un generador de codificadores de mensajes, un codificador de mensajes, un elemento de enlace de la codificación de mensajes y un controlador de configuración. Muestra lo siguiente:

- Compilar un codificador personalizado y un generador de codificadores.

- Crear un elemento de enlace para un codificador personalizado.

- Utilizar la configuración de enlace personalizado para integrar los elementos de enlace personalizado.

- Desarrollar un controlador de configuración personalizado para permitir la configuración del archivo de un elemento de enlace personalizado.

## <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Instale ASP.NET 4,0 con el siguiente comando.

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

3. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).

4. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).

## <a name="message-encoder-factory-and-the-message-encoder"></a>Generador de codificadores de mensajes y el codificador de mensajes

Cuando se abre <xref:System.ServiceModel.ServiceHost> o el canal de cliente, el componente de tiempo de diseño `CustomTextMessageBindingElement` crea `CustomTextMessageEncoderFactory`. El generador crea `CustomTextMessageEncoder`. El codificador de mensajes funciona tanto en el modo de transmisión por secuencias como en el modo de almacenamiento en búfer. Utiliza respectivamente <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter> para leer y escribir mensajes respectivamente. En contraposición a los lectores y escritores XML optimizados de WCF que solo admiten UTF-8, UTF-16 y Big-Endian Unicode, estos lectores y escritores admiten toda la codificación compatible con la plataforma.

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
        this.contentType = $"{this.factory.MediaType}; charset={this.writerSettings.Encoding.HeaderName}";
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

Los elementos de enlace permiten la configuración de la pila en tiempo de ejecución de WCF. Para usar el codificador de mensajes personalizado en una aplicación WCF, se requiere un elemento de enlace que cree el generador del codificador del mensaje con la configuración adecuada en el nivel adecuado en la pila en tiempo de ejecución.

`CustomTextMessageBindingElement` deriva de la clase base <xref:System.ServiceModel.Channels.BindingElement> y hereda de la clase <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>. Esto permite que otros componentes de WCF reconozcan este elemento de enlace como un elemento de enlace de codificación de mensajes. La implementación de <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> devuelve una instancia del generador de codificadores de mensajes coincidente con los valores adecuados.

`CustomTextMessageBindingElement` expone los valores para `MessageVersion`, `ContentType` y `Encoding` a través de las propiedades. El codificador admite tanto las versiones Soap11Addressing como Soap12Addressing1. El valor predeterminado es Soap11Addressing1. El valor predeterminado de `ContentType` se establece como "text/xml". La propiedad `Encoding` le permite establecer el valor de la codificación de caracteres deseada. El cliente y el servicio de ejemplo utilizan la codificación de caracteres ISO-8859-1 (latin1), que no es compatible con <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> de WCF.

El código siguiente muestra cómo crear mediante programación el enlace usando el codificador de mensajes de texto personalizado.

```csharp
ICollection<BindingElement> bindingElements = new List<BindingElement>();
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();
CustomTextMessageBindingElement textBindingElement = new CustomTextMessageBindingElement();
bindingElements.Add(textBindingElement);
bindingElements.Add(httpBindingElement);
CustomBinding binding = new CustomBinding(bindingElements);
```

## <a name="adding-metadata-support-to-the-message-encoding-binding-element"></a>Adición de compatibilidad de metadatos al elemento de enlace de la codificación de mensajes

Cualquier tipo que deriva de <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> es responsable de actualizar la versión del enlace SOAP en el documento WSDL generado para el servicio. Esto se hace implementando el método `ExportEndpoint` en la interfaz <xref:System.ServiceModel.Description.IWsdlExportExtension> y modificando a continuación el WSDL generado. En este ejemplo, `CustomTextMessageBindingElement` utiliza la lógica de exportación de WSDL desde `TextMessageEncodingBindingElement`.

Para este ejemplo, la configuración del cliente se hace manualmente. No puede utilizar Svcutil.exe para generar la configuración del cliente porque `CustomTextMessageBindingElement` no exporta una aserción de directiva para describir su comportamiento. Generalmente debería implementar la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension> en un elemento de enlace personalizado para exportar una aserción de directiva personalizada que describa el comportamiento o la función implementada por el elemento de enlace. Para obtener un ejemplo de cómo exportar una aserción de directiva para un elemento de enlace personalizado, vea el ejemplo [Transport: UDP](transport-udp.md) .

## <a name="message-encoding-binding-configuration-handler"></a>Controlador de configuración de enlace de codificación de mensajes

La sección anterior muestra cómo utilizar mediante programación el codificador de mensajes de texto personalizado. `CustomTextMessageEncodingBindingSection` implementa un controlador de configuración que le permite especificar el uso de un codificador de mensajes de texto personalizado dentro de un archivo de configuración. La clase `CustomTextMessageEncodingBindingSection` se deriva de la clase <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> . La propiedad `BindingElementType` informa al sistema de configuración del tipo de elemento de enlace que se va a crear para esta sección.

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
