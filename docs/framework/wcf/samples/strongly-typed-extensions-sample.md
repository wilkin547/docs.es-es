---
title: Ejemplo de extensiones fuertemente tipadas
ms.date: 03/30/2017
ms.assetid: 02220f11-1a83-441c-9e5a-85f9a9367572
ms.openlocfilehash: e8c3bf202a1fb76d383f0a3fe15084d19a1d51fb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600885"
---
# <a name="strongly-typed-extensions-sample"></a><span data-ttu-id="88f32-102">Ejemplo de extensiones fuertemente tipadas</span><span class="sxs-lookup"><span data-stu-id="88f32-102">Strongly typed extensions sample</span></span>

<span data-ttu-id="88f32-103">El ejemplo utiliza la clase <xref:System.ServiceModel.Syndication.SyndicationFeed> para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="88f32-103">The sample uses the <xref:System.ServiceModel.Syndication.SyndicationFeed> class for the purposes of the example.</span></span> <span data-ttu-id="88f32-104">Sin embargo, los modelos mostrados en este ejemplo se pueden utilizar con todas las clases de sindicación que admiten los datos de la extensión:</span><span class="sxs-lookup"><span data-stu-id="88f32-104">However, the patterns demonstrated in this sample can be used with all of the Syndication classes that support extension data.</span></span>  
  
 <span data-ttu-id="88f32-105">El modelo de objetos de distribución (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem> y las clases relacionadas) admite el acceso fuertemente tipado en datos de extensión utilizando las propiedades <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> y <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="88f32-105">The Syndication object model (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, and related classes) supports loosely-typed access to extension data by using the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> properties.</span></span> <span data-ttu-id="88f32-106">En este ejemplo se muestra cómo proporcionar acceso fuertemente tipado a los datos de extensión mediante la implementación de clases derivadas personalizadas de <xref:System.ServiceModel.Syndication.SyndicationFeed> y <xref:System.ServiceModel.Syndication.SyndicationItem> que hacen que estén disponibles ciertas extensiones específicas de la aplicación como propiedades fuertemente tipadas.</span><span class="sxs-lookup"><span data-stu-id="88f32-106">This sample shows how to provide strongly typed access to extension data by implementing custom derived classes of <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> that make available certain application-specific extensions as strongly typed properties.</span></span>  
  
 <span data-ttu-id="88f32-107">Como ejemplo, este ejemplo muestra cómo implementar un elemento de extensión definido en el RFC de las extensiones de subprocesamiento de Atom propuesto.</span><span class="sxs-lookup"><span data-stu-id="88f32-107">As an example, this sample shows how to implement an extension element defined in the proposed Atom Threading Extensions RFC.</span></span> <span data-ttu-id="88f32-108">Esto solo es para fines ilustrativos y este ejemplo no está diseñado para que sea una implementación completa de la especificación propuesta.</span><span class="sxs-lookup"><span data-stu-id="88f32-108">This is for demonstration purposes only and this sample is not intended to be a full implementation of the proposed specification.</span></span>  
  
## <a name="sample-xml"></a><span data-ttu-id="88f32-109">XML de ejemplo</span><span class="sxs-lookup"><span data-stu-id="88f32-109">Sample XML</span></span>  
 <span data-ttu-id="88f32-110">El siguiente ejemplo de XML muestra una entrada de Atom 1.0 con un elemento de extensión `<in-reply-to>` adicional.</span><span class="sxs-lookup"><span data-stu-id="88f32-110">The following XML example shows an Atom 1.0 entry with an additional `<in-reply-to>` extension element.</span></span>  
  
```xml  
<entry>  
    <id>tag:example.org,2005:1,2</id>  
    <title type="text">Another response to the original</title>  
    <summary type="text">  
         This is a response to the original entry</summary>  
    <updated>2006-03-01T12:12:13Z</updated>  
    <link href="http://www.example.org/entries/1/2" />  
    <in-reply-to p3:ref="tag:example.org,2005:1"
                 p3:href="http://www.example.org/entries/1"
                 p3:type="application/xhtml+xml"
                 xmlns:p3="http://contoso.org/syndication/thread/1.0"
                 xmlns="http://contoso.org/syndication/thread/1.0">  
      <anotherElement xmlns="http://www.w3.org/2005/Atom">  
                     Some more data</anotherElement>  
      <aDifferentElement xmlns="http://www.w3.org/2005/Atom">  
                     Even more data</aDifferentElement>  
    </in-reply-to>  
</entry>  
```  
  
 <span data-ttu-id="88f32-111">El `<in-reply-to>` elemento especifica tres atributos obligatorios ( `ref` , `type` y), a `href` la vez que también permite la presencia de atributos de extensión y elementos de extensión adicionales.</span><span class="sxs-lookup"><span data-stu-id="88f32-111">The `<in-reply-to>` element specifies three required attributes (`ref`, `type` and `href`) while also allowing for the presence of additional extension attributes and extension elements.</span></span>  
  
