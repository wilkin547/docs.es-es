---
title: "Cómo: buscar un elemento con un elemento secundario específico (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0d0a463-6a85-46c3-8453-ad25b0ecf93c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6ddb35e954d709548c6b32475f37454015e0a98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-an-element-with-a-specific-child-element-visual-basic"></a>Cómo: buscar un elemento con un elemento secundario específico (Visual Basic)
Este tema muestra cómo encontrar un elemento en particular que tenga un elemento secundario con un valor específico.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo busca el elemento `Test` que tenga un elemento secundario `CommandLine` con el valor de "Examp2.EXE".  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Configuración de prueba (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).  
  
```vb  
Dim root As XElement = XElement.Load("TestConfig.xml")  
Dim tests As IEnumerable(Of XElement) = _  
    From el In root.<Test> _  
    Where el.<CommandLine>.Value = "Examp2.EXE" _  
    Select el  
For Each el as XElement In tests  
    Console.WriteLine(el.@TestId)  
Next  
```  
  
 Este código genera el siguiente resultado:  
  
```  
0002  
0006  
```  
  
 Tenga en cuenta que este ejemplo se utiliza la [propiedad de eje secundario XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), [propiedad axis para atributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)y el [propiedad Value de XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres. Para obtener más información, consulte [trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Configuración de prueba en un espacio de nombres](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("TestConfigInNamespace.xml")  
        Dim tests As IEnumerable(Of XElement) = _  
            From el In root.<Test> _  
            Where el.<CommandLine>.Value = "Examp2.EXE" _  
            Select el  
        For Each el As XElement In tests  
            Console.WriteLine(el.@TestId)  
        Next  
    End Sub  
End Module  
```  
  
 Este código genera el siguiente resultado:  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [Consultas básicas (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Operaciones de proyección (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
