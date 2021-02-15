---
description: 'Más información acerca de cómo: buscar caracteres en una cadena (LINQ) (Visual Basic)'
title: Procedimiento para buscar caracteres en una cadena (LINQ)
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: bd8fabc06e88c83ae4e89079378ad67efb13c446
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425755"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="552b9-103">Cómo: buscar caracteres en una cadena (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="552b9-103">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="552b9-104">Como la clase <xref:System.String> implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> genérica, cualquier cadena puede consultarse como una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="552b9-104">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="552b9-105">Pero esto no es un uso habitual de LINQ.</span><span class="sxs-lookup"><span data-stu-id="552b9-105">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="552b9-106">Para operaciones de coincidencia de patrones complejas, use la clase <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="552b9-106">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>

## <a name="example"></a><span data-ttu-id="552b9-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="552b9-107">Example</span></span>

<span data-ttu-id="552b9-108">En el ejemplo siguiente se consulta una cadena para determinar el número de dígitos numéricos que contiene.</span><span class="sxs-lookup"><span data-stu-id="552b9-108">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="552b9-109">Tenga en cuenta que la consulta se "reutiliza" después de que se ejecute la primera vez.</span><span class="sxs-lookup"><span data-stu-id="552b9-109">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="552b9-110">Esto es posible porque la propia consulta no almacena ningún resultado real.</span><span class="sxs-lookup"><span data-stu-id="552b9-110">This is possible because the query itself does not store any actual results.</span></span>

```vb
Class QueryAString

    Shared Sub Main()

        ' A string is an IEnumerable data source.
        Dim aString As String = "ABCDE99F-J74-12-89A"

        ' Select only those characters that are numbers
        Dim stringQuery = From ch In aString
                          Where Char.IsDigit(ch)
                          Select ch
        ' Execute the query
        For Each c As Char In stringQuery
            Console.Write(c & " ")
        Next

        ' Call the Count method on the existing query.
        Dim count As Integer = stringQuery.Count()
        Console.WriteLine(System.Environment.NewLine & "Count = " & count)

        ' Select all characters before the first '-'
        Dim stringQuery2 = aString.TakeWhile(Function(c) c <> "-")

        ' Execute the second query
        For Each ch In stringQuery2
            Console.Write(ch)
        Next

        Console.WriteLine(System.Environment.NewLine & "Press any key to exit")
        Console.ReadKey()
    End Sub
End Class
' Output:
' 9 9 7 4 1 2 8 9
' Count = 8
' ABCDE99F
```

## <a name="compile-the-code"></a><span data-ttu-id="552b9-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="552b9-111">Compile the code</span></span>

<span data-ttu-id="552b9-112">Cree un proyecto de aplicación de consola de Visual Basic, con una `Imports` instrucción para el espacio de nombres System. Linq.</span><span class="sxs-lookup"><span data-stu-id="552b9-112">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="552b9-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="552b9-113">See also</span></span>

- [<span data-ttu-id="552b9-114">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="552b9-114">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="552b9-115">Cómo combinar consultas LINQ con expresiones regulares (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="552b9-115">How to combine LINQ queries with regular expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)
