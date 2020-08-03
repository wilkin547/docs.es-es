---
title: Procedimiento para realizar una transformación de streaming de documentos XML grandes (C#)
description: Aprenda a realizar una transformación de streaming de texto a XML en C# para evitar el uso excesivo de memoria en algunos archivos.
ms.date: 07/20/2015
ms.assetid: 5f16d1f8-5370-4b55-b0c8-e497df163037
ms.openlocfilehash: e1ab2866079b2244dc764271d7ba63173349e2f3
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104868"
---
# <a name="how-to-perform-streaming-transform-of-large-xml-documents-c"></a><span data-ttu-id="43b26-103">Procedimiento para realizar una transformación de streaming de documentos XML grandes (C#)</span><span class="sxs-lookup"><span data-stu-id="43b26-103">How to perform streaming transform of large XML documents (C#)</span></span>
<span data-ttu-id="43b26-104">A veces tiene que transformar los archivos XML grandes y escribir la aplicación para que sea predecible la superficie en memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="43b26-104">Sometimes you have to transform large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="43b26-105">Si intenta rellenar un árbol XML con un archivo XML de gran tamaño, su utilización de memoria será proporcional al tamaño del archivo (es decir, excesivo).</span><span class="sxs-lookup"><span data-stu-id="43b26-105">If you try to populate an XML tree with a very large XML file, your memory usage will be proportional to the size of the file (that is, excessive).</span></span> <span data-ttu-id="43b26-106">Por consiguiente, debe utilizar en su lugar una técnica de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="43b26-106">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="43b26-107">Las técnicas de transmisión por secuencias se aplican mejor en situaciones en las que el documento de origen solo se debe procesar una vez y se pueden procesar los elementos en el orden del documento.</span><span class="sxs-lookup"><span data-stu-id="43b26-107">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="43b26-108">Ciertos operadores de consulta estándar, como <xref:System.Linq.Enumerable.OrderBy%2A>, recorren en iteración su origen, recaban todos los datos, los ordenan y finalmente producen el primer elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="43b26-108">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="43b26-109">Tenga en cuenta que si utiliza un operador de consulta que materializa su origen antes de producir el primer elemento, no retendrá una superficie de memoria pequeña para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="43b26-109">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint for your application.</span></span>  
  
<span data-ttu-id="43b26-110">Incluso si se usa la técnica descrita en [Procedimiento para hacer streaming de fragmentos XML con acceso a la información del encabezado (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md), si se intenta ensamblar un árbol XML que contiene el documento transformado, el uso de memoria será excesivo.</span><span class="sxs-lookup"><span data-stu-id="43b26-110">Even if you use the technique described in [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md), if you try to assemble an XML tree that contains the transformed document, memory usage will be too great.</span></span>
  
 <span data-ttu-id="43b26-111">Hay dos grandes enfoques.</span><span class="sxs-lookup"><span data-stu-id="43b26-111">There are two main approaches.</span></span> <span data-ttu-id="43b26-112">Un enfoque consiste en utilizar las características de procesamiento aplazada de <xref:System.Xml.Linq.XStreamingElement>.</span><span class="sxs-lookup"><span data-stu-id="43b26-112">One approach is to use the deferred processing characteristics of <xref:System.Xml.Linq.XStreamingElement>.</span></span> <span data-ttu-id="43b26-113">El otro enfoque consiste en crear un <xref:System.Xml.XmlWriter> y utilizar las capacidades de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para escribir elementos en un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="43b26-113">Another approach is to create an <xref:System.Xml.XmlWriter>, and use the capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="43b26-114">En este tema se muestran ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="43b26-114">This topic demonstrates both approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43b26-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43b26-115">Example</span></span>  
 <span data-ttu-id="43b26-116">El ejemplo siguiente se basa en el ejemplo de [Procedimiento para hacer streaming de fragmentos XML con acceso a la información del encabezado (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md).</span><span class="sxs-lookup"><span data-stu-id="43b26-116">The following example builds on the example in [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>
  
 <span data-ttu-id="43b26-117">Este ejemplo utiliza las funciones de ejecución aplazada de <xref:System.Xml.Linq.XStreamingElement> para transmitir por secuencias el resultado.</span><span class="sxs-lookup"><span data-stu-id="43b26-117">This example uses the deferred execution capabilities of <xref:System.Xml.Linq.XStreamingElement> to stream the output.</span></span> <span data-ttu-id="43b26-118">Este ejemplo puede transformar un documento muy grande a la vez que mantiene una pequeña superficie de memoria.</span><span class="sxs-lookup"><span data-stu-id="43b26-118">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="43b26-119">Observe que se escribe el eje personalizado (`StreamCustomerItem`) específicamente para que espere un documento que tiene los elementos `Customer`, `Name` e `Item`, y que esos elementos se organizarán como en el documento Source.xml siguiente.</span><span class="sxs-lookup"><span data-stu-id="43b26-119">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="43b26-120">No obstante, una implementación más sólida estaría preparada para analizar un documento no válido.</span><span class="sxs-lookup"><span data-stu-id="43b26-120">A more robust implementation, however, would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="43b26-121">A continuación, se muestra el documento de origen, Source.xml:</span><span class="sxs-lookup"><span data-stu-id="43b26-121">The following is the source document, Source.xml:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null)  
                        {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    XStreamingElement root = new XStreamingElement("Root",  
        from el in StreamCustomerItem("Source.xml")  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        )  
    );  
    root.Save("Test.xml");  
    Console.WriteLine(File.ReadAllText("Test.xml"));  
}  
```  
  
 <span data-ttu-id="43b26-122">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="43b26-122">This code produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="43b26-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43b26-123">Example</span></span>  
<span data-ttu-id="43b26-124">El ejemplo siguiente también se basa en el ejemplo de [Procedimiento para hacer streaming de fragmentos XML con acceso a la información del encabezado (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md).</span><span class="sxs-lookup"><span data-stu-id="43b26-124">The following example also builds on the example in [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>
  
 <span data-ttu-id="43b26-125">Este ejemplo utiliza la capacidad de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para escribir elementos en un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="43b26-125">This example uses the capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="43b26-126">Este ejemplo puede transformar un documento muy grande a la vez que mantiene una pequeña superficie de memoria.</span><span class="sxs-lookup"><span data-stu-id="43b26-126">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="43b26-127">Observe que se escribe el eje personalizado (`StreamCustomerItem`) específicamente para que espere un documento que tiene los elementos `Customer`, `Name` e `Item`, y que esos elementos se organizarán como en el documento Source.xml siguiente.</span><span class="sxs-lookup"><span data-stu-id="43b26-127">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="43b26-128">Una implementación más sólida, sin embargo, validaría el documento de origen con XSD o se prepararía para analizar un documento no válido.</span><span class="sxs-lookup"><span data-stu-id="43b26-128">A more robust implementation, however, would either validate the source document with an XSD, or would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="43b26-129">Este ejemplo utiliza el mismo documento de origen, Source.xml, que el ejemplo anterior de este tema.</span><span class="sxs-lookup"><span data-stu-id="43b26-129">This example uses the same source document, Source.xml, as the previous example in this topic.</span></span> <span data-ttu-id="43b26-130">También produce exactamente el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="43b26-130">It also produces exactly the same output.</span></span>  
  
 <span data-ttu-id="43b26-131">Se prefiere usar la clase <xref:System.Xml.Linq.XStreamingElement> para la transmisión por secuencias de la salida XML a sobrescribir una clase <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="43b26-131">Using <xref:System.Xml.Linq.XStreamingElement> for streaming the output XML is preferred over writing to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null) {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    IEnumerable<XElement> srcTree =  
        from el in StreamCustomerItem("Source.xml")  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        );  
    XmlWriterSettings xws = new XmlWriterSettings();  
    xws.OmitXmlDeclaration = true;  
    xws.Indent = true;  
    using (XmlWriter xw = XmlWriter.Create("Output.xml", xws)) {  
        xw.WriteStartElement("Root");  
        foreach (XElement el in srcTree)  
            el.WriteTo(xw);  
        xw.WriteEndElement();  
    }  
  
    string str = File.ReadAllText("Output.xml");  
    Console.WriteLine(str);  
}  
```  
  
 <span data-ttu-id="43b26-132">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="43b26-132">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  