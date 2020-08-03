---
title: Procedimiento para leer y escribir un documento codificado (C#)
description: Aprenda a crear un documento XML codificado en C# mediante la adición de un elemento XDeclaration al árbol XML y el establecimiento de la codificación en el nombre de página de códigos deseado.
ms.date: 07/20/2015
ms.assetid: 84f64e71-39a6-42c6-ad68-f052bb158a03
ms.openlocfilehash: ed02b7467f4de71455da516a6c894070337684e7
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104319"
---
# <a name="how-to-read-and-write-an-encoded-document-c"></a><span data-ttu-id="a5398-103">Procedimiento para leer y escribir un documento codificado (C#)</span><span class="sxs-lookup"><span data-stu-id="a5398-103">How to read and write an encoded document (C#)</span></span>
<span data-ttu-id="a5398-104">Para crear un documento XML codificado, se agrega un <xref:System.Xml.Linq.XDeclaration> al árbol XML, estableciendo la codificación en el nombre de página de códigos deseado.</span><span class="sxs-lookup"><span data-stu-id="a5398-104">To create an encoded XML document, you add an <xref:System.Xml.Linq.XDeclaration> to the XML tree, setting the encoding to the desired code page name.</span></span>  
  
 <span data-ttu-id="a5398-105">Los valores devueltos por <xref:System.Text.Encoding.WebName%2A> son valores válidos.</span><span class="sxs-lookup"><span data-stu-id="a5398-105">Any value returned by <xref:System.Text.Encoding.WebName%2A> is a valid value.</span></span>  
  
 <span data-ttu-id="a5398-106">Si lee un documento codificado, la propiedad <xref:System.Xml.Linq.XDeclaration.Encoding%2A> estará establecida en el nombre de la página de códigos.</span><span class="sxs-lookup"><span data-stu-id="a5398-106">If you read an encoded document, the <xref:System.Xml.Linq.XDeclaration.Encoding%2A> property will be set to the code page name.</span></span>  
  
 <span data-ttu-id="a5398-107">Si establece <xref:System.Xml.Linq.XDeclaration.Encoding%2A> en un nombre de página de códigos válido, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se serializará con la codificación especificada.</span><span class="sxs-lookup"><span data-stu-id="a5398-107">If you set <xref:System.Xml.Linq.XDeclaration.Encoding%2A> to a valid code page name, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will serialize with the specified encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5398-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5398-108">Example</span></span>  
 <span data-ttu-id="a5398-109">En el ejemplo siguiente se crean dos documentos, uno con codificación utf-8 y otro con codificación utf-16.</span><span class="sxs-lookup"><span data-stu-id="a5398-109">The following example creates two documents, one with utf-8 encoding, and one with utf-16 encoding.</span></span> <span data-ttu-id="a5398-110">A continuación se cargan los documentos y se imprime la codificación en la consola.</span><span class="sxs-lookup"><span data-stu-id="a5398-110">It then loads the documents and prints the encoding to the console.</span></span>  
  
```csharp  
Console.WriteLine("Creating a document with utf-8 encoding");  
XDocument encodedDoc8 = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc8.Save("EncodedUtf8.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
Console.WriteLine("Creating a document with utf-16 encoding");  
XDocument encodedDoc16 = new XDocument(  
    new XDeclaration("1.0", "utf-16", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc16.Save("EncodedUtf16.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc8 = XDocument.Load("EncodedUtf8.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc16 = XDocument.Load("EncodedUtf16.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding);  
```  
  
 <span data-ttu-id="a5398-111">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a5398-111">This example produces the following output:</span></span>  
  
```output  
Creating a document with utf-8 encoding  
Encoding is:utf-8  
  
Creating a document with utf-16 encoding  
Encoding is:utf-16  
  
Encoded document:  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-8  
  
Encoded document:  
<?xml version="1.0" encoding="utf-16" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-16  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5398-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5398-112">See also</span></span>

- <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=nameWithType>
