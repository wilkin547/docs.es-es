---
title: Procedimiento para buscar atributos de elementos del mismo nivel con un nombre específico (XPath-LINQ to XML) (C#)
description: Aprenda a buscar todos los atributos de los elementos secundarios del nodo de contexto. Revise un ejemplo de código que usa un archivo XML de ejemplo.
ms.date: 07/20/2015
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: 12bba22c91fef92fc3383d028ff9dfb8bd3cfa3e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301702"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a><span data-ttu-id="2eac7-104">Procedimiento para buscar atributos de elementos del mismo nivel con un nombre específico (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2eac7-104">How to find attributes of siblings with a specific name (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="2eac7-105">En este tema se muestra cómo buscar todos los atributos de los elementos secundarios del nodo de contexto.</span><span class="sxs-lookup"><span data-stu-id="2eac7-105">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="2eac7-106">Sólo se devuelven los atributos con un nombre específico en la recopilación.</span><span class="sxs-lookup"><span data-stu-id="2eac7-106">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="2eac7-107">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="2eac7-107">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="2eac7-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2eac7-108">Example</span></span>  
 <span data-ttu-id="2eac7-109">Este ejemplo primero busca un elemento `Book`, después busca todos los elementos secundarios con el nombre `Book` y después busca todos los atributos con el nombre `id`.</span><span class="sxs-lookup"><span data-stu-id="2eac7-109">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="2eac7-110">El resultado es una colección de atributos.</span><span class="sxs-lookup"><span data-stu-id="2eac7-110">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="2eac7-111">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Libros (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2eac7-111">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="2eac7-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="2eac7-112">This example produces the following output:</span></span>  
  
```output  
Results are identical  
id="bk101"  
id="bk102"  
```  
  