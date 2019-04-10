---
title: Filtrar Ordenar o filtrar los datos de texto por palabra o campo (LINQ) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9df137fe-335b-46e0-aecf-ea8a9eddd4e3
ms.openlocfilehash: 46c9149a7cb1809bf94162649de0a35110bbc697
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59294514"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-visual-basic"></a><span data-ttu-id="4c013-102">Filtrar Ordenar o filtrar los datos de texto por palabra o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c013-102">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="4c013-103">En el ejemplo siguiente se muestra cómo ordenar líneas de texto estructurado, como valores separados por comas, por cualquier campo de la línea.</span><span class="sxs-lookup"><span data-stu-id="4c013-103">The following example shows how to sort lines of structured text, such as comma-separated values, by any field in the line.</span></span> <span data-ttu-id="4c013-104">El campo se puede especificar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4c013-104">The field may be dynamically specified at runtime.</span></span> <span data-ttu-id="4c013-105">Supongamos que los campos de scores.csv representan el número de identificación de un alumno, seguido de una serie de cuatro calificaciones.</span><span class="sxs-lookup"><span data-stu-id="4c013-105">Assume that the fields in scores.csv represent a student's ID number, followed by a series of four test scores.</span></span>  
  
### <a name="to-create-a-file-that-contains-data"></a><span data-ttu-id="4c013-106">Para crear un archivo que contenga datos</span><span class="sxs-lookup"><span data-stu-id="4c013-106">To create a file that contains data</span></span>  
  
1. <span data-ttu-id="4c013-107">Copie los datos de scores.csv desde el tema [Cómo: Combinar contenido de archivos no similares (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) y guárdelo en la carpeta de su solución.</span><span class="sxs-lookup"><span data-stu-id="4c013-107">Copy the scores.csv data from the topic [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) and save it to your solution folder.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c013-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c013-108">Example</span></span>  
  
```vb  
Class SortLines  
  
    Shared Sub Main()  
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")  
  
        ' Change this to any value from 0 to 4  
        Dim sortField As Integer = 1  
  
        Console.WriteLine("Sorted highest to lowest by field " & sortField)  
  
        ' Demonstrates how to return query from a method.  
        ' The query is executed here.  
        For Each str As String In SortQuery(scores, sortField)  
            Console.WriteLine(str)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    Shared Function SortQuery(  
        ByVal source As IEnumerable(Of String),   
        ByVal num As Integer) As IEnumerable(Of String)  
  
        Dim scoreQuery = From line In source   
                         Let fields = line.Split(New Char() {","})   
                         Order By fields(num) Descending   
                         Select line  
  
        Return scoreQuery  
    End Function  
End Class  
' Output:  
' Sorted highest to lowest by field 1  
' 116, 99, 86, 90, 94  
' 120, 99, 82, 81, 79  
' 111, 97, 92, 81, 60  
' 114, 97, 89, 85, 82  
' 121, 96, 85, 91, 60  
' 122, 94, 92, 91, 91  
' 117, 93, 92, 80, 87  
' 118, 92, 90, 83, 78  
' 113, 88, 94, 65, 91  
' 112, 75, 84, 91, 39  
' 119, 68, 79, 88, 92  
' 115, 35, 72, 91, 70  
```  
  
 <span data-ttu-id="4c013-109">En este ejemplo también muestra cómo devolver una variable de consulta de una función.</span><span class="sxs-lookup"><span data-stu-id="4c013-109">This example also demonstrates how to return a query variable from a Function.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c013-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4c013-110">Compiling the Code</span></span>  
 <span data-ttu-id="4c013-111">Cree un proyecto que tenga como destino la versión 3.5 de .NET Framework, o bien una posterior, con una referencia a System.Core.dll y una instrucción `Imports` para el espacio de nombres System.Linq.</span><span class="sxs-lookup"><span data-stu-id="4c013-111">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c013-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c013-112">See also</span></span>

- [<span data-ttu-id="4c013-113">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c013-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
