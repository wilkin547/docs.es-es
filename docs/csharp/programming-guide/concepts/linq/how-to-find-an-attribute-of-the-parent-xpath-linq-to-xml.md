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
