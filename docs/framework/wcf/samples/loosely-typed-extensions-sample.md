---
title: "Ejemplo de extensiones débilmente tipadas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56ce265b-8163-4b85-98e7-7692a12c4357
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8861138f7763f413f06983bbfba5f6e0ec3c8b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
  
-   Atributo `myAttribute` del elemento `<feed>`.  
  
-   Elemento `<simpleString>`.  
  
-   Elemento `<DataContractExtension>`.  
  
-   Elemento `<XmlSerializerExtension>`.  
  
-   Elemento `<xElementExtension>`.  
  
## <a name="writing-extension-data"></a>Cómo escribir datos de extensión  
 Las extensiones de atributo se crean agregando entradas a la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> tal y como se muestra en el código de ejemplo siguiente.  
  
```  
//Attribute extensions are stored in a dictionary indexed by   
// XmlQualifiedName  
feed.AttributeExtensions.Add(new XmlQualifiedName("myAttribute", ""), "someValue");  
```  
  
 Las extensiones de elemento se crean agregando entradas a la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>. Estas extensiones pueden ser valores básicos como cadenas, serializaciones XML de objetos .NET Framework o nodos XML codificados a mano.  
  
 El código de ejemplo siguiente crea un elemento de extensión denominado `simpleString`.  
  
```  
feed.ElementExtensions.Add("simpleString", "", "hello, world!");  
```  
  
 El espacio de nombres XML para este elemento es el espacio de nombres vacío ("") y su valor es un nodo de texto que contiene la cadena "hello, world!".  
  
 Una manera de crear extensiones de elemento complejas que consten de muchos elementos anidados es utilizar las API de .NET Framework para la serialización (se admiten <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer>) tal como se muestra en los ejemplos siguientes.  
  
```  
feed.ElementExtensions.Add( new DataContractExtension() { Key = "X", Value = 4 } );  
feed.ElementExtensions.Add( new XmlSerializerExtension { Key = "Y", Value = 8 }, new XmlSerializer( typeof( XmlSerializerExtension ) ) );  
```  
  
 En este ejemplo, `DataContractExtension` y `XmlSerializerExtension` son tipos personalizados escritos para su uso con un serializador.  
  
 La clase <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> también se puede utilizar para crear extensiones de elemento a partir de una instancia <xref:System.Xml.XmlReader>. Esto permite la fácil integración con las API de procesamiento de XML como <xref:System.Xml.Linq.XElement> tal y como se muestra en el código de ejemplo siguiente.  
  
```  
feed.ElementExtensions.Add(new XElement("xElementExtension",  
        new XElement("Key", new XAttribute("attr1", "someValue"), "Z"),  
        new XElement("Value", new XAttribute("attr1", "someValue"),   
        "15")).CreateReader());  
```  
  
## <a name="reading-extension-data"></a>Lectura de datos de la extensión  
 Los valores para las extensiones de atributo se pueden obtener buscando el atributo en la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> por su <xref:System.Xml.XmlQualifiedName> tal y como se muestra en el código de ejemplo siguiente.  
  
```  
Console.WriteLine( feed.AttributeExtensions[ new XmlQualifiedName( "myAttribute", "" )]);  
```  
  
 Se tiene acceso a las extensiones de elemento utilizando el método `ReadElementExtensions<T>`.  
  
```  
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
  
```  
foreach (SyndicationElementExtension extension in feed2.ElementExtensions.Where<SyndicationElementExtension>(x => x.OuterName == "xElementExtension"))  
{  
    XNode xelement = XElement.ReadFrom(extension.GetReader());  
    Console.WriteLine(xelement.ToString());  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\LooselyTypedExtensions`  
  
## <a name="see-also"></a>Vea también  
 [Extensiones fuertemente tipadas](../../../../docs/framework/wcf/samples/strongly-typed-extensions-sample.md)  
 [Redifusión en WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
