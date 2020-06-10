---
title: 'Codificador de mensajes personalizado: codificador de compresión'
ms.date: 03/30/2017
ms.assetid: 57450b6c-89fe-4b8a-8376-3d794857bfd7
ms.openlocfilehash: db20ec20579d6fcb0ec202920db0d7781b0676df
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600625"
---
# <a name="custom-message-encoder-compression-encoder"></a><span data-ttu-id="39344-102">Codificador de mensajes personalizado: codificador de compresión</span><span class="sxs-lookup"><span data-stu-id="39344-102">Custom Message Encoder: Compression Encoder</span></span>

<span data-ttu-id="39344-103">Este ejemplo muestra cómo implementar un codificador personalizado mediante la plataforma Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="39344-103">This sample demonstrates how to implement a custom encoder using the Windows Communication Foundation (WCF) platform.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39344-104">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="39344-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="39344-105">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="39344-105">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="39344-106">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="39344-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="39344-107">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="39344-107">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Compression`

## <a name="sample-details"></a><span data-ttu-id="39344-108">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="39344-108">Sample Details</span></span>

<span data-ttu-id="39344-109">Este ejemplo está compuesto de un programa de consola de cliente (.exe), un programa de consola de servicio autohospedado (.exe) y una biblioteca de codificador del mensaje de compresión (.dll).</span><span class="sxs-lookup"><span data-stu-id="39344-109">This sample consists of a client console program (.exe), a self-hosted service console program (.exe) and a compression message encoder library (.dll).</span></span> <span data-ttu-id="39344-110">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="39344-110">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="39344-111">El contrato está definido por la interfaz `ISampleServer`, que expone las operaciones de eco de cadena básica (`Echo` y `BigEcho`).</span><span class="sxs-lookup"><span data-stu-id="39344-111">The contract is defined by the `ISampleServer` interface, which exposes basic string echoing operations (`Echo` and `BigEcho`).</span></span> <span data-ttu-id="39344-112">El cliente realiza solicitudes sincrónicas a una operación determinada y el servicio responde repitiendo el mensaje en el cliente.</span><span class="sxs-lookup"><span data-stu-id="39344-112">The client makes synchronous requests to a given operation and the service replies by repeating the message back to the client.</span></span> <span data-ttu-id="39344-113">La actividad del cliente y el servicio está visible en las ventanas de la consola.</span><span class="sxs-lookup"><span data-stu-id="39344-113">Client and service activity is visible in the console windows.</span></span> <span data-ttu-id="39344-114">El intento de este ejemplo es mostrar cómo escribir un codificador personalizado y mostrar el impacto de compresión de un mensaje en la conexión.</span><span class="sxs-lookup"><span data-stu-id="39344-114">The intent of this sample is to show how to write a custom encoder and demonstrate the impact of compression of a message on the wire.</span></span> <span data-ttu-id="39344-115">Puede agregar la instrumentación al codificador del mensaje de compresión para calcular el tamaño del mensaje, el tiempo de procesamiento o ambos.</span><span class="sxs-lookup"><span data-stu-id="39344-115">You can add instrumentation to the compression message encoder to calculate message size, processing time, or both.</span></span>

> [!NOTE]
> <span data-ttu-id="39344-116">En el .NET Framework 4, se ha habilitado la descompresión automática en un cliente de WCF si el servidor envía una respuesta comprimida (creada con un algoritmo como GZip o DEFLATE).</span><span class="sxs-lookup"><span data-stu-id="39344-116">In the .NET Framework 4, automatic decompression has been enabled on a WCF client if the server is sending a compressed response (created with an algorithm such as GZip or Deflate).</span></span> <span data-ttu-id="39344-117">Si el servicio se hospeda en web en Internet Information Server (IIS), IIS se puede configurar para que el servicio envíe una respuesta cifrada.</span><span class="sxs-lookup"><span data-stu-id="39344-117">If the service is Web-hosted in Internet Information Server (IIS), then IIS can be configured for the service to send a compressed response.</span></span> <span data-ttu-id="39344-118">Se puede utilizar este ejemplo si se tiene que llevar a cabo la compresión y la descompresión tanto en el cliente como en el servicio, o si el servicio se auto-hospeda.</span><span class="sxs-lookup"><span data-stu-id="39344-118">This sample can be used if the requirement is to do compression and decompression on both the client and the service or if the service is self-hosted.</span></span>

