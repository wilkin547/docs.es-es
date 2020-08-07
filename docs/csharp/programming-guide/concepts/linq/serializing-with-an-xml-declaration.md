---
title: Serializar con una declaración XML (C#)
description: Aprenda sobre las configuraciones en las que la serialización de C# genera una declaración XML, como la serialización en un archivo, TextWriter y XmlWriter.
ms.date: 07/20/2015
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
ms.openlocfilehash: 7e91b61f037d28149f7c2355f4233dc319b54627
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302365"
---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="e5cb5-103">Serializar con una declaración XML (C#)</span><span class="sxs-lookup"><span data-stu-id="e5cb5-103">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="e5cb5-104">En este tema se describe cómo controlar si la serialización genera una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="e5cb5-104">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="e5cb5-105">Generación de declaración XML</span><span class="sxs-lookup"><span data-stu-id="e5cb5-105">XML Declaration Generation</span></span>  
 <span data-ttu-id="e5cb5-106">La serialización en <xref:System.IO.File> o <xref:System.IO.TextWriter> mediante el método <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> o el método <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> genera una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="e5cb5-106">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="e5cb5-107">Cuando serializa en <xref:System.Xml.XmlWriter>, la configuración del escritor (especificada en un objeto <xref:System.Xml.XmlWriterSettings>) determina si se genera una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="e5cb5-107">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="e5cb5-108">Si está serializando en una cadena mediante el método `ToString`, el XML resultante no incluirá una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="e5cb5-108">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="e5cb5-109">Serializar con una declaración XML</span><span class="sxs-lookup"><span data-stu-id="e5cb5-109">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="e5cb5-110">En el ejemplo siguiente se crea un <xref:System.Xml.Linq.XElement>, se guarda el documento en un archivo y, a continuación, se imprime el archivo en la consola:</span><span class="sxs-lookup"><span data-stu-id="e5cb5-110">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="e5cb5-111">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e5cb5-111">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="e5cb5-112">Serializar sin una declaración XML</span><span class="sxs-lookup"><span data-stu-id="e5cb5-112">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="e5cb5-113">En el siguiente ejemplo se muestra cómo guardar un <xref:System.Xml.Linq.XElement> en un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="e5cb5-113">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 <span data-ttu-id="e5cb5-114">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e5cb5-114">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5cb5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5cb5-115">See also</span></span>

- [<span data-ttu-id="e5cb5-116">Serializar árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="e5cb5-116">Serializing XML Trees (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
