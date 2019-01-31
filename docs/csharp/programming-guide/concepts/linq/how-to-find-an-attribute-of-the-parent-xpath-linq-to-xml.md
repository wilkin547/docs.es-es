---
title: Procedimiento para buscar un atributo del elemento principal (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: e139e278141a8f42cddf8103f1c5d8d3195751e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621817"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="1df69-102">Procedimiento para buscar un atributo del elemento principal (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="1df69-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="1df69-103">En este tema se muestra cómo desplazarse hasta el elemento primario y buscar un atributo en él.</span><span class="sxs-lookup"><span data-stu-id="1df69-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="1df69-104">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="1df69-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="1df69-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1df69-105">Example</span></span>  
 <span data-ttu-id="1df69-106">Este ejemplo busca primero un elemento `Author`.</span><span class="sxs-lookup"><span data-stu-id="1df69-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="1df69-107">Después busca el atributo `id` del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="1df69-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="1df69-108">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Libros (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1df69-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement author =   
    books  
    .Root  
    .Element("Book")  
    .Element("Author");  
  
// LINQ to XML query  
XAttribute att1 =  
    author  
    .Parent  
    .Attribute("id");  
  
// XPath expression  
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();  
  
if (att1 == att2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(att1);  
```  
  
 <span data-ttu-id="1df69-109">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="1df69-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="1df69-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1df69-110">See also</span></span>

- [<span data-ttu-id="1df69-111">LINQ to XML para usuarios de XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="1df69-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