<span data-ttu-id="39344-119">En el ejemplo se muestra cómo crear e integrar un codificador de mensajes personalizado en una aplicación WCF.</span><span class="sxs-lookup"><span data-stu-id="39344-119">The sample demonstrates how to build and integrate a custom message encoder into a WCF application.</span></span> <span data-ttu-id="39344-120">GZipEncoder.dll de la biblioteca se implementa tanto en el cliente como en el servicio.</span><span class="sxs-lookup"><span data-stu-id="39344-120">The library GZipEncoder.dll is deployed with both the client and the service.</span></span> <span data-ttu-id="39344-121">Este ejemplo también muestra el impacto de comprimir mensajes.</span><span class="sxs-lookup"><span data-stu-id="39344-121">This sample also demonstrates the impact of compressing messages.</span></span> <span data-ttu-id="39344-122">El código en GZipEncoder.dll muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39344-122">The code in GZipEncoder.dll demonstrates the following:</span></span>

- <span data-ttu-id="39344-123">Compilar un codificador personalizado y un generador de codificadores.</span><span class="sxs-lookup"><span data-stu-id="39344-123">Building a custom encoder and encoder factory.</span></span>

- <span data-ttu-id="39344-124">Desarrollar un elemento de enlace para un codificador personalizado.</span><span class="sxs-lookup"><span data-stu-id="39344-124">Developing a binding element for a custom encoder.</span></span>

- <span data-ttu-id="39344-125">Utilizar la configuración de enlace personalizado para integrar los elementos de enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="39344-125">Using the custom binding configuration for integrating custom binding elements.</span></span>

- <span data-ttu-id="39344-126">Desarrollar un controlador de configuración personalizado para permitir la configuración del archivo de un elemento de enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="39344-126">Developing a custom configuration handler to allow file configuration of a custom binding element.</span></span>

<span data-ttu-id="39344-127">Tal y como se ha indicado previamente, hay varios niveles que se implementan en un codificador personalizado.</span><span class="sxs-lookup"><span data-stu-id="39344-127">As indicated previously, there are several layers that are implemented in a custom encoder.</span></span> <span data-ttu-id="39344-128">Para mostrar mejor la relación entre cada uno de estos niveles, hay un orden simplificado de eventos para el inicio del servicio en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="39344-128">To better illustrate the relationship between each of these layers, a simplified order of events for service start-up is in the following list:</span></span>

1. <span data-ttu-id="39344-129">El servidor se inicia.</span><span class="sxs-lookup"><span data-stu-id="39344-129">The server starts.</span></span>

2. <span data-ttu-id="39344-130">Se lee la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="39344-130">The configuration information is read.</span></span>

    1. <span data-ttu-id="39344-131">La configuración de servicio registra el controlador de configuración personalizado.</span><span class="sxs-lookup"><span data-stu-id="39344-131">The service configuration registers the custom configuration handler.</span></span>

    2. <span data-ttu-id="39344-132">El host del servicio se crea y se abre.</span><span class="sxs-lookup"><span data-stu-id="39344-132">The service host is created and opened.</span></span>

    3. <span data-ttu-id="39344-133">El elemento de configuración personalizado crea y devuelve el elemento de enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="39344-133">The custom configuration element creates and returns the custom binding element.</span></span>

    4. <span data-ttu-id="39344-134">El elemento de enlace personalizado crea y devuelve el generador de codificadores de mensajes.</span><span class="sxs-lookup"><span data-stu-id="39344-134">The custom binding element creates and returns a message encoder factory.</span></span>

3. <span data-ttu-id="39344-135">Se recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="39344-135">A message is received.</span></span>

