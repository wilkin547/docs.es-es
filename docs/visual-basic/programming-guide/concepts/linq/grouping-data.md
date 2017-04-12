---
title: Agrupar datos (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d89ae6d155ab901b03cf92a7508261fb147b97b7
ms.lasthandoff: 03/13/2017

---
# <a name="grouping-data-visual-basic"></a>Agrupar datos (Visual Basic)
El agrupamiento hace referencia a la operación de colocar datos en grupos para que los elementos de cada grupo compartan un atributo común.  
  
 La ilustración siguiente muestra los resultados de agrupar una secuencia de caracteres. La clave de cada grupo es el carácter.  
  
 ![Operaciones de agrupamiento en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")  
  
 Los métodos de operador de consulta estándar que agrupan los elementos de datos se muestran en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de expresiones de consulta de Visual Basic|Más información|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|GroupBy|Agrupa los elementos que comparten un atributo común. Cada grupo está representado por un <xref:System.Linq.IGrouping%602>objeto.</xref:System.Linq.IGrouping%602>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName>|  
|ToLookup|Inserta elementos en una <xref:System.Linq.Lookup%602>(diccionario uno a varios) según una función del selector de claves.</xref:System.Linq.Lookup%602>|No es aplicable.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Ejemplo de sintaxis de expresiones de consulta  
 El siguiente ejemplo de código utiliza el `Group By` cláusula para agrupar los enteros en una lista según si son par o impar.  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers   
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq></xref:System.Linq>   
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Group By cláusula](../../../../visual-basic/language-reference/queries/group-by-clause.md)   
 [Cómo: agrupar archivos por extensión (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)   
 [Cómo: dividir un archivo en varios archivos mediante el uso de grupos (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
