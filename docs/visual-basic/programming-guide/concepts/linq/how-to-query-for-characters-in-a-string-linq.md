---
title: Procedimiento Buscar caracteres en una cadena (LINQ) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: 3f460f635c581eef5655c5707e3dd356e7986d74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819494"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="31573-102">Procedimiento Buscar caracteres en una cadena (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31573-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="31573-103">Como la clase <xref:System.String> implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> genérica, cualquier cadena puede consultarse como una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="31573-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="31573-104">Pero esto no es un uso habitual de LINQ.</span><span class="sxs-lookup"><span data-stu-id="31573-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="31573-105">Para operaciones de coincidencia de patrones complejas, use la clase <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="31573-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31573-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="31573-106">Example</span></span>  
 <span data-ttu-id="31573-107">En el ejemplo siguiente se consulta una cadena para determinar el número de dígitos numéricos que contiene.</span><span class="sxs-lookup"><span data-stu-id="31573-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="31573-108">Tenga en cuenta que la consulta se "reutiliza" después de que se ejecute la primera vez.</span><span class="sxs-lookup"><span data-stu-id="31573-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="31573-109">Esto es posible porque la propia consulta no almacena ningún resultado real.</span><span class="sxs-lookup"><span data-stu-id="31573-109">This is possible because the query itself does not store any actual results.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="31573-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="31573-110">Compiling the Code</span></span>  
 <span data-ttu-id="31573-111">Cree un proyecto que tenga como destino la versión 3.5 de .NET Framework, o bien una posterior, con una referencia a System.Core.dll y una instrucción `Imports` para el espacio de nombres System.Linq.</span><span class="sxs-lookup"><span data-stu-id="31573-111">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31573-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="31573-112">See also</span></span>

- [<span data-ttu-id="31573-113">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31573-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="31573-114">Cómo: Combinar consultas LINQ con expresiones regulares (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31573-114">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