4. <span data-ttu-id="39344-136">El generador de codificadores de mensajes devuelve un codificador de mensaje para leer en el mensaje y escribir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="39344-136">The message encoder factory returns a message encoder for reading in the message and writing out the response.</span></span>

5. <span data-ttu-id="39344-137">El nivel del codificador se implementa como un generador de clases.</span><span class="sxs-lookup"><span data-stu-id="39344-137">The encoder layer is implemented as a class factory.</span></span> <span data-ttu-id="39344-138">Sólo se debe exponer públicamente el generador de clases del codificador para el codificador personalizado.</span><span class="sxs-lookup"><span data-stu-id="39344-138">Only the encoder class factory must be publicly exposed for the custom encoder.</span></span> <span data-ttu-id="39344-139">El elemento de enlace devuelve el objeto del generador cuando se crea el objeto <xref:System.ServiceModel.ServiceHost> o <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="39344-139">The factory object is returned by the binding element when the <xref:System.ServiceModel.ServiceHost> or <xref:System.ServiceModel.ChannelFactory%601> object is created.</span></span> <span data-ttu-id="39344-140">Los codificadores de mensaje pueden funcionar en un modo almacenado en búfer o en un modo de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="39344-140">Message encoders can operate in a buffered or streaming mode.</span></span> <span data-ttu-id="39344-141">Este ejemplo muestra ambos modos.</span><span class="sxs-lookup"><span data-stu-id="39344-141">This sample demonstrates both buffered mode and streaming mode.</span></span>

<span data-ttu-id="39344-142">Para cada modo hay un método `ReadMessage` y `WriteMessage` acompañante en la clase `MessageEncoder` abstracta.</span><span class="sxs-lookup"><span data-stu-id="39344-142">For each mode there is an accompanying `ReadMessage` and `WriteMessage` method on the abstract `MessageEncoder` class.</span></span> <span data-ttu-id="39344-143">Una mayoría del trabajo de codificación tiene lugar en estos métodos.</span><span class="sxs-lookup"><span data-stu-id="39344-143">A majority of the encoding work takes place in these methods.</span></span> <span data-ttu-id="39344-144">El ejemplo ajusta el texto existente y los codificadores de mensaje binarios.</span><span class="sxs-lookup"><span data-stu-id="39344-144">The sample wraps the existing text and binary message encoders.</span></span> <span data-ttu-id="39344-145">Esto permite al ejemplo delegar la lectura y escritura de la representación de la conexión de mensajes en el codificador interno y permite al codificador de compresión comprimir o descomprimir los resultados.</span><span class="sxs-lookup"><span data-stu-id="39344-145">This allows the sample to delegate the reading and writing of the wire representation of messages to the inner encoder and allows the compression encoder to compress or decompress the results.</span></span> <span data-ttu-id="39344-146">Dado que no hay ninguna canalización para la codificación de mensajes, este es el único modelo para usar varios codificadores en WCF.</span><span class="sxs-lookup"><span data-stu-id="39344-146">Because there is no pipeline for message encoding, this is the only model for using multiple encoders in WCF.</span></span> <span data-ttu-id="39344-147">Una vez descomprimido el mensaje, el mensaje resultante se pasa a la pila para que lo gestione la pila de canales.</span><span class="sxs-lookup"><span data-stu-id="39344-147">Once the message has been decompressed, the resulting message is passed up the stack for the channel stack to handle.</span></span> <span data-ttu-id="39344-148">Durante la compresión, el mensaje comprimido resultante se escribe directamente en la secuencia proporcionada.</span><span class="sxs-lookup"><span data-stu-id="39344-148">During compression, the resulting compressed message is written directly to the stream provided.</span></span>

<span data-ttu-id="39344-149">Este ejemplo utiliza los métodos del asistente (`CompressBuffer` y `DecompressBuffer`) para realizar la conversión de los búferes a secuencias para utilizar la clase `GZipStream`.</span><span class="sxs-lookup"><span data-stu-id="39344-149">This sample uses helper methods (`CompressBuffer` and `DecompressBuffer`) to perform conversion from buffers to streams to use the `GZipStream` class.</span></span>

