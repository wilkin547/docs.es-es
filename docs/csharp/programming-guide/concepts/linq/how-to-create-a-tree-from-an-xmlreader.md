---
title: Procedimiento para crear un árbol a partir de un objeto XmlReader (C#)
description: Aprenda a crear un árbol XML directamente desde una instancia de XmlReader. Vea un ejemplo en el que se muestra cómo crear un objeto T:System.Xml.XmlReader.
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: 3801177e664d142652d38748d44eaf3f274239dd
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302664"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a><span data-ttu-id="6bfa2-104">Procedimiento para crear un árbol a partir de un objeto XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="6bfa2-104">How to create a tree from an XmlReader (C#)</span></span>
<span data-ttu-id="6bfa2-105">En este tema se muestra cómo crear un árbol XML directamente de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="6bfa2-105">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="6bfa2-106">Para crear un <xref:System.Xml.Linq.XElement> de <xref:System.Xml.XmlReader>, debe colocar el <xref:System.Xml.XmlReader> en un nodo de elemento.</span><span class="sxs-lookup"><span data-stu-id="6bfa2-106">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="6bfa2-107"><xref:System.Xml.XmlReader> omitirá los comentarios y las instrucciones de procesamiento, pero si <xref:System.Xml.XmlReader> se coloca en un nodo de texto, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="6bfa2-107">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="6bfa2-108">Para evitar tales errores, coloque siempre <xref:System.Xml.XmlReader> en un elemento ante de crear un árbol XML de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="6bfa2-108">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bfa2-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6bfa2-109">Example</span></span>  
 <span data-ttu-id="6bfa2-110">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Libros (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6bfa2-110">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="6bfa2-111">El siguiente código crea un objeto `T:System.Xml.XmlReader` y lee nodos hasta que encuentra el primer nodo de elemento.</span><span class="sxs-lookup"><span data-stu-id="6bfa2-111">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="6bfa2-112">A continuación, carga el objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="6bfa2-112">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="6bfa2-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6bfa2-113">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6bfa2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bfa2-114">See also</span></span>

- [<span data-ttu-id="6bfa2-115">Analizar XML (C#)</span><span class="sxs-lookup"><span data-stu-id="6bfa2-115">Parsing XML (C#)</span></span>](how-to-parse-a-string.md)