## <a name="modeling-the-in-reply-to-element"></a><span data-ttu-id="88f32-112">Modelar el elemento In-Reply-To</span><span class="sxs-lookup"><span data-stu-id="88f32-112">Modeling the In-Reply-To element</span></span>  
 <span data-ttu-id="88f32-113">En este ejemplo, el elemento `<in-reply-to>` se modela como CLR que implementa <xref:System.Xml.Serialization.IXmlSerializable>, lo que habilita su uso con <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="88f32-113">In this sample, the `<in-reply-to>` element is modeled as CLR that implements <xref:System.Xml.Serialization.IXmlSerializable>, which enables its use with the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="88f32-114">También implementa algunos métodos y propiedades para tener acceso a los datos del elemento, tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="88f32-114">It also implements some methods and properties for accessing the element's data, as shown in the following sample code.</span></span>  
  
```csharp  
[XmlRoot(ElementName = "in-reply-to", Namespace = "http://contoso.org/syndication/thread/1.0")]  
public class InReplyToElement : IXmlSerializable  
{  
    internal const string ElementName = "in-reply-to";  
    internal const string NsUri =
                  "http://contoso.org/syndication/thread/1.0";  
    private Dictionary<XmlQualifiedName, string> extensionAttributes;  
    private Collection<XElement> extensionElements;  
  
    public InReplyToElement()  
    {  
        this.extensionElements = new Collection<XElement>();  
        this.extensionAttributes = new Dictionary<XmlQualifiedName,
                                                          string>();  
    }  
  
    public Dictionary<XmlQualifiedName, string> AttributeExtensions  
    {  
        get { return this.extensionAttributes; }  
    }  
  
    public Collection<XElement> ElementExtensions  
    {  
        get { return this.extensionElements; }  
    }  
  
    public Uri Href  
    { get; set; }  
  
    public string MediaType  
    { get; set; }  
  
    public string Ref  
    { get; set; }  
  
    public Uri Source  
    { get; set; }  
}  
```  
  
 <span data-ttu-id="88f32-115">La clase `InReplyToElement` implementa las propiedades para el atributo necesario (`HRef`, `MediaType` y `Source`) así como las colecciones para contener <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> y <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="88f32-115">The `InReplyToElement` class implements properties for the required attribute (`HRef`, `MediaType`, and `Source`) as well as collections to hold <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span></span>  
  
 <span data-ttu-id="88f32-116">La clase `InReplyToElement` implementa la interfaz <xref:System.Xml.Serialization.IXmlSerializable>, que permite el control directo sobre cómo se leen y se escriben las instancias del objeto en XML.</span><span class="sxs-lookup"><span data-stu-id="88f32-116">The `InReplyToElement` class implements the <xref:System.Xml.Serialization.IXmlSerializable> interface, which allows direct control over how object instances are read from and written to XML.</span></span> <span data-ttu-id="88f32-117">El método `ReadXml` lee primero los valores para las propiedades `Ref`, `HRef`, `Source` y `MediaType` de <xref:System.Xml.XmlReader> pasado a él.</span><span class="sxs-lookup"><span data-stu-id="88f32-117">The `ReadXml` method first reads the values for the `Ref`, `HRef`, `Source`, and `MediaType` properties from the <xref:System.Xml.XmlReader> passed to it.</span></span> <span data-ttu-id="88f32-118">Cualquier atributo desconocido se almacena en la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="88f32-118">Any unknown attributes are stored in the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection.</span></span> <span data-ttu-id="88f32-119">Cuando se hayan leído todos los atributos, se llama a <xref:System.Xml.XmlReader.ReadStartElement> para avanzar el lector al elemento siguiente.</span><span class="sxs-lookup"><span data-stu-id="88f32-119">When all the attributes have been read, <xref:System.Xml.XmlReader.ReadStartElement> is called to advance the reader to the next element.</span></span> <span data-ttu-id="88f32-120">Dado que el elemento modelado por esta clase no tiene ningún elemento secundario necesario, los elementos secundarios se almacenan en búfer en las instancias `XElement` y se almacenan en la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>, como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="88f32-120">Because the element modeled by this class has no required children, the child elements get buffered into `XElement` instances and stored in the <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> collection, as shown in the following code.</span></span>  
  