<span data-ttu-id="39344-150">Las clases `ReadMessage` y `WriteMessage` almacenadas en búfer hacen uso de la clase `BufferManager`.</span><span class="sxs-lookup"><span data-stu-id="39344-150">The buffered `ReadMessage` and `WriteMessage` classes make use of the `BufferManager` class.</span></span> <span data-ttu-id="39344-151">Sólo se puede acceder al codificador mediante el generador de codificadores.</span><span class="sxs-lookup"><span data-stu-id="39344-151">The encoder is accessible only through the encoder factory.</span></span> <span data-ttu-id="39344-152">La clase `MessageEncoderFactory` abstracta proporciona una propiedad denominada `Encoder` para tener acceso al codificador actual y a un método denominado `CreateSessionEncoder` para crear un codificador que admite sesiones.</span><span class="sxs-lookup"><span data-stu-id="39344-152">The abstract `MessageEncoderFactory` class provides a property named `Encoder` for accessing the current encoder and a method named `CreateSessionEncoder` for creating an encoder that supports sessions.</span></span> <span data-ttu-id="39344-153">Este tipo de codificador se puede utilizar en el escenario donde el canal admite las sesiones, se ordena y es confiable.</span><span class="sxs-lookup"><span data-stu-id="39344-153">Such an encoder can be used in the scenario where the channel supports sessions, is ordered and is reliable.</span></span> <span data-ttu-id="39344-154">Este escenario permite la optimización en cada sesión de los datos escritos en la conexión.</span><span class="sxs-lookup"><span data-stu-id="39344-154">This scenario allows for optimization in each session of the data written to the wire.</span></span> <span data-ttu-id="39344-155">Si no es esto lo que se desea, no se debería sobrecargar el método base.</span><span class="sxs-lookup"><span data-stu-id="39344-155">If this is not desired, the base method should not be overloaded.</span></span> <span data-ttu-id="39344-156">La propiedad `Encoder` proporciona un mecanismo para tener acceso al codificador sin sesión. La implementación predeterminada del método `CreateSessionEncoder` devuelve el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="39344-156">The `Encoder` property provides a mechanism for accessing the session-less encoder and the default implementation of the `CreateSessionEncoder` method returns the value of the property.</span></span> <span data-ttu-id="39344-157">Dado que el ejemplo ajusta un codificador existente para proporcionar la compresión, la implementación `MessageEncoderFactory` acepta `MessageEncoderFactory` que representa el generador de codificadores interno.</span><span class="sxs-lookup"><span data-stu-id="39344-157">Because the sample wraps an existing encoder to provide compression, the `MessageEncoderFactory` implementation accepts a `MessageEncoderFactory` that represents the inner encoder factory.</span></span>

<span data-ttu-id="39344-158">Ahora que el codificador y el generador de codificador están definidos, se pueden usar con un cliente y un servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="39344-158">Now that the encoder and encoder factory are defined, they can be used with a WCF client and service.</span></span> <span data-ttu-id="39344-159">Sin embargo, se deben agregar estos codificadores a la pila de canales.</span><span class="sxs-lookup"><span data-stu-id="39344-159">However, these encoders must be added to the channel stack.</span></span> <span data-ttu-id="39344-160">Puede derivar las clases <xref:System.ServiceModel.ServiceHost> y <xref:System.ServiceModel.ChannelFactory%601> e invalidar los métodos `OnInitialize` para agregar manualmente este generador de codificadores.</span><span class="sxs-lookup"><span data-stu-id="39344-160">You can derive classes from the <xref:System.ServiceModel.ServiceHost> and <xref:System.ServiceModel.ChannelFactory%601> classes and override the `OnInitialize` methods to add this encoder factory manually.</span></span> <span data-ttu-id="39344-161">También puede exponer el generador de codificadores a través de un elemento de enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="39344-161">You can also expose the encoder factory through a custom binding element.</span></span>

