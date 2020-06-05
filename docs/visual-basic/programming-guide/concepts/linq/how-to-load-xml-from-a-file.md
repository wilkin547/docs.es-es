---
title: Procedimiento para cargar un documento XML desde un archivo
ms.date: 07/20/2015
ms.assetid: e2d337ad-8ac8-4671-b694-30e5ca1413b7
ms.openlocfilehash: faea93b8eea2b713a8beb7fe199be7d644a07706
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398004"
---
# <a name="how-to-load-xml-from-a-file-visual-basic"></a>Cómo: cargar XML desde un archivo (Visual Basic)

En este tema se muestra cómo cargar XML de una dirección URI usando el método <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

El siguiente ejemplo muestra cómo cargar un documento XML desde un archivo. El siguiente ejemplo carga books.xml y produce el árbol XML en la consola.

En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: libros (LINQ to XML)](sample-xml-file-books-linq-to-xml.md).

```vb
Dim booksFromFile As XElement = XElement.Load("books.xml")
Console.WriteLine(booksFromFile)
```

Este código genera el siguiente resultado:

```xml
<Catalog>
  <Book id="bk101">
    <Author>Garghentini, Davide</Author>
    <Title>XML Developer's Guide</Title>
    <Genre>Computer</Genre>
    <Price>44.95</Price>
    <PublishDate>2000-10-01</PublishDate>
    <Description>An in-depth look at creating applications
      with XML.</Description>
  </Book>
  <Book id="bk102">
    <Author>Garcia, Debra</Author>
    <Title>Midnight Rain</Title>
    <Genre>Fantasy</Genre>
    <Price>5.95</Price>
    <PublishDate>2000-12-16</PublishDate>
    <Description>A former architect battles corporate zombies,
      an evil sorceress, and her own childhood to become queen
      of the world.</Description>
  </Book>
</Catalog>
```

## <a name="see-also"></a>Consulte también

- [Analizar XML (Visual Basic)](parsing-xml.md)
