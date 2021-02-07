---
description: 'Más información sobre: ejemplo de extensiones fuertemente tipadas'
title: Ejemplo de extensiones fuertemente tipadas
ms.date: 03/30/2017
ms.assetid: 02220f11-1a83-441c-9e5a-85f9a9367572
ms.openlocfilehash: dd0a12b07db3f805f041742c8957cd46bb418bad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668765"
---
# <a name="strongly-typed-extensions-sample"></a><span data-ttu-id="d458f-103">Ejemplo de extensiones fuertemente tipadas</span><span class="sxs-lookup"><span data-stu-id="d458f-103">Strongly typed extensions sample</span></span>

<span data-ttu-id="d458f-104">El ejemplo utiliza la clase <xref:System.ServiceModel.Syndication.SyndicationFeed> para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d458f-104">The sample uses the <xref:System.ServiceModel.Syndication.SyndicationFeed> class for the purposes of the example.</span></span> <span data-ttu-id="d458f-105">Sin embargo, los modelos mostrados en este ejemplo se pueden utilizar con todas las clases de sindicación que admiten los datos de la extensión:</span><span class="sxs-lookup"><span data-stu-id="d458f-105">However, the patterns demonstrated in this sample can be used with all of the Syndication classes that support extension data.</span></span>  
  
 <span data-ttu-id="d458f-106">El modelo de objetos de distribución (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem> y las clases relacionadas) admite el acceso fuertemente tipado en datos de extensión utilizando las propiedades <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> y <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="d458f-106">The Syndication object model (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, and related classes) supports loosely-typed access to extension data by using the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> properties.</span></span> <span data-ttu-id="d458f-107">En este ejemplo se muestra cómo proporcionar acceso fuertemente tipado a los datos de extensión mediante la implementación de clases derivadas personalizadas de <xref:System.ServiceModel.Syndication.SyndicationFeed> y <xref:System.ServiceModel.Syndication.SyndicationItem> que hacen que estén disponibles ciertas extensiones específicas de la aplicación como propiedades fuertemente tipadas.</span><span class="sxs-lookup"><span data-stu-id="d458f-107">This sample shows how to provide strongly typed access to extension data by implementing custom derived classes of <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> that make available certain application-specific extensions as strongly typed properties.</span></span>  
  
 <span data-ttu-id="d458f-108">Como ejemplo, este ejemplo muestra cómo implementar un elemento de extensión definido en el RFC de las extensiones de subprocesamiento de Atom propuesto.</span><span class="sxs-lookup"><span data-stu-id="d458f-108">As an example, this sample shows how to implement an extension element defined in the proposed Atom Threading Extensions RFC.</span></span> <span data-ttu-id="d458f-109">Esto solo es para fines ilustrativos y este ejemplo no está diseñado para que sea una implementación completa de la especificación propuesta.</span><span class="sxs-lookup"><span data-stu-id="d458f-109">This is for demonstration purposes only and this sample is not intended to be a full implementation of the proposed specification.</span></span>  
  
## <a name="sample-xml"></a><span data-ttu-id="d458f-110">XML de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d458f-110">Sample XML</span></span>  

 <span data-ttu-id="d458f-111">El siguiente ejemplo de XML muestra una entrada de Atom 1.0 con un elemento de extensión `<in-reply-to>` adicional.</span><span class="sxs-lookup"><span data-stu-id="d458f-111">The following XML example shows an Atom 1.0 entry with an additional `<in-reply-to>` extension element.</span></span>  
  
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
  
 <span data-ttu-id="d458f-112">El `<in-reply-to>` elemento especifica tres atributos obligatorios ( `ref` , `type` y), a `href` la vez que también permite la presencia de atributos de extensión y elementos de extensión adicionales.</span><span class="sxs-lookup"><span data-stu-id="d458f-112">The `<in-reply-to>` element specifies three required attributes (`ref`, `type` and `href`) while also allowing for the presence of additional extension attributes and extension elements.</span></span>  
  