```csharp
public void ReadXml(System.Xml.XmlReader reader)  
{  
    bool isEmpty = reader.IsEmptyElement;  
  
    if (reader.HasAttributes)  
    {  
        for (int i = 0; i < reader.AttributeCount; i++)  
        {  
            reader.MoveToNextAttribute();  
  
            if (reader.NamespaceURI == "")  
            {  
                if (reader.LocalName == "ref")  
                {  
                    this.Ref = reader.Value;  
                }  
                else if (reader.LocalName == "href")  
                {  
                    this.Href = new Uri(reader.Value);  
                }  
                else if (reader.LocalName == "source")  
                {  
                    this.Source = new Uri(reader.Value);  
                }  
                else if (reader.LocalName == "type")  
                {  
                    this.MediaType = reader.Value;  
                }  
                else  
                {  
                    this.AttributeExtensions.Add(new
                                 XmlQualifiedName(reader.LocalName,
                                 reader.NamespaceURI),
                                 reader.Value);  
                }  
            }  
        }  
    }  
  
    reader.ReadStartElement();  
  
    if (!isEmpty)  
    {  
        while (reader.IsStartElement())  
        {  
            ElementExtensions.Add(  
                  (XElement) XElement.ReadFrom(reader));  
        }  
        reader.ReadEndElement();  
    }  
}  
```  
  
 <span data-ttu-id="88f32-121">En `WriteXml`, el método `InReplyToElement` escribe primero los valores de las propiedades `Ref`, `HRef`, `Source` y `MediaType` como atributos XML (`WriteXml` no es responsable de escribir el elemento externo propiamente dicho, como lo ha hecho el autor de la llamada de `WriteXml`).</span><span class="sxs-lookup"><span data-stu-id="88f32-121">In `WriteXml`, the `InReplyToElement` method first writes out the values of the `Ref`, `HRef`, `Source`, and `MediaType` properties as XML attributes (`WriteXml` is not responsible for writing the actual outer element itself, as that done by the caller of `WriteXml`).</span></span> <span data-ttu-id="88f32-122">También escribe el contenido de <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> y <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> en el sistema de escritura, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="88f32-122">It also writes the contents of the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> to the writer, as shown in the following code.</span></span>  
  
```csharp
public void WriteXml(System.Xml.XmlWriter writer)  
{  
    if (this.Ref != null)  
    {  
        writer.WriteAttributeString("ref", InReplyToElement.NsUri,
                                            this.Ref);  
    }  
    if (this.Href != null)  
    {  
        writer.WriteAttributeString("href", InReplyToElement.NsUri,
                                                this.Href.ToString());  
    }  
    if (this.Source != null)  
    {  
        writer.WriteAttributeString("source", InReplyToElement.NsUri,
                                              this.Source.ToString());  
    }  
    if (this.MediaType != null)  
    {  
        writer.WriteAttributeString("type", InReplyToElement.NsUri,
                                                    this.MediaType);  
    }  
  
    foreach (KeyValuePair<XmlQualifiedName, string> kvp in
                                             this.AttributeExtensions)  
    {  
        writer.WriteAttributeString(kvp.Key.Name, kvp.Key.Namespace,
                                                   kvp.Value);  
    }  
  
    foreach (XElement element in this.ElementExtensions)  
    {  
        element.WriteTo(writer);  
    }  
}  
```  
  
