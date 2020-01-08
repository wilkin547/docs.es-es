---
title: 'Cómo: Buscar caracteres en una cadena (LINQ)'
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: 2f306a488610aaa5775210eba3d7312b092545a7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345521"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="50500-102">Cómo: buscar caracteres en una cadena (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50500-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="50500-103">Como la clase <xref:System.String> implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> genérica, cualquier cadena puede consultarse como una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="50500-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="50500-104">Pero esto no es un uso habitual de LINQ.</span><span class="sxs-lookup"><span data-stu-id="50500-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="50500-105">Para operaciones de coincidencia de patrones complejas, use la clase <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="50500-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>

## <a name="example"></a><span data-ttu-id="50500-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50500-106">Example</span></span>

<span data-ttu-id="50500-107">En el ejemplo siguiente se consulta una cadena para determinar el número de dígitos numéricos que contiene.</span><span class="sxs-lookup"><span data-stu-id="50500-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="50500-108">Tenga en cuenta que la consulta se "reutiliza" después de que se ejecute la primera vez.</span><span class="sxs-lookup"><span data-stu-id="50500-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="50500-109">Esto es posible porque la propia consulta no almacena ningún resultado real.</span><span class="sxs-lookup"><span data-stu-id="50500-109">This is possible because the query itself does not store any actual results.</span></span>

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

## <a name="compile-the-code"></a><span data-ttu-id="50500-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="50500-110">Compile the code</span></span>

<span data-ttu-id="50500-111">Cree un proyecto de aplicación de consola de Visual Basic, con una instrucción de `Imports` para el espacio de nombres System. Linq.</span><span class="sxs-lookup"><span data-stu-id="50500-111">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="50500-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="50500-112">See also</span></span>

- [<span data-ttu-id="50500-113">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50500-113">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="50500-114">Cómo combinar consultas LINQ con expresiones regulares (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50500-114">How to combine LINQ queries with regular expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)
