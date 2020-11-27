---
title: Ejemplo de extensiones débilmente tipadas
ms.date: 03/30/2017
ms.assetid: 56ce265b-8163-4b85-98e7-7692a12c4357
ms.openlocfilehash: 94e01970502223febd3ff03e30be7b17d9019d93
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264900"
---
# <a name="loosely-typed-extensions-sample"></a><span data-ttu-id="ee462-102">Ejemplo de extensiones débilmente tipadas</span><span class="sxs-lookup"><span data-stu-id="ee462-102">Loosely-Typed Extensions Sample</span></span>

<span data-ttu-id="ee462-103">El modelo de objetos de sindicación proporciona compatibilidad enriquecida para trabajar con datos de extensión (información que está presente en una representación XML de una fuente de sindicación pero no explícitamente expuesta por clases como <xref:System.ServiceModel.Syndication.SyndicationFeed> y <xref:System.ServiceModel.Syndication.SyndicationItem>.</span><span class="sxs-lookup"><span data-stu-id="ee462-103">The Syndication object model provides rich support for working with extension data—information that is present in a syndication feed's XML representation but not explicitly exposed by classes such as <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem>.</span></span> <span data-ttu-id="ee462-104">Este ejemplo muestra las técnicas básicas para trabajar con datos de extensión.</span><span class="sxs-lookup"><span data-stu-id="ee462-104">This sample illustrates the basic techniques for working with extension data.</span></span>  
  
 <span data-ttu-id="ee462-105">El ejemplo utiliza la clase <xref:System.ServiceModel.Syndication.SyndicationFeed> para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ee462-105">The sample uses the <xref:System.ServiceModel.Syndication.SyndicationFeed> class for the purposes of the example.</span></span> <span data-ttu-id="ee462-106">Sin embargo, los modelos mostrados en este ejemplo se pueden utilizar con todas las clases de sindicación que admiten datos de extensión:</span><span class="sxs-lookup"><span data-stu-id="ee462-106">However, the patterns demonstrated in this sample can be used with all of the Syndication classes that support extension data:</span></span>  
  
 <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
 <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
 <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
 <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
## <a name="sample-xml"></a><span data-ttu-id="ee462-107">XML de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee462-107">Sample XML</span></span>  

 <span data-ttu-id="ee462-108">Como referencia, el siguiente documento XML se usa en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ee462-108">For reference, the following XML document is used in this sample.</span></span>  
  
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
  
 <span data-ttu-id="ee462-109">Este documento contiene las siguientes partes de datos de extensión:</span><span class="sxs-lookup"><span data-stu-id="ee462-109">This document contains the following pieces of extension data:</span></span>  
  
- <span data-ttu-id="ee462-110">Atributo `myAttribute` del elemento `<feed>`.</span><span class="sxs-lookup"><span data-stu-id="ee462-110">The `myAttribute` attribute of the `<feed>` element.</span></span>  
  
- <span data-ttu-id="ee462-111">Elemento `<simpleString>`.</span><span class="sxs-lookup"><span data-stu-id="ee462-111">`<simpleString>` element.</span></span>  
  
- <span data-ttu-id="ee462-112">Elemento `<DataContractExtension>`.</span><span class="sxs-lookup"><span data-stu-id="ee462-112">`<DataContractExtension>` element.</span></span>  
  
- <span data-ttu-id="ee462-113">Elemento `<XmlSerializerExtension>`.</span><span class="sxs-lookup"><span data-stu-id="ee462-113">`<XmlSerializerExtension>` element.</span></span>  
  
- <span data-ttu-id="ee462-114">Elemento `<xElementExtension>`.</span><span class="sxs-lookup"><span data-stu-id="ee462-114">`<xElementExtension>` element.</span></span>  
  
## <a name="writing-extension-data"></a><span data-ttu-id="ee462-115">Cómo escribir datos de extensión</span><span class="sxs-lookup"><span data-stu-id="ee462-115">Writing Extension Data</span></span>  

 <span data-ttu-id="ee462-116">Las extensiones de atributo se crean agregando entradas a la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ee462-116">Attribute extensions are created by adding entries to the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection as shown in the following sample code.</span></span>  
  
```csharp  
//Attribute extensions are stored in a dictionary indexed by
// XmlQualifiedName  
feed.AttributeExtensions.Add(new XmlQualifiedName("myAttribute", ""), "someValue");  
```  
  
 <span data-ttu-id="ee462-117">Las extensiones de elemento se crean agregando entradas a la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee462-117">Element extensions are created by adding entries to the <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> collection.</span></span> <span data-ttu-id="ee462-118">Estas extensiones pueden ser valores básicos como cadenas, serializaciones XML de objetos .NET Framework o nodos XML codificados a mano.</span><span class="sxs-lookup"><span data-stu-id="ee462-118">These extensions can by basic values such as strings, XML serializations of .NET Framework objects, or XML nodes coded by hand.</span></span>  
  
 <span data-ttu-id="ee462-119">El código de ejemplo siguiente crea un elemento de extensión denominado `simpleString`.</span><span class="sxs-lookup"><span data-stu-id="ee462-119">The following sample code creates an extension element named `simpleString`.</span></span>  
  
```csharp  
feed.ElementExtensions.Add("simpleString", "", "hello, world!");  
```  
  
 <span data-ttu-id="ee462-120">El espacio de nombres XML para este elemento es el espacio de nombres vacío ("") y su valor es un nodo de texto que contiene la cadena "Hello, World!".</span><span class="sxs-lookup"><span data-stu-id="ee462-120">The XML namespace for this element is the empty namespace ("") and its value is a text node that contains the string "hello, world!".</span></span>  
  
 <span data-ttu-id="ee462-121">Una manera de crear extensiones de elemento complejas que consten de muchos elementos anidados es utilizar las API de .NET Framework para la serialización (se admiten <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer>) tal como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="ee462-121">One way to create complex element extensions that consist of many nested elements is to use the .NET Framework APIs for serialization (both the <xref:System.Runtime.Serialization.DataContractSerializer> and the <xref:System.Xml.Serialization.XmlSerializer> are supported) as shown in the following examples.</span></span>  
  
```csharp  
feed.ElementExtensions.Add( new DataContractExtension() { Key = "X", Value = 4 } );  
feed.ElementExtensions.Add( new XmlSerializerExtension { Key = "Y", Value = 8 }, new XmlSerializer( typeof( XmlSerializerExtension ) ) );  
```  
  
 <span data-ttu-id="ee462-122">En este ejemplo, `DataContractExtension` y `XmlSerializerExtension` son tipos personalizados escritos para su uso con un serializador.</span><span class="sxs-lookup"><span data-stu-id="ee462-122">In this example, the `DataContractExtension` and `XmlSerializerExtension` are custom types written for use with a serializer.</span></span>  
  
 <span data-ttu-id="ee462-123">La clase <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> también se puede utilizar para crear extensiones de elemento a partir de una instancia <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="ee462-123">The <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> class can also be used to create element extensions from an <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="ee462-124">Esto permite la fácil integración con las API de procesamiento de XML como <xref:System.Xml.Linq.XElement> tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ee462-124">This allows for easy integration with XML processing APIs such as <xref:System.Xml.Linq.XElement> as shown in the following sample code.</span></span>  
  
```csharp  
feed.ElementExtensions.Add(new XElement("xElementExtension",  
        new XElement("Key", new XAttribute("attr1", "someValue"), "Z"),  
        new XElement("Value", new XAttribute("attr1", "someValue"),
        "15")).CreateReader());  
```  
  
## <a name="reading-extension-data"></a><span data-ttu-id="ee462-125">Lectura de datos de la extensión</span><span class="sxs-lookup"><span data-stu-id="ee462-125">Reading Extension Data</span></span>  

 <span data-ttu-id="ee462-126">Los valores para las extensiones de atributo se pueden obtener buscando el atributo en la colección <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> por su <xref:System.Xml.XmlQualifiedName> tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ee462-126">The values for attribute extensions can be obtained by looking up the attribute in the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection by its <xref:System.Xml.XmlQualifiedName> as shown in the following sample code.</span></span>  
  
```csharp  
Console.WriteLine( feed.AttributeExtensions[ new XmlQualifiedName( "myAttribute", "" )]);  
```  
  
 <span data-ttu-id="ee462-127">Se tiene acceso a las extensiones de elemento utilizando el método `ReadElementExtensions<T>`.</span><span class="sxs-lookup"><span data-stu-id="ee462-127">Element extensions are accessed using the `ReadElementExtensions<T>` method.</span></span>  
  
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
  
 <span data-ttu-id="ee462-128">También es posible obtener un `XmlReader` en las extensiones de elemento individuales utilizando el método <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader>.</span><span class="sxs-lookup"><span data-stu-id="ee462-128">It is also possible to obtain an `XmlReader` at individual element extensions by using the <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader> method.</span></span>  
  
```csharp  
foreach (SyndicationElementExtension extension in feed2.ElementExtensions.Where<SyndicationElementExtension>(x => x.OuterName == "xElementExtension"))  
{  
    XNode xelement = XElement.ReadFrom(extension.GetReader());  
    Console.WriteLine(xelement.ToString());  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ee462-129">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee462-129">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ee462-130">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ee462-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ee462-131">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ee462-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ee462-132">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ee462-132">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ee462-133">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ee462-133">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ee462-134">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ee462-134">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ee462-135">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ee462-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ee462-136">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ee462-136">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\LooselyTypedExtensions`  
  
## <a name="see-also"></a><span data-ttu-id="ee462-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee462-137">See also</span></span>

- [<span data-ttu-id="ee462-138">Extensiones fuertemente tipadas</span><span class="sxs-lookup"><span data-stu-id="ee462-138">Strongly typed Extensions</span></span>](strongly-typed-extensions-sample.md)
- [<span data-ttu-id="ee462-139">Sindicación en WCF</span><span class="sxs-lookup"><span data-stu-id="ee462-139">WCF Syndication</span></span>](../feature-details/wcf-syndication.md)