## <a name="threadedfeed-and-threadeditem"></a><span data-ttu-id="88f32-123">ThreadedFeed y ThreadedItem</span><span class="sxs-lookup"><span data-stu-id="88f32-123">ThreadedFeed and ThreadedItem</span></span>  
 <span data-ttu-id="88f32-124">En el ejemplo, la clase `SyndicationItems` modela `InReplyTo` con extensiones `ThreadedItem`.</span><span class="sxs-lookup"><span data-stu-id="88f32-124">In the sample, `SyndicationItems` with `InReplyTo` extensions are modeled by the `ThreadedItem` class.</span></span> <span data-ttu-id="88f32-125">De igual manera, la clase `ThreadedFeed` es `SyndicationFeed` cuyos elementos son todos instancias de `ThreadedItem`.</span><span class="sxs-lookup"><span data-stu-id="88f32-125">Similarly, the `ThreadedFeed` class is a `SyndicationFeed` whose items are all instances of `ThreadedItem`.</span></span>  
  
 <span data-ttu-id="88f32-126">La clase `ThreadedFeed` hereda de `SyndicationFeed` e invalida `OnCreateItem` para devolver un `ThreadedItem`.</span><span class="sxs-lookup"><span data-stu-id="88f32-126">The `ThreadedFeed` class inherits from `SyndicationFeed` and overrides `OnCreateItem` to return a `ThreadedItem`.</span></span> <span data-ttu-id="88f32-127">También implementa un método para tener acceso a la colección `Items` como `ThreadedItems`, como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="88f32-127">It also implements a method for accessing the `Items` collection as `ThreadedItems`, as shown in the following code.</span></span>  
  
```csharp
public class ThreadedFeed : SyndicationFeed  
{  
    public ThreadedFeed()  
    {  
    }  
  
    public IEnumerable<ThreadedItem> ThreadedItems  
    {  
        get  
        {  
            return this.Items.Cast<ThreadedItem>();  
        }  
    }  
  
    protected override SyndicationItem CreateItem()  
    {  
        return new ThreadedItem();  
    }  
}  
```  
  
 <span data-ttu-id="88f32-128">La clase `ThreadedItem` hereda de `SyndicationItem` y realiza `InReplyToElement` una propiedad fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="88f32-128">The class `ThreadedItem` inherits from `SyndicationItem` and makes `InReplyToElement` as a strongly typed property.</span></span> <span data-ttu-id="88f32-129">Esto proporciona acceso adecuado mediante programación a los datos de extensión `InReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="88f32-129">This provides for convenient programmatic access to the `InReplyTo` extension data.</span></span> <span data-ttu-id="88f32-130">También implementa `TryParseElement` y `WriteElementExtensions` para leer y escribir sus datos de la extensión, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="88f32-130">It also implements `TryParseElement` and `WriteElementExtensions` for reading and writing its extension data, as shown in the following code.</span></span>  
  
```csharp
public class ThreadedItem : SyndicationItem  
{  
    private InReplyToElement inReplyTo;  
    // Constructors  
        public ThreadedItem()  
        {  
            inReplyTo = new InReplyToElement();  
        }  
  
        public ThreadedItem(string title, string content, Uri itemAlternateLink, string id, DateTimeOffset lastUpdatedTime) : base(title, content, itemAlternateLink, id, lastUpdatedTime)  
        {  
            inReplyTo = new InReplyToElement();  
        }  
  
    public InReplyToElement InReplyTo  
    {  
        get { return this.inReplyTo; }  
    }  
  
    protected override bool TryParseElement(  
                        System.Xml.XmlReader reader,
                        string version)  
    {  
        if (version == SyndicationVersions.Atom10 &&  
            reader.NamespaceURI == InReplyToElement.NsUri &&  
            reader.LocalName == InReplyToElement.ElementName)  
        {  
            this.inReplyTo = new InReplyToElement();  
  
            this.InReplyTo.ReadXml(reader);  
  
            return true;  
        }  
        else  
        {  
            return base.TryParseElement(reader, version);  
        }  
    }  
  
    protected override void WriteElementExtensions(XmlWriter writer,
                                                 string version)  
    {  
        if (this.InReplyTo != null &&
                     version == SyndicationVersions.Atom10)  
        {  
            writer.WriteStartElement(InReplyToElement.ElementName,
                                           InReplyToElement.NsUri);  
            this.InReplyTo.WriteXml(writer);  
            writer.WriteEndElement();  
        }  
  
        base.WriteElementExtensions(writer, version);  
    }  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="88f32-131">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="88f32-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="88f32-132">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="88f32-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="88f32-133">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="88f32-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="88f32-134">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="88f32-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="88f32-135">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="88f32-135">The samples may already be installed on your computer.</span></span> <span data-ttu-id="88f32-136">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="88f32-136">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="88f32-137">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="88f32-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="88f32-138">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="88f32-138">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StronglyTypedExtensions`  
