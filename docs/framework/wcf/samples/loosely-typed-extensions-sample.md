---
description: 'Más información acerca de: ejemplo de Loosely-Typed Extensions'
title: Ejemplo de extensiones débilmente tipadas
ms.date: 03/30/2017
ms.assetid: 56ce265b-8163-4b85-98e7-7692a12c4357
ms.openlocfilehash: cd430a922a35baf0ed9ce387b7df81fa3af6b35d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793238"
---
# <a name="loosely-typed-extensions-sample"></a>Ejemplo de extensiones débilmente tipadas

El modelo de objetos de sindicación proporciona compatibilidad enriquecida para trabajar con datos de extensión (información que está presente en una representación XML de una fuente de sindicación pero no explícitamente expuesta por clases como <xref:System.ServiceModel.Syndication.SyndicationFeed> y <xref:System.ServiceModel.Syndication.SyndicationItem>. Este ejemplo muestra las técnicas básicas para trabajar con datos de extensión.  
  
 El ejemplo utiliza la clase <xref:System.ServiceModel.Syndication.SyndicationFeed> para el ejemplo. Sin embargo, los modelos mostrados en este ejemplo se pueden utilizar con todas las clases de sindicación que admiten datos de extensión:  
  
 <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
 <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
 <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
 <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
## <a name="sample-xml"></a>XML de ejemplo  

 Como referencia, el siguiente documento XML se usa en este ejemplo:  
  
```xml  
<?xml version="1.0" encoding="IBM437"?>  
<feed myAttribute="someValue" xmlns="http://www.w3.org/2005/Atom">  
  <title type="text"></title>  
  <id>uuid:8f60c7b3-a3c0-4de7-a642-2165d77ce3c1;id=1</id>  
  <updated>2007-09-07T22:15:34Z</updated>  
  <simpleString xmlns="">hello, world!</simpleString>  
  <simpleString xmlns="">another simple string</simpleString>  
  <DataContractExtension xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.d  
atacontract.org/2004/07/Microsoft.Syndication.Samples">  
    <Key>X</Key>  
    <Value>4</Value>  
  </DataContractExtension>  
  <XmlSerializerExtension xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://ww  
w.w3.org/2001/XMLSchema" xmlns="">  
    <Key>Y</Key>  
    <Value>8</Value>  
  </XmlSerializerExtension>  
  <xElementExtension xmlns="">  
    <Key attr1="someValue">Z</Key>  
    <Value attr1="someValue">15</Value>  
  </xElementExtension>  
</feed>  
```  
  
 Este documento contiene las siguientes partes de datos de extensión:  
  
- Atributo `myAttribute` del elemento `<feed>`.  
  
- Elemento `<simpleString>`.  
  
- Elemento `<DataContractExtension>`.  
  
- Elemento `<XmlSerializerExtension>`.  
  
- Elemento `<xElementExtension>`.  
  
## <a name="writing-extension-data"></a>Cómo escribir datos de extensión  

 Las extensiones de atributo se crean agregando entradas a la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> tal y como se muestra en el código de ejemplo siguiente.  
  
```csharp  
//Attribute extensions are stored in a dictionary indexed by
// XmlQualifiedName  
feed.AttributeExtensions.Add(new XmlQualifiedName("myAttribute", ""), "someValue");  
```  
  
 Las extensiones de elemento se crean agregando entradas a la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>. Estas extensiones pueden ser valores básicos como cadenas, serializaciones XML de objetos .NET Framework o nodos XML codificados a mano.  
  
 El código de ejemplo siguiente crea un elemento de extensión denominado `simpleString`.  
  
```csharp  
feed.ElementExtensions.Add("simpleString", "", "hello, world!");  
```  
  
 El espacio de nombres XML para este elemento es el espacio de nombres vacío ("") y su valor es un nodo de texto que contiene la cadena "Hello, World!".  
  
 Una manera de crear extensiones de elemento complejas que consten de muchos elementos anidados es utilizar las API de .NET Framework para la serialización (se admiten <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer>) tal como se muestra en los ejemplos siguientes.  
  
```csharp  
feed.ElementExtensions.Add( new DataContractExtension() { Key = "X", Value = 4 } );  
feed.ElementExtensions.Add( new XmlSerializerExtension { Key = "Y", Value = 8 }, new XmlSerializer( typeof( XmlSerializerExtension ) ) );  
```  
  
 En este ejemplo, `DataContractExtension` y `XmlSerializerExtension` son tipos personalizados escritos para su uso con un serializador.  
  
 La clase <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> también se puede utilizar para crear extensiones de elemento a partir de una instancia <xref:System.Xml.XmlReader>. Esto permite la fácil integración con las API de procesamiento de XML como <xref:System.Xml.Linq.XElement> tal y como se muestra en el código de ejemplo siguiente.  
  
```csharp  
feed.ElementExtensions.Add(new XElement("xElementExtension",  
        new XElement("Key", new XAttribute("attr1", "someValue"), "Z"),  
        new XElement("Value", new XAttribute("attr1", "someValue"),
        "15")).CreateReader());  
```  
  
## <a name="reading-extension-data"></a>Lectura de datos de la extensión  

 Los valores para las extensiones de atributo se pueden obtener buscando el atributo en la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> por su <xref:System.Xml.XmlQualifiedName> tal y como se muestra en el código de ejemplo siguiente.  
  
```csharp  
Console.WriteLine( feed.AttributeExtensions[ new XmlQualifiedName( "myAttribute", "" )]);  
```  
  
 Se tiene acceso a las extensiones de elemento utilizando el método `ReadElementExtensions<T>`.  
  
```csharp  
foreach( string s in feed2.ElementExtensions.ReadElementExtensions<string>("simpleString", ""))  
{  
    Console.WriteLine(s);  
}  
  
foreach (DataContractExtension dce in feed2.ElementExtensions.ReadElementExtensions<DataContractExtension>("DataContractExtension",  
"http://schemas.datacontract.org/2004/07/SyndicationExtensions"))  
{  
    Console.WriteLine(dce.ToString());  
}  
  
foreach (XmlSerializerExtension xse in feed2.ElementExtensions.ReadElementExtensions<XmlSerializerExtension>("XmlSerializerExtension", "", new XmlSerializer(typeof(XmlSerializerExtension))))  
{  
    Console.WriteLine(xse.ToString());  
}  
```  
  
 También es posible obtener un `XmlReader` en las extensiones de elemento individuales utilizando el método <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader>.  
  
```csharp  
foreach (SyndicationElementExtension extension in feed2.ElementExtensions.Where<SyndicationElementExtension>(x => x.OuterName == "xElementExtension"))  
{  
    XNode xelement = XElement.ReadFrom(extension.GetReader());  
    Console.WriteLine(xelement.ToString());  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\LooselyTypedExtensions`  
  
## <a name="see-also"></a>Vea también

- [Extensiones fuertemente tipadas](strongly-typed-extensions-sample.md)
- [Sindicación en WCF](../feature-details/wcf-syndication.md)
