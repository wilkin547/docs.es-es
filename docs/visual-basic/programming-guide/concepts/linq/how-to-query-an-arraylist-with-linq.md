---
title: 'Cómo: Consultar un objeto ArrayList con LINQ'
ms.date: 07/20/2015
ms.assetid: 176358a9-d765-4b57-9557-7feb4428138d
ms.openlocfilehash: 94a3c6d4c381f41f9ba87bf3af93261712ad1136
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347754"
---
# <a name="how-to-query-an-arraylist-with-linq-visual-basic"></a>How to: Query an ArrayList with LINQ (Visual Basic)

Cuando use LINQ para consultar colecciones no genéricas <xref:System.Collections.IEnumerable> como <xref:System.Collections.ArrayList>, debe declarar explícitamente el tipo de variable de rango para reflejar el tipo específico de los objetos de la colección. For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md) should look like this:

```vb
Dim query = From student As Student In arrList
'...
```

Al especificar el tipo de la variable de rango, se convierte cada elemento de la <xref:System.Collections.ArrayList> en un `Student`.

El uso de una variable de rango con tipo explícito en una expresión de consulta es equivalente a llamar al método <xref:System.Linq.Enumerable.Cast%2A>. <xref:System.Linq.Enumerable.Cast%2A> genera una excepción si la conversión especificada no puede realizarse. <xref:System.Linq.Enumerable.Cast%2A> y <xref:System.Linq.Enumerable.OfType%2A> son los dos métodos de operador de consulta estándar que funcionan en tipos <xref:System.Collections.IEnumerable> no genéricos. In Visual Basic, you must explicitly call the <xref:System.Linq.Enumerable.Cast%2A> method on the data source to ensure a specific range variable type. For more information, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestra una consulta simple sobre un <xref:System.Collections.ArrayList>. Tenga en cuenta que en este ejemplo se usan inicializadores de objeto cuando el código llama al método <xref:System.Collections.ArrayList.Add%2A>, pero esto no es un requisito.

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

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
