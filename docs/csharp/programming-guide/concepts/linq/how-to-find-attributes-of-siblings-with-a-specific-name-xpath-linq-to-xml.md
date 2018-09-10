---
title: 'Cómo: Buscar atributos de elementos del mismo nivel con un nombre específico (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: 60b6529f310ccbb02160ff96e1db7870bcc71058
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863126"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a><span data-ttu-id="6321f-102">Cómo: Buscar atributos de elementos del mismo nivel con un nombre específico (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6321f-102">How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="6321f-103">En este tema se muestra cómo buscar todos los atributos de los elementos secundarios del nodo de contexto.</span><span class="sxs-lookup"><span data-stu-id="6321f-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="6321f-104">Sólo se devuelven los atributos con un nombre específico en la recopilación.</span><span class="sxs-lookup"><span data-stu-id="6321f-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="6321f-105">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="6321f-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="6321f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6321f-106">Example</span></span>  
 <span data-ttu-id="6321f-107">Este ejemplo primero busca un elemento `Book`, después busca todos los elementos secundarios con el nombre `Book` y después busca todos los atributos con el nombre `id`.</span><span class="sxs-lookup"><span data-stu-id="6321f-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="6321f-108">El resultado es una colección de atributos.</span><span class="sxs-lookup"><span data-stu-id="6321f-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="6321f-109">En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Libros (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6321f-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =   
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="6321f-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6321f-110">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a><span data-ttu-id="6321f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6321f-111">See Also</span></span>

- [<span data-ttu-id="6321f-112">LINQ to XML para usuarios de XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="6321f-112">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
