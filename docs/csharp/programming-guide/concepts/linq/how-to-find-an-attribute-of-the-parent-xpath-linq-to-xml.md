---
title: Procedimiento para buscar un atributo del elemento principal (XPath-LINQ to XML) (C#)
description: Aprenda a buscar un atributo del elemento principal. Vea un ejemplo de código en el que se usa un documento XML de ejemplo.
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 03344bb66f617970d9598c91366eb7d69514397a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303301"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="7553a-104">Procedimiento para buscar un atributo del elemento principal (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="7553a-104">How to find an attribute of the parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="7553a-105">En este tema se muestra cómo desplazarse hasta el elemento primario y buscar un atributo en él.</span><span class="sxs-lookup"><span data-stu-id="7553a-105">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="7553a-106">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="7553a-106">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="7553a-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7553a-107">Example</span></span>

<span data-ttu-id="7553a-108">Este ejemplo busca primero un elemento `Author`.</span><span class="sxs-lookup"><span data-stu-id="7553a-108">This example first finds an `Author` element.</span></span> <span data-ttu-id="7553a-109">Después busca el atributo `id` del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="7553a-109">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="7553a-110">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Libros (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7553a-110">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

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

<span data-ttu-id="7553a-111">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7553a-111">This example produces the following output:</span></span>

```output
Results are identical
id="bk101"
```
