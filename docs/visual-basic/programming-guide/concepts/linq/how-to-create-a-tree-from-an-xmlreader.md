---
title: Procedimiento para crear un árbol a partir de un objeto XmlReader
ms.date: 07/20/2015
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
ms.openlocfilehash: 25c15ff08563b12b26041a536dfbca1c9cce260a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414613"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a><span data-ttu-id="a6919-102">Cómo: crear un árbol a partir de un objeto XmlReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6919-102">How to: Create a Tree from an XmlReader (Visual Basic)</span></span>

<span data-ttu-id="a6919-103">En este tema se muestra cómo crear un árbol XML directamente de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="a6919-103">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="a6919-104">Para crear un <xref:System.Xml.Linq.XElement> de <xref:System.Xml.XmlReader>, debe colocar el <xref:System.Xml.XmlReader> en un nodo de elemento.</span><span class="sxs-lookup"><span data-stu-id="a6919-104">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="a6919-105"><xref:System.Xml.XmlReader> omitirá los comentarios y las instrucciones de procesamiento, pero si <xref:System.Xml.XmlReader> se coloca en un nodo de texto, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="a6919-105">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="a6919-106">Para evitar tales errores, coloque siempre <xref:System.Xml.XmlReader> en un elemento ante de crear un árbol XML de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="a6919-106">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>

## <a name="example"></a><span data-ttu-id="a6919-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6919-107">Example</span></span>

<span data-ttu-id="a6919-108">En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: libros (LINQ to XML)](sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a6919-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](sample-xml-file-books-linq-to-xml.md).</span></span>

<span data-ttu-id="a6919-109">El siguiente código crea un objeto `T:System.Xml.XmlReader` y lee nodos hasta que encuentra el primer nodo de elemento.</span><span class="sxs-lookup"><span data-stu-id="a6919-109">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="a6919-110">A continuación, carga el objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a6919-110">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>

```vb
Dim r As XmlReader = XmlReader.Create("books.xml")
Do While r.NodeType <> XmlNodeType.Element
    r.Read()
Loop
Dim e As XElement = XElement.Load(r)
Console.WriteLine(e)
```

<span data-ttu-id="a6919-111">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a6919-111">This example produces the following output:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a6919-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6919-112">See also</span></span>

- [<span data-ttu-id="a6919-113">Analizar XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6919-113">Parsing XML (Visual Basic)</span></span>](parsing-xml.md)
