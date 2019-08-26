---
title: Procedimiento para buscar un atributo del elemento principal (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 2e6c124d2653fb4426b3abb693f0b58daa5413c2
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593615"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="1e75a-102">Procedimiento para buscar un atributo del elemento principal (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="1e75a-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="1e75a-103">En este tema se muestra cómo desplazarse hasta el elemento primario y buscar un atributo en él.</span><span class="sxs-lookup"><span data-stu-id="1e75a-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="1e75a-104">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="1e75a-104">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="1e75a-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e75a-105">Example</span></span>

<span data-ttu-id="1e75a-106">Este ejemplo busca primero un elemento `Author`.</span><span class="sxs-lookup"><span data-stu-id="1e75a-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="1e75a-107">Después busca el atributo `id` del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="1e75a-107">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="1e75a-108">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Libros (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1e75a-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

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

<span data-ttu-id="1e75a-109">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="1e75a-109">This example produces the following output:</span></span>

```
Results are identical
id="bk101"
```