## <a name="modeling-the-in-reply-to-element"></a><span data-ttu-id="d458f-113">Modelar el elemento In-Reply-To</span><span class="sxs-lookup"><span data-stu-id="d458f-113">Modeling the In-Reply-To element</span></span>  

 <span data-ttu-id="d458f-114">En este ejemplo, el elemento `<in-reply-to>` se modela como CLR que implementa <xref:System.Xml.Serialization.IXmlSerializable>, lo que habilita su uso con <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d458f-114">In this sample, the `<in-reply-to>` element is modeled as CLR that implements <xref:System.Xml.Serialization.IXmlSerializable>, which enables its use with the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="d458f-115">También implementa algunos métodos y propiedades para tener acceso a los datos del elemento, tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d458f-115">It also implements some methods and properties for accessing the element's data, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="d458f-116">La clase `InReplyToElement` implementa las propiedades para el atributo necesario (`HRef`, `MediaType` y `Source`) así como las colecciones para contener <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> y <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="d458f-116">The `InReplyToElement` class implements properties for the required attribute (`HRef`, `MediaType`, and `Source`) as well as collections to hold <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span></span>  
  
 <span data-ttu-id="d458f-117">La clase `InReplyToElement` implementa la interfaz <xref:System.Xml.Serialization.IXmlSerializable>, que permite el control directo sobre cómo se leen y se escriben las instancias del objeto en XML.</span><span class="sxs-lookup"><span data-stu-id="d458f-117">The `InReplyToElement` class implements the <xref:System.Xml.Serialization.IXmlSerializable> interface, which allows direct control over how object instances are read from and written to XML.</span></span> <span data-ttu-id="d458f-118">El método `ReadXml` lee primero los valores para las propiedades `Ref`, `HRef`, `Source` y `MediaType` de <xref:System.Xml.XmlReader> pasado a él.</span><span class="sxs-lookup"><span data-stu-id="d458f-118">The `ReadXml` method first reads the values for the `Ref`, `HRef`, `Source`, and `MediaType` properties from the <xref:System.Xml.XmlReader> passed to it.</span></span> <span data-ttu-id="d458f-119">Cualquier atributo desconocido se almacena en la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="d458f-119">Any unknown attributes are stored in the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection.</span></span> <span data-ttu-id="d458f-120">Cuando se hayan leído todos los atributos, se llama a <xref:System.Xml.XmlReader.ReadStartElement> para avanzar el lector al elemento siguiente.</span><span class="sxs-lookup"><span data-stu-id="d458f-120">When all the attributes have been read, <xref:System.Xml.XmlReader.ReadStartElement> is called to advance the reader to the next element.</span></span> <span data-ttu-id="d458f-121">Dado que el elemento modelado por esta clase no tiene ningún elemento secundario necesario, los elementos secundarios se almacenan en búfer en las instancias `XElement` y se almacenan en la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>, como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="d458f-121">Because the element modeled by this class has no required children, the child elements get buffered into `XElement` instances and stored in the <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> collection, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="d458f-122">En `WriteXml`, el método `InReplyToElement` escribe primero los valores de las propiedades `Ref`, `HRef`, `Source` y `MediaType` como atributos XML (`WriteXml` no es responsable de escribir el elemento externo propiamente dicho, como lo ha hecho el autor de la llamada de `WriteXml`).</span><span class="sxs-lookup"><span data-stu-id="d458f-122">In `WriteXml`, the `InReplyToElement` method first writes out the values of the `Ref`, `HRef`, `Source`, and `MediaType` properties as XML attributes (`WriteXml` is not responsible for writing the actual outer element itself, as that done by the caller of `WriteXml`).</span></span> <span data-ttu-id="d458f-123">También escribe el contenido de <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> y <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> en el sistema de escritura, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d458f-123">It also writes the contents of the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> to the writer, as shown in the following code.</span></span>  
  
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
  
## <a name="threadedfeed-and-threadeditem"></a><span data-ttu-id="d458f-124">ThreadedFeed y ThreadedItem</span><span class="sxs-lookup"><span data-stu-id="d458f-124">ThreadedFeed and ThreadedItem</span></span>  

 <span data-ttu-id="d458f-125">En el ejemplo, la clase `SyndicationItems` modela `InReplyTo` con extensiones `ThreadedItem`.</span><span class="sxs-lookup"><span data-stu-id="d458f-125">In the sample, `SyndicationItems` with `InReplyTo` extensions are modeled by the `ThreadedItem` class.</span></span> <span data-ttu-id="d458f-126">De igual manera, la clase `ThreadedFeed` es `SyndicationFeed` cuyos elementos son todos instancias de `ThreadedItem`.</span><span class="sxs-lookup"><span data-stu-id="d458f-126">Similarly, the `ThreadedFeed` class is a `SyndicationFeed` whose items are all instances of `ThreadedItem`.</span></span>  
  
 <span data-ttu-id="d458f-127">La clase `ThreadedFeed` hereda de `SyndicationFeed` e invalida `OnCreateItem` para devolver un `ThreadedItem`.</span><span class="sxs-lookup"><span data-stu-id="d458f-127">The `ThreadedFeed` class inherits from `SyndicationFeed` and overrides `OnCreateItem` to return a `ThreadedItem`.</span></span> <span data-ttu-id="d458f-128">También implementa un método para tener acceso a la colección `Items` como `ThreadedItems`, como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="d458f-128">It also implements a method for accessing the `Items` collection as `ThreadedItems`, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="d458f-129">La clase `ThreadedItem` hereda de `SyndicationItem` y realiza `InReplyToElement` una propiedad fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="d458f-129">The class `ThreadedItem` inherits from `SyndicationItem` and makes `InReplyToElement` as a strongly typed property.</span></span> <span data-ttu-id="d458f-130">Esto proporciona acceso adecuado mediante programación a los datos de extensión `InReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="d458f-130">This provides for convenient programmatic access to the `InReplyTo` extension data.</span></span> <span data-ttu-id="d458f-131">También implementa `TryParseElement` y `WriteElementExtensions` para leer y escribir sus datos de la extensión, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d458f-131">It also implements `TryParseElement` and `WriteElementExtensions` for reading and writing its extension data, as shown in the following code.</span></span>  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d458f-132">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="d458f-132">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d458f-133">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d458f-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="d458f-134">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d458f-134">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="d458f-135">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d458f-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d458f-136">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="d458f-136">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d458f-137">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d458f-137">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="d458f-138">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="d458f-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d458f-139">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="d458f-139">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StronglyTypedExtensions`  
