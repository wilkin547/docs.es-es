---
title: Procedimiento para buscar descendientes de un elemento secundario (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: fb3e20ce21c1f6d2a71f2f71b8acec7cecf0f3ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141097"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a>Procedimiento para buscar descendientes de un elemento secundario (XPath-LINQ to XML) (C#)
En este tema se muestra cómo obtener los elementos descendientes de un elemento secundario con un nombre particular.  
  
 La expresión XPath es:  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo simula los problemas de extraer texto de una representación XML de un documento de un procesador de texto. Primero selecciona todos los elementos de `Paragraph` y después selecciona todos los elementos descendientes de `Text` de cada elemento `Paragraph`. Esto no selecciona los elementos `Text` descendientes del elemento `Comment`.  
  
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
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  