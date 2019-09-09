---
title: Procedimiento para buscar un atributo del elemento principal (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: aa602f6876b014c48a73dea9b2ff42eb953e5c4c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253774"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a>Procedimiento para buscar un atributo del elemento principal (XPath-LINQ to XML) (C#)

En este tema se muestra cómo desplazarse hasta el elemento primario y buscar un atributo en él.

La expresión XPath es:

`../@id`

## <a name="example"></a>Ejemplo

Este ejemplo busca primero un elemento `Author`. Después busca el atributo `id` del elemento primario.

Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Libros (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).

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

Este ejemplo produce el siguiente resultado:

```output
Results are identical
id="bk101"
```
