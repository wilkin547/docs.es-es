---
title: Procedimiento para consultar un objeto ArrayList con LINQ
ms.date: 07/20/2015
ms.assetid: 176358a9-d765-4b57-9557-7feb4428138d
ms.openlocfilehash: b7b75e017fb314b5e5998b743dbf922f34fd9b7c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396472"
---
# <a name="how-to-query-an-arraylist-with-linq-visual-basic"></a><span data-ttu-id="3c977-102">Cómo: consultar una ArrayList con LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c977-102">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>

<span data-ttu-id="3c977-103">Cuando use LINQ para consultar colecciones no genéricas <xref:System.Collections.IEnumerable> como <xref:System.Collections.ArrayList>, debe declarar explícitamente el tipo de variable de rango para reflejar el tipo específico de los objetos de la colección.</span><span class="sxs-lookup"><span data-stu-id="3c977-103">When using LINQ to query non-generic <xref:System.Collections.IEnumerable> collections such as <xref:System.Collections.ArrayList>, you must explicitly declare the type of the range variable to reflect the specific type of the objects in the collection.</span></span> <span data-ttu-id="3c977-104">Por ejemplo, si tiene una <xref:System.Collections.ArrayList> de `Student` objetos, la [cláusula FROM](../../../language-reference/queries/from-clause.md) debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c977-104">For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [From Clause](../../../language-reference/queries/from-clause.md) should look like this:</span></span>

```vb
Dim query = From student As Student In arrList
'...
```

<span data-ttu-id="3c977-105">Al especificar el tipo de la variable de rango, se convierte cada elemento de la <xref:System.Collections.ArrayList> en un `Student`.</span><span class="sxs-lookup"><span data-stu-id="3c977-105">By specifying the type of the range variable, you are casting each item in the <xref:System.Collections.ArrayList> to a `Student`.</span></span>

<span data-ttu-id="3c977-106">El uso de una variable de rango con tipo explícito en una expresión de consulta es equivalente a llamar al método <xref:System.Linq.Enumerable.Cast%2A>.</span><span class="sxs-lookup"><span data-stu-id="3c977-106">The use of an explicitly typed range variable in a query expression is equivalent to calling the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="3c977-107"><xref:System.Linq.Enumerable.Cast%2A> genera una excepción si la conversión especificada no puede realizarse.</span><span class="sxs-lookup"><span data-stu-id="3c977-107"><xref:System.Linq.Enumerable.Cast%2A> throws an exception if the specified cast cannot be performed.</span></span> <span data-ttu-id="3c977-108"><xref:System.Linq.Enumerable.Cast%2A> y <xref:System.Linq.Enumerable.OfType%2A> son los dos métodos de operador de consulta estándar que funcionan en tipos <xref:System.Collections.IEnumerable> no genéricos.</span><span class="sxs-lookup"><span data-stu-id="3c977-108"><xref:System.Linq.Enumerable.Cast%2A> and <xref:System.Linq.Enumerable.OfType%2A> are the two Standard Query Operator methods that operate on non-generic <xref:System.Collections.IEnumerable> types.</span></span> <span data-ttu-id="3c977-109">En Visual Basic, debe llamar explícitamente al <xref:System.Linq.Enumerable.Cast%2A> método en el origen de datos para garantizar un tipo de variable de rango específico.</span><span class="sxs-lookup"><span data-stu-id="3c977-109">In Visual Basic, you must explicitly call the <xref:System.Linq.Enumerable.Cast%2A> method on the data source to ensure a specific range variable type.</span></span> <span data-ttu-id="3c977-110">Para obtener más información, vea [relaciones de tipos en operaciones de consulta (Visual Basic)](type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="3c977-110">For more information, see [Type Relationships in Query Operations (Visual Basic)](type-relationships-in-query-operations.md).</span></span>

## <a name="example"></a><span data-ttu-id="3c977-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c977-111">Example</span></span>

<span data-ttu-id="3c977-112">En el siguiente ejemplo se muestra una consulta simple sobre un <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="3c977-112">The following example shows a simple query over an <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="3c977-113">Tenga en cuenta que en este ejemplo se usan inicializadores de objeto cuando el código llama al método <xref:System.Collections.ArrayList.Add%2A>, pero esto no es un requisito.</span><span class="sxs-lookup"><span data-stu-id="3c977-113">Note that this example uses object initializers when the code calls the <xref:System.Collections.ArrayList.Add%2A> method, but this is not a requirement.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3c977-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c977-114">See also</span></span>

- [<span data-ttu-id="3c977-115">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c977-115">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