<span data-ttu-id="39344-162">Para crear un nuevo elemento de enlace personalizado, derive una clase desde la clase <xref:System.ServiceModel.Channels.BindingElement>.</span><span class="sxs-lookup"><span data-stu-id="39344-162">To create a new custom binding element, derive a class from the <xref:System.ServiceModel.Channels.BindingElement> class.</span></span> <span data-ttu-id="39344-163">Hay, sin embargo, varios tipos de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="39344-163">There are, however, several types of binding elements.</span></span> <span data-ttu-id="39344-164">Para garantizar que el elemento de enlace personalizado se reconozca como un elemento de enlace de la codificación de mensajes, debe implementar también <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="39344-164">To ensure that the custom binding element is recognized as a message encoding binding element, you also must implement the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.</span></span> <span data-ttu-id="39344-165"><xref:System.ServiceModel.Channels.MessageEncodingBindingElement> expone un método para crear un nuevo generador de codificadores de mensajes (`CreateMessageEncoderFactory`), que se implementa para devolver una instancia del generador de codificadores de mensajes correspondiente.</span><span class="sxs-lookup"><span data-stu-id="39344-165">The <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> exposes a method for creating a new message encoder factory (`CreateMessageEncoderFactory`), which is implemented to return an instance of the matching message encoder factory.</span></span> <span data-ttu-id="39344-166">Además, <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> tiene una propiedad para indicar la versión de direccionamiento.</span><span class="sxs-lookup"><span data-stu-id="39344-166">Additionally, the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> has a property to indicate the addressing version.</span></span> <span data-ttu-id="39344-167">Dado que este ejemplo ajusta los codificadores existentes, la implementación del ejemplo también ajusta los elementos de enlace del codificador existentes y lleva un elemento de enlace del codificador interno como un parámetro al constructor y lo expone mediante una propiedad.</span><span class="sxs-lookup"><span data-stu-id="39344-167">Because this sample wraps the existing encoders, the sample implementation also wraps the existing encoder binding elements and takes an inner encoder binding element as a parameter to the constructor and exposes it through a property.</span></span> <span data-ttu-id="39344-168">El código de ejemplo siguiente muestra la implementación de la clase `GZipMessageEncodingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="39344-168">The following sample code shows the implementation of the `GZipMessageEncodingBindingElement` class.</span></span>

```csharp
public sealed class GZipMessageEncodingBindingElement
                        : MessageEncodingBindingElement //BindingElement
                        , IPolicyExportExtension
{

    //We use an inner binding element to store information
    //required for the inner encoder.
    MessageEncodingBindingElement innerBindingElement;

        //By default, use the default text encoder as the inner encoder.
        public GZipMessageEncodingBindingElement()
            : this(new TextMessageEncodingBindingElement()) { }

    public GZipMessageEncodingBindingElement(MessageEncodingBindingElement messageEncoderBindingElement)
    {
        this.innerBindingElement = messageEncoderBindingElement;
    }

    public MessageEncodingBindingElement InnerMessageEncodingBindingElement
    {
        get { return innerBindingElement; }
        set { innerBindingElement = value; }
    }

    //Main entry point into the encoder binding element.
    // Called by WCF to get the factory that creates the
    //message encoder.
    public override MessageEncoderFactory CreateMessageEncoderFactory()
    {
        return new
GZipMessageEncoderFactory(innerBindingElement.CreateMessageEncoderFactory());
    }

    public override MessageVersion MessageVersion
    {
        get { return innerBindingElement.MessageVersion; }
        set { innerBindingElement.MessageVersion = value; }
    }

    public override BindingElement Clone()
    {
        return new
        GZipMessageEncodingBindingElement(this.innerBindingElement);
    }

    public override T GetProperty<T>(BindingContext context)
    {
        if (typeof(T) == typeof(XmlDictionaryReaderQuotas))
        {
            return innerBindingElement.GetProperty<T>(context);
        }
        else
        {
            return base.GetProperty<T>(context);
        }
    }

    public override IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)
    {
        if (context == null)
            throw new ArgumentNullException("context");

        context.BindingParameters.Add(this);
        return context.BuildInnerChannelFactory<TChannel>();
    }

    public override IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)
    {
        if (context == null)
            throw new ArgumentNullException("context");

        context.BindingParameters.Add(this);
        return context.BuildInnerChannelListener<TChannel>();
    }

    public override bool CanBuildChannelListener<TChannel>(BindingContext context)
    {
        if (context == null)
            throw new ArgumentNullException("context");

        context.BindingParameters.Add(this);
        return context.CanBuildInnerChannelListener<TChannel>();
    }

    void IPolicyExportExtension.ExportPolicy(MetadataExporter exporter, PolicyConversionContext policyContext)
    {
        if (policyContext == null)
        {
            throw new ArgumentNullException("policyContext");
        }
       XmlDocument document = new XmlDocument();
       policyContext.GetBindingAssertions().Add(document.CreateElement(
            GZipMessageEncodingPolicyConstants.GZipEncodingPrefix,
            GZipMessageEncodingPolicyConstants.GZipEncodingName,
            GZipMessageEncodingPolicyConstants.GZipEncodingNamespace));
    }
}
```

<span data-ttu-id="39344-169">Observe que la clase `GZipMessageEncodingBindingElement` implementa la interfaz `IPolicyExportExtension`, para que este elemento de enlace se pueda exportar como una directiva en metadatos, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="39344-169">Note that `GZipMessageEncodingBindingElement` class implements the `IPolicyExportExtension` interface, so that this binding element can be exported as a policy in metadata, as shown in the following example.</span></span>

```xml
<wsp:Policy wsu:Id="BufferedHttpSampleServer_ISampleServer_policy">
    <wsp:ExactlyOne>
      <wsp:All>
        <gzip:text xmlns:gzip=
        "http://schemas.microsoft.com/ws/06/2004/mspolicy/netgzip1" />
       <wsaw:UsingAddressing />
     </wsp:All>
   </wsp:ExactlyOne>
