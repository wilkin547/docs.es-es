---
title: "Cómo: buscar elementos secundarios en función de la posición (XPath-LINQ to XML) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 6831e1db-5e97-444f-a7a1-d0a87104b005
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7c1ef9db560de02efa20dbe88ff0e73ffd9e7fff
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-visual-basic"></a>Cómo: buscar elementos secundarios en función de la posición (XPath-LINQ to XML) (Visual Basic)
En ocasiones, deseará buscar elementos en función de su posición. Quizá desee buscar el segundo elemento o buscar el tercero en el quinto elemento.  
  
 La expresión XPath es:  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 Existen dos aproximaciones posibles para escribir esta consulta de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] de forma diferida. Puede usar el <xref:System.Linq.Enumerable.Skip%2A>y <xref:System.Linq.Enumerable.Take%2A>operadores, o puede utilizar el <xref:System.Linq.Enumerable.Where%2A>sobrecarga que toma un índice.</xref:System.Linq.Enumerable.Where%2A> </xref:System.Linq.Enumerable.Take%2A> </xref:System.Linq.Enumerable.Skip%2A> Cuando se usa el <xref:System.Linq.Enumerable.Where%2A>sobrecarga, utiliza una expresión lambda que toma dos argumentos.</xref:System.Linq.Enumerable.Where%2A> El siguiente ejemplo muestra ambos métodos para seleccionar elementos en base a la posición.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo encontrará el segundo en el cuarto elemento de `Test`. El resultado es una colección de elementos.  
  
 Este ejemplo utiliza el siguiente documento XML: [archivo XML de ejemplo: configuración de prueba (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).  
  
```vb  
Dim testCfg As XElement = XElement.Load("TestConfig.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test").Skip(1).Take(3)  
  
'LINQ to XML query  
Dim list2 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test"). _  
    Where(Function(ByVal el, ByVal idx) idx >= 1 And idx <= 3)  
  
' XPath expression  
Dim list3 As IEnumerable(Of XElement) = _  
    testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]")  
  
If list1.Count() = list2.Count() And _  
       list1.Count() = list3.Count() And _  
       list1.Intersect(list2).Count() = list1.Count() And _  
       list1.Intersect(list3).Count() = list1.Count() Then  
  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML para usuarios de XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
