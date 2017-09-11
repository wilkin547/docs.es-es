---
title: "Cómo: Buscar descendientes de un elemento secundario (XPath-LINQ to XML) (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b645290b6cac55e48be0b15a33307f53c08edd6
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="0fa9a-102">Cómo: Buscar descendientes de un elemento secundario (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa9a-102">How to: Find Descendants of a Child Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="0fa9a-103">En este tema se muestra cómo obtener los elementos descendientes de un elemento secundario con un nombre particular.</span><span class="sxs-lookup"><span data-stu-id="0fa9a-103">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="0fa9a-104">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="0fa9a-104">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="0fa9a-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0fa9a-105">Example</span></span>  
 <span data-ttu-id="0fa9a-106">Este ejemplo simula los problemas de extraer texto de una representación XML de un documento de un procesador de texto.</span><span class="sxs-lookup"><span data-stu-id="0fa9a-106">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="0fa9a-107">Primero selecciona todos los elementos de `Paragraph` y después selecciona todos los elementos descendientes de `Text` de cada elemento `Paragraph`.</span><span class="sxs-lookup"><span data-stu-id="0fa9a-107">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="0fa9a-108">Esto no selecciona los elementos `Text` descendientes del elemento `Comment`.</span><span class="sxs-lookup"><span data-stu-id="0fa9a-108">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
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
  
 <span data-ttu-id="0fa9a-109">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0fa9a-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fa9a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fa9a-110">See Also</span></span>  
 [<span data-ttu-id="0fa9a-111">LINQ to XML para usuarios de XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa9a-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

