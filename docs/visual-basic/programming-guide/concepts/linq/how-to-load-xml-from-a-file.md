---
title: 'Cómo: cargar XML desde un archivo (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: e2d337ad-8ac8-4671-b694-30e5ca1413b7
ms.openlocfilehash: fce4ebee075f5e622de17bd5227dd6e4ae9cccd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641444"
---
# <a name="how-to-load-xml-from-a-file-visual-basic"></a><span data-ttu-id="6a8b8-102">Cómo: cargar XML desde un archivo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a8b8-102">How to: Load XML from a File (Visual Basic)</span></span>
<span data-ttu-id="6a8b8-103">En este tema se muestra cómo cargar XML de una dirección URI usando el método <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-103">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a8b8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a8b8-104">Example</span></span>  
 <span data-ttu-id="6a8b8-105">El siguiente ejemplo muestra cómo cargar un documento XML desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-105">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="6a8b8-106">El siguiente ejemplo carga books.xml y produce el árbol XML en la consola.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-106">The following example loads books.xml and outputs the XML tree to the console.</span></span>  
  
 <span data-ttu-id="6a8b8-107">En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Libros (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6a8b8-107">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim booksFromFile As XElement = XElement.Load("books.xml")  
Console.WriteLine(booksFromFile)  
```  
  
 <span data-ttu-id="6a8b8-108">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6a8b8-108">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6a8b8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a8b8-109">See Also</span></span>  
 [<span data-ttu-id="6a8b8-110">Analizar XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a8b8-110">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