</wsp:Policy>
```

<span data-ttu-id="39344-170">La clase `GZipMessageEncodingBindingElementImporter` implementa la interfaz `IPolicyImportExtension` Esta clase importa la directiva para `GZipMessageEncodingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="39344-170">The `GZipMessageEncodingBindingElementImporter` class implements the `IPolicyImportExtension` interface, this class imports policy for `GZipMessageEncodingBindingElement`.</span></span> <span data-ttu-id="39344-171">La herramienta Svcutil.exe se puede utilizar para importar las directivas al archivo de configuración. Para administrar `GZipMessageEncodingBindingElement`, se debería agregar lo siguiente a Svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="39344-171">Svcutil.exe tool can be used to import policies to the configuration file, to handle `GZipMessageEncodingBindingElement`, the following should be added to Svcutil.exe.config.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <extensions>
      <bindingElementExtensions>
        <add name="gzipMessageEncoding"
          type=
            "Microsoft.ServiceModel.Samples.GZipMessageEncodingElement, GZipEncoder, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
      </bindingElementExtensions>
    </extensions>
    <client>
      <metadata>
        <policyImporters>
          <remove type=
"System.ServiceModel.Channels.MessageEncodingBindingElementImporter, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
          <extension type=
"Microsoft.ServiceModel.Samples.GZipMessageEncodingBindingElementImporter, GZipEncoder, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
        </policyImporters>
      </metadata>
    </client>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="39344-172">Ahora que hay un elemento de enlace correspondiente para el codificador de compresión, se puede enlazar mediante programación con el servicio o cliente construyendo un nuevo objeto de enlace personalizado y agregando el elemento de enlace personalizado a él, tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="39344-172">Now that there is a matching binding element for the compression encoder, it can be programmatically hooked into the service or client by constructing a new custom binding object and adding the custom binding element to it, as shown in the following sample code.</span></span>

```csharp
ICollection<BindingElement> bindingElements = new List<BindingElement>();
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();
GZipMessageEncodingBindingElement compBindingElement = new GZipMessageEncodingBindingElement ();
bindingElements.Add(compBindingElement);
bindingElements.Add(httpBindingElement);
CustomBinding binding = new CustomBinding(bindingElements);
binding.Name = "SampleBinding";
binding.Namespace = "http://tempuri.org/bindings";
```

