---
title: "Cómo: consultar un objeto ArrayList con LINQ (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 176358a9-d765-4b57-9557-7feb4428138d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f48b06c23b1e28fccb953638954a8d9afefe574e
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-an-arraylist-with-linq-visual-basic"></a>Cómo: consultar un objeto ArrayList con LINQ (Visual Basic)
Cuando se utiliza LINQ a consultas no genérica <xref:System.Collections.IEnumerable>colecciones como <xref:System.Collections.ArrayList>, debe declarar explícitamente el tipo de la variable de rango para reflejar el tipo específico de los objetos de la colección.</xref:System.Collections.ArrayList> </xref:System.Collections.IEnumerable> Por ejemplo, si tiene un <xref:System.Collections.ArrayList>de `Student` objetos, su [cláusula From](../../../../visual-basic/language-reference/queries/from-clause.md) debería tener este aspecto:</xref:System.Collections.ArrayList>  
  
```  
Dim query = From student As Student In arrList   
...  
```  
  
 Al especificar el tipo de la variable de rango, convierte cada elemento de la <xref:System.Collections.ArrayList>a una `Student`.</xref:System.Collections.ArrayList>  
  
 El uso de una variable de rango con tipo explícito en una expresión de consulta es equivalente a llamar a la <xref:System.Linq.Enumerable.Cast%2A>método.</xref:System.Linq.Enumerable.Cast%2A> <xref:System.Linq.Enumerable.Cast%2A>produce una excepción si no se puede realizar la conversión especificada.</xref:System.Linq.Enumerable.Cast%2A> <xref:System.Linq.Enumerable.Cast%2A>y <xref:System.Linq.Enumerable.OfType%2A>son los dos métodos de operador de consulta estándar que funcionan en la no genérica <xref:System.Collections.IEnumerable>tipos.</xref:System.Collections.IEnumerable> </xref:System.Linq.Enumerable.OfType%2A></xref:System.Linq.Enumerable.Cast%2A> En Visual Basic, se debe llamar explícitamente el <xref:System.Linq.Enumerable.Cast%2A>método en el origen de datos para garantizar un tipo de variable de rango específico.</xref:System.Linq.Enumerable.Cast%2A> Para obtener más información, consulte[relaciones entre tipos en operaciones de consulta (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una consulta simple en un <xref:System.Collections.ArrayList>.</xref:System.Collections.ArrayList> Tenga en cuenta que este ejemplo usa los inicializadores de objeto cuando el código llama a la <xref:System.Collections.ArrayList.Add%2A>(método), pero esto no es un requisito.</xref:System.Collections.ArrayList.Add%2A>  
  
```vb  
Imports System.Collections  
Imports System.Linq  
  
Module Module1  
  
    Public Class Student  
        Public Property FirstName As String  
        Public Property LastName As String  
        Public Property Scores As Integer()  
    End Class  
  
    Sub Main()  
  
        Dim student1 As New Student With {.FirstName = "Svetlana",   
                                     .LastName = "Omelchenko",   
                                     .Scores = New Integer() {98, 92, 81, 60}}  
        Dim student2 As New Student With {.FirstName = "Claire",   
                                    .LastName = "O'Donnell",   
                                    .Scores = New Integer() {75, 84, 91, 39}}  
        Dim student3 As New Student With {.FirstName = "Cesar",   
                                    .LastName = "Garcia",   
                                    .Scores = New Integer() {97, 89, 85, 82}}  
        Dim student4 As New Student With {.FirstName = "Sven",   
                                    .LastName = "Mortensen",   
                                    .Scores = New Integer() {88, 94, 65, 91}}  
  
        Dim arrList As New ArrayList()  
        arrList.Add(student1)  
        arrList.Add(student2)  
        arrList.Add(student3)  
        arrList.Add(student4)  
  
        ' Use an explicit type for non-generic collections  
        Dim query = From student As Student In arrList   
                    Where student.Scores(0) > 95   
                    Select student  
  
        For Each student As Student In query  
            Console.WriteLine(student.LastName & ": " & student.Scores(0))  
        Next  
        ' Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
End Module  
' Output:  
'   Omelchenko: 98  
'   Garcia: 97  
```  
  
## <a name="see-also"></a>Vea también  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

