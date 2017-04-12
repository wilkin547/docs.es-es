---
title: "Cómo: buscar el elemento relacionado anterior inmediato (XPath-LINQ to XML) (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 24e3fc1cdf03017a939424fa5df9b778116f95cd
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a>Cómo: buscar el elemento relacionado anterior inmediato (XPath-LINQ to XML) (Visual Basic)
Es posible que en alguna ocasión desee buscar el elemento del mismo nivel inmediatamente anterior a un nodo. Debido a las diferencias de semántica de los predicados posicionales para los ejes de los elementos del mismo nivel anteriores de XPath en comparación con [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], ésta es una de las comparaciones más interesantes.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, el [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] consulta utiliza el <xref:System.Linq.Enumerable.Last%2A>operador para buscar el último nodo en la colección devuelta por <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A> </xref:System.Linq.Enumerable.Last%2A> Por el contrario, la expresión XPath usa un predicado con un valor de 1 para buscar el elemento inmediatamente anterior.  
  
```vb  
Dim root As XElement = _   
    <Root>  
        <Child1/>  
        <Child2/>  
        <Child3/>  
        <Child4/>  
    </Root>  
Dim child4 As XElement = root.Element("Child4")  
  
' LINQ to XML query  
Dim el1 As XElement = child4.ElementsBeforeSelf().Last()  
  
' XPath expression  
Dim el2 As XElement = _  
    DirectCast(child4.XPathEvaluate("preceding-sibling::*[1]"),  _  
    IEnumerable).Cast(Of XElement)().First()  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Results are identical  
<Child3 />  
```  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML para usuarios de XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
