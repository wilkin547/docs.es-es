---
title: "Serializar con una declaración XML (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 36ffb8ddd584785c660896ca77707d504638852f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="e3ac0-102">Serializar con una declaración XML (C#)</span><span class="sxs-lookup"><span data-stu-id="e3ac0-102">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="e3ac0-103">En este tema se describe cómo controlar si la serialización genera una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="e3ac0-104">Generación de declaración XML</span><span class="sxs-lookup"><span data-stu-id="e3ac0-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="e3ac0-105">La serialización en <xref:System.IO.File> o <xref:System.IO.TextWriter> mediante el método <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> o el método <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> genera una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> method generates an XML declaration.</span></span> <span data-ttu-id="e3ac0-106">Cuando serializa en <xref:System.Xml.XmlWriter>, la configuración del escritor (especificada en un objeto <xref:System.Xml.XmlWriterSettings>) determina si se genera una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="e3ac0-107">Si está serializando en una cadena mediante el método `ToString`, el XML resultante no incluirá una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="e3ac0-108">Serializar con una declaración XML</span><span class="sxs-lookup"><span data-stu-id="e3ac0-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="e3ac0-109">En el ejemplo siguiente se crea un <xref:System.Xml.Linq.XElement>, se guarda el documento en un archivo y, a continuación, se imprime el archivo en la consola:</span><span class="sxs-lookup"><span data-stu-id="e3ac0-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="e3ac0-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e3ac0-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="e3ac0-111">Serializar sin una declaración XML</span><span class="sxs-lookup"><span data-stu-id="e3ac0-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="e3ac0-112">En el siguiente ejemplo se muestra cómo guardar un <xref:System.Xml.Linq.XElement> en un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="e3ac0-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
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
  
 <span data-ttu-id="e3ac0-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e3ac0-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3ac0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3ac0-114">See Also</span></span>  
 [<span data-ttu-id="e3ac0-115">Serializar árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="e3ac0-115">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)

