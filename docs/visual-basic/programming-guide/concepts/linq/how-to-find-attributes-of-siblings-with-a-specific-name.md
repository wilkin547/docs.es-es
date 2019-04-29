---
title: Procedimiento Buscar atributos de elementos del mismo nivel con un nombre específico (XPath-LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 83b3ddca-830a-4b71-9756-9e4bdf907302
ms.openlocfilehash: 07fb5647950c450d08ab3235ac8cb396eff15305
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780580"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="3773d-102">Procedimiento Buscar atributos de elementos del mismo nivel con un nombre específico (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3773d-102">How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="3773d-103">En este tema se muestra cómo buscar todos los atributos de los elementos secundarios del nodo de contexto.</span><span class="sxs-lookup"><span data-stu-id="3773d-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="3773d-104">Sólo se devuelven los atributos con un nombre específico en la recopilación.</span><span class="sxs-lookup"><span data-stu-id="3773d-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="3773d-105">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="3773d-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="3773d-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3773d-106">Example</span></span>  
 <span data-ttu-id="3773d-107">Este ejemplo primero busca un elemento `Book`, después busca todos los elementos secundarios con el nombre `Book` y después busca todos los atributos con el nombre `id`.</span><span class="sxs-lookup"><span data-stu-id="3773d-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="3773d-108">El resultado es una colección de atributos.</span><span class="sxs-lookup"><span data-stu-id="3773d-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="3773d-109">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Libros (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3773d-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books as XDocument = XDocument.Load("Books.xml")  
Dim book As XElement = books.Root.<Book>(0)  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XAttribute) = _  
    From el In book.Parent.<Book> _  
    Select el.Attribute("id")  
  
' XPath expression  
Dim list2 As IEnumerable(Of XAttribute) = DirectCast(book. _  
    XPathEvaluate("../Book/@id"), IEnumerable).Cast(Of XAttribute)()  
  
If list1.Count() = list2.Count() And _  
        (list1.Intersect(list2)).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XAttribute In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="3773d-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="3773d-110">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a><span data-ttu-id="3773d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3773d-111">See also</span></span>

- [<span data-ttu-id="3773d-112">LINQ to XML para usuarios de XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3773d-112">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
