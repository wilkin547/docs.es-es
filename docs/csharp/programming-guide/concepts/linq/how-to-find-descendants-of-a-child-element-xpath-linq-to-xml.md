---
title: Procedimiento para buscar descendientes de un elemento secundario (XPath-LINQ to XML) (C#)
description: Aprenda a buscar elementos descendientes de un elemento secundario con un nombre determinado mediante una expresión XPath.
ms.date: 07/20/2015
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: b8e110abc2e0df99c3fdf6d2846c7cbbc4736c1a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303262"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="0ff4a-103">Procedimiento para buscar descendientes de un elemento secundario (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0ff4a-103">How to find descendants of a child element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="0ff4a-104">En este tema se muestra cómo obtener los elementos descendientes de un elemento secundario con un nombre particular.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-104">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="0ff4a-105">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="0ff4a-105">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="0ff4a-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ff4a-106">Example</span></span>  
 <span data-ttu-id="0ff4a-107">Este ejemplo simula los problemas de extraer texto de una representación XML de un documento de un procesador de texto.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-107">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="0ff4a-108">Primero selecciona todos los elementos de `Paragraph` y después selecciona todos los elementos descendientes de `Text` de cada elemento `Paragraph`.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-108">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="0ff4a-109">Esto no selecciona los elementos `Text` descendientes del elemento `Comment`.</span><span class="sxs-lookup"><span data-stu-id="0ff4a-109">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
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
  
 <span data-ttu-id="0ff4a-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0ff4a-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  