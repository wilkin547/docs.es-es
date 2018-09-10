---
title: 'Cómo: Buscar descendientes de un elemento secundario (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: 2fbb5111cdabac5ecbdc1db43e2ce2f41ebb7303
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523209"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="f6eb2-102">Cómo: Buscar descendientes de un elemento secundario (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f6eb2-102">How to: Find Descendants of a Child Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="f6eb2-103">En este tema se muestra cómo obtener los elementos descendientes de un elemento secundario con un nombre particular.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-103">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="f6eb2-104">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="f6eb2-104">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="f6eb2-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6eb2-105">Example</span></span>  
 <span data-ttu-id="f6eb2-106">Este ejemplo simula los problemas de extraer texto de una representación XML de un documento de un procesador de texto.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-106">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="f6eb2-107">Primero selecciona todos los elementos de `Paragraph` y después selecciona todos los elementos descendientes de `Text` de cada elemento `Paragraph`.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-107">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="f6eb2-108">Esto no selecciona los elementos `Text` descendientes del elemento `Comment`.</span><span class="sxs-lookup"><span data-stu-id="f6eb2-108">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root>  
  <Paragraph>  
    <Text>This is the start of</Text>  
  </Paragraph>  
  <Comment>  
    <Text>This comment is not part of the paragraph text.</Text>  
  </Comment>  
  <Paragraph>  
    <Annotation Emphasis='true'>  
      <Text> a sentence.</Text>  
    </Annotation>  
  </Paragraph>  
  <Paragraph>  
    <Text>  This is a second sentence.</Text>  
  </Paragraph>  
</Root>");  
  
// LINQ to XML query  
string str1 =  
    root  
    .Elements("Paragraph")  
    .Descendants("Text")  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
// XPath expression  
string str2 =  
    ((IEnumerable)root.XPathEvaluate("./Paragraph//Text/text()"))  
    .Cast<XText>()  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
if (str1 == str2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(str2);  
```  
  
 <span data-ttu-id="f6eb2-109">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f6eb2-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6eb2-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6eb2-110">See Also</span></span>

- [<span data-ttu-id="f6eb2-111">LINQ to XML para usuarios de XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="f6eb2-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