<span data-ttu-id="39344-173">Aunque esto puede ser suficiente para la mayoría de escenarios de usuario, ser compatible con una configuración de archivo es fundamental si se hospeda en web un servicio.</span><span class="sxs-lookup"><span data-stu-id="39344-173">While this may be sufficient for the majority of user scenarios, supporting a file configuration is critical if a service is to be Web-hosted.</span></span> <span data-ttu-id="39344-174">Para admitir el escenario hospedado en web, debe desarrollar un controlador de configuración personalizado para permitir que se configure un elemento de enlace personalizado en un archivo.</span><span class="sxs-lookup"><span data-stu-id="39344-174">To support the Web-hosted scenario, you must develop a custom configuration handler to allow a custom binding element to be configurable in a file.</span></span>

<span data-ttu-id="39344-175">Puede compilar un controlador de configuración para el elemento de enlace en la parte superior del sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="39344-175">You can build a configuration handler for the binding element on top of the configuration system.</span></span> <span data-ttu-id="39344-176">El controlador de configuración para el elemento de enlace debe derivar de la clase <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>.</span><span class="sxs-lookup"><span data-stu-id="39344-176">The configuration handler for the binding element must derive from the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> class.</span></span> <span data-ttu-id="39344-177"><xref:System.ServiceModel.Configuration.BindingElementExtensionElement.BindingElementType?displayProperty=nameWithType>Informa al sistema de configuración del tipo de elemento de enlace que se va a crear para esta sección.</span><span class="sxs-lookup"><span data-stu-id="39344-177">The <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.BindingElementType?displayProperty=nameWithType> informs the configuration system of the type of binding element to create for this section.</span></span> <span data-ttu-id="39344-178">Todos los aspectos de `BindingElement` que se pueden establecer se deberían exponer como propiedades en la clase derivada <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>.</span><span class="sxs-lookup"><span data-stu-id="39344-178">All aspects of the `BindingElement` that can be set should be exposed as properties in the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> derived class.</span></span> <span data-ttu-id="39344-179"><xref:System.Configuration.ConfigurationPropertyAttribute>Ayuda a asignar los atributos del elemento de configuración a las propiedades y a establecer los valores predeterminados si faltan atributos.</span><span class="sxs-lookup"><span data-stu-id="39344-179">The <xref:System.Configuration.ConfigurationPropertyAttribute> assists in mapping the configuration element attributes to the properties and setting default values if attributes are missing.</span></span> <span data-ttu-id="39344-180">Después de cargar y aplicar los valores de configuración a las propiedades, se llama al método <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A?displayProperty=nameWithType>, que convierte las propiedades en una instancia concreta de un elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="39344-180">After the values from configuration are loaded and applied to the properties, the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A?displayProperty=nameWithType> method is called, which converts the properties into a concrete instance of a binding element.</span></span> <span data-ttu-id="39344-181">El <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.ApplyConfiguration%2A?displayProperty=nameWithType> método se usa para convertir las propiedades de la <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> clase derivada en los valores que se van a establecer en el elemento de enlace que se acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="39344-181">The <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.ApplyConfiguration%2A?displayProperty=nameWithType> method is used to convert the properties on the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> derived class into the values to be set on the newly created binding element.</span></span>

<span data-ttu-id="39344-182">En el siguiente código de ejemplo muestra la implementación de `GZipMessageEncodingElement`.</span><span class="sxs-lookup"><span data-stu-id="39344-182">The following sample code shows the implementation of the `GZipMessageEncodingElement`.</span></span>

