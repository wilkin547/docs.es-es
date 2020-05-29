---
title: Ejemplo de extensiones fuertemente tipadas
ms.date: 03/30/2017
ms.assetid: 02220f11-1a83-441c-9e5a-85f9a9367572
ms.openlocfilehash: 65f14b2c8db7553cb2f14bc7a1fe6f7128f523b6
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201549"
---
# <a name="strongly-typed-extensions-sample"></a>Ejemplo de extensiones fuertemente tipadas

El ejemplo utiliza la clase <xref:System.ServiceModel.Syndication.SyndicationFeed> para el ejemplo. Sin embargo, los modelos mostrados en este ejemplo se pueden utilizar con todas las clases de sindicación que admiten los datos de la extensión:  
  
 El modelo de objetos de distribución (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem> y las clases relacionadas) admite el acceso fuertemente tipado en datos de extensión utilizando las propiedades <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> y <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>. En este ejemplo se muestra cómo proporcionar acceso fuertemente tipado a los datos de extensión mediante la implementación de clases derivadas personalizadas de <xref:System.ServiceModel.Syndication.SyndicationFeed> y <xref:System.ServiceModel.Syndication.SyndicationItem> que hacen que estén disponibles ciertas extensiones específicas de la aplicación como propiedades fuertemente tipadas.  
  
 Como ejemplo, este ejemplo muestra cómo implementar un elemento de extensión definido en el RFC de las extensiones de subprocesamiento de Atom propuesto. Esto solo es para fines ilustrativos y este ejemplo no está diseñado para que sea una implementación completa de la especificación propuesta.  
  
## <a name="sample-xml"></a>XML de ejemplo  
 El siguiente ejemplo de XML muestra una entrada de Atom 1.0 con un elemento de extensión `<in-reply-to>` adicional.  
  
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
  
 El `<in-reply-to>` elemento especifica tres atributos obligatorios ( `ref` , `type` y), a `href` la vez que también permite la presencia de atributos de extensión y elementos de extensión adicionales.  
  
## <a name="modeling-the-in-reply-to-element"></a>Modelar el elemento In-Reply-To  
 En este ejemplo, el elemento `<in-reply-to>` se modela como CLR que implementa <xref:System.Xml.Serialization.IXmlSerializable>, lo que habilita su uso con <xref:System.Runtime.Serialization.DataContractSerializer>. También implementa algunos métodos y propiedades para tener acceso a los datos del elemento, tal y como se muestra en el código de ejemplo siguiente.  
  
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
  
 La clase `InReplyToElement` implementa las propiedades para el atributo necesario (`HRef`, `MediaType` y `Source`) así como las colecciones para contener <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> y <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.  
  
 La clase `InReplyToElement` implementa la interfaz <xref:System.Xml.Serialization.IXmlSerializable>, que permite el control directo sobre cómo se leen y se escriben las instancias del objeto en XML. El método `ReadXml` lee primero los valores para las propiedades `Ref`, `HRef`, `Source` y `MediaType` de <xref:System.Xml.XmlReader> pasado a él. Cualquier atributo desconocido se almacena en la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>. Cuando se hayan leído todos los atributos, se llama a <xref:System.Xml.XmlReader.ReadStartElement> para avanzar el lector al elemento siguiente. Dado que el elemento modelado por esta clase no tiene ningún elemento secundario necesario, los elementos secundarios se almacenan en búfer en las instancias `XElement` y se almacenan en la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>, como se muestra en el siguiente código.  
  
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
  
 En `WriteXml`, el método `InReplyToElement` escribe primero los valores de las propiedades `Ref`, `HRef`, `Source` y `MediaType` como atributos XML (`WriteXml` no es responsable de escribir el elemento externo propiamente dicho, como lo ha hecho el autor de la llamada de `WriteXml`). También escribe el contenido de <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> y <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> en el sistema de escritura, como se muestra en el código siguiente.  
  
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
  
## <a name="threadedfeed-and-threadeditem"></a>ThreadedFeed y ThreadedItem  
 En el ejemplo, la clase `SyndicationItems` modela `InReplyTo` con extensiones `ThreadedItem`. De igual manera, la clase `ThreadedFeed` es `SyndicationFeed` cuyos elementos son todos instancias de `ThreadedItem`.  
  
 La clase `ThreadedFeed` hereda de `SyndicationFeed` e invalida `OnCreateItem` para devolver un `ThreadedItem`. También implementa un método para tener acceso a la colección `Items` como `ThreadedItems`, como se muestra en el siguiente código.  
  
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
  
 La clase `ThreadedItem` hereda de `SyndicationItem` y realiza `InReplyToElement` una propiedad fuertemente tipada. Esto proporciona acceso adecuado mediante programación a los datos de extensión `InReplyTo`. También implementa `TryParseElement` y `WriteElementExtensions` para leer y escribir sus datos de la extensión, como se muestra en el código siguiente.  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StronglyTypedExtensions`  