```csharp
public class GZipMessageEncodingElement : BindingElementExtensionElement
{
    public GZipMessageEncodingElement()
    {
    }

//Called by the WCF to discover the type of binding element this
//config section enables
    public override Type BindingElementType
    {
        get { return typeof(GZipMessageEncodingBindingElement); }
    }

    //The only property we need to configure for our binding element is
    //the type of inner encoder to use. Here, we support text and
    //binary.
    [ConfigurationProperty("innerMessageEncoding",
                         DefaultValue = "textMessageEncoding")]
    public string InnerMessageEncoding
    {
        get { return (string)base["innerMessageEncoding"]; }
        set { base["innerMessageEncoding"] = value; }
    }

    //Called by the WCF to apply the configuration settings (the
    //property above) to the binding element
    public override void ApplyConfiguration(BindingElement bindingElement)
    {
        GZipMessageEncodingBindingElement binding =
                (GZipMessageEncodingBindingElement)bindingElement;
        PropertyInformationCollection propertyInfo =
                    this.ElementInformation.Properties;
        if (propertyInfo["innerMessageEncoding"].ValueOrigin !=
                                     PropertyValueOrigin.Default)
        {
            switch (this.InnerMessageEncoding)
            {
                case "textMessageEncoding":
                    binding.InnerMessageEncodingBindingElement =
                      new TextMessageEncodingBindingElement();
                    break;
                case "binaryMessageEncoding":
                    binding.InnerMessageEncodingBindingElement =
                         new BinaryMessageEncodingBindingElement();
                    break;
            }
        }
    }

    //Called by the WCF to create the binding element
    protected override BindingElement CreateBindingElement()
    {
        GZipMessageEncodingBindingElement bindingElement =
                new GZipMessageEncodingBindingElement();
        this.ApplyConfiguration(bindingElement);
        return bindingElement;
    }
}
```

<span data-ttu-id="39344-183">Este controlador de configuración asigna a la representación siguiente en App.config o Web.config para el servicio o cliente.</span><span class="sxs-lookup"><span data-stu-id="39344-183">This configuration handler maps to the following representation in the App.config or Web.config for the service or client.</span></span>

```xml
<gzipMessageEncoding innerMessageEncoding="textMessageEncoding" />
```

<span data-ttu-id="39344-184">Para utilizar este controlador de configuración, se debe registrar en el [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento, tal y como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="39344-184">To use this configuration handler, it must be registered within the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, as shown in the following sample configuration.</span></span>

```xml
<extensions>
    <bindingElementExtensions>
       <add
           name="gzipMessageEncoding"
           type=
           "Microsoft.ServiceModel.Samples.GZipMessageEncodingElement,
           GZipEncoder, Version=1.0.0.0, Culture=neutral,
           PublicKeyToken=null" />
      </bindingElementExtensions>
</extensions>
```

<span data-ttu-id="39344-185">Al ejecutar el servidor, las solicitudes y respuestas de la operación se muestran en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="39344-185">When you run the server, the operation requests and responses are displayed in the console window.</span></span> <span data-ttu-id="39344-186">Presione ENTRAR en la ventana para cerrar el servidor.</span><span class="sxs-lookup"><span data-stu-id="39344-186">Press ENTER in the window to shut down the server.</span></span>

```console
Press Enter key to Exit.

        Server Echo(string input) called:
        Client message: Simple hello

        Server BigEcho(string[] input) called:
        64 client messages
```

<span data-ttu-id="39344-187">Al ejecutar el cliente, las solicitudes y respuestas de la operación se muestran en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="39344-187">When you run the client, the operation requests and responses are displayed in the console window.</span></span> <span data-ttu-id="39344-188">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="39344-188">Press ENTER in the client window to shut down the client.</span></span>

```console
Calling Echo(string):
Server responds: Simple hello Simple hello

Calling BigEcho(string[]):
Server responds: Hello 0

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="39344-189">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="39344-189">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="39344-190">Instale ASP.NET 4,0 con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="39344-190">Install ASP.NET 4.0 using the following command:</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="39344-191">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="39344-191">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="39344-192">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="39344-192">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="39344-193">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="39344-193">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39344-194">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="39344-194">The samples may already be installed on your machine.</span></span> <span data-ttu-id="39344-195">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="39344-195">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="39344-196">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="39344-196">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="39344-197">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="39344-197">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Compression`
