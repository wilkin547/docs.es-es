---
title: Filtrar Rellenar colecciones de objetos de varios orígenes (LINQ) (Visual Basic)
ms.date: 06/22/2018
ms.assetid: 63062a22-e6a9-42c0-b357-c7c965f58f33
ms.openlocfilehash: 65c7e2c791ba8331416ee2eee292f1e8c4888712
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836362"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-visual-basic"></a><span data-ttu-id="b52d5-102">Procedimiento Rellenar colecciones de objetos de varios orígenes (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b52d5-102">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="b52d5-103">En este ejemplo se muestra cómo combinar datos de orígenes diferentes en una secuencia de tipos nuevos.</span><span class="sxs-lookup"><span data-stu-id="b52d5-103">This example shows how to merge data from different sources into a sequence of new types.</span></span>

> [!NOTE]
> <span data-ttu-id="b52d5-104">No intente unir datos en memoria o datos del sistema de archivos con datos que todavía están en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="b52d5-104">Don't try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="b52d5-105">Dichas combinaciones entre dominios pueden producir resultados indefinidos porque hay diferentes maneras de definir las operaciones de combinación para las consultas de base de datos y otros tipos de orígenes.</span><span class="sxs-lookup"><span data-stu-id="b52d5-105">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="b52d5-106">Además, existe el riesgo de que esta operación produzca una excepción de memoria insuficiente si la cantidad de datos existente en la base de datos es considerable.</span><span class="sxs-lookup"><span data-stu-id="b52d5-106">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="b52d5-107">Para combinar datos de una base de datos con datos en memoria, primero debe llamar a `ToList` o a `ToArray` en la base de datos de consulta y, luego, debe efectuar la combinación en la colección devuelta.</span><span class="sxs-lookup"><span data-stu-id="b52d5-107">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>

## <a name="to-create-the-data-file"></a><span data-ttu-id="b52d5-108">Para crear el archivo de datos</span><span class="sxs-lookup"><span data-stu-id="b52d5-108">To create the data file</span></span>

- <span data-ttu-id="b52d5-109">Copie los archivos names.csv y scores.csv en la carpeta del proyecto, como se describe en [Cómo: Combinar contenido de archivos no similares (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span><span class="sxs-lookup"><span data-stu-id="b52d5-109">Copy the names.csv and scores.csv files into your project folder, as described in [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="b52d5-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b52d5-110">Example</span></span>

<span data-ttu-id="b52d5-111">En el ejemplo siguiente se muestra cómo usar un tipo `Student` con nombre para almacenar los datos combinados de dos colecciones de cadenas en memoria que simulan datos de hoja de cálculo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="b52d5-111">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="b52d5-112">La primera colección de cadenas representa los nombres y los identificadores de los estudiantes, mientras que la segunda colección representa el identificador de los estudiantes (en la primera columna) y cuatro notas de exámenes.</span><span class="sxs-lookup"><span data-stu-id="b52d5-112">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="b52d5-113">El identificador se usa como clave externa.</span><span class="sxs-lookup"><span data-stu-id="b52d5-113">The ID is used as the foreign key.</span></span>

```vb
Imports System.Collections.Generic
Imports System.Linq

Class Student
    Public FirstName As String
    Public LastName As String
    Public ID As Integer
    Public ExamScores As List(Of Integer)
End Class

Class PopulateCollection

    Shared Sub Main()

        ' Merge content from spreadsheets into a list of Student objects.

        ' These data files are defined in How to: Join Content from
        ' Dissimilar Files (LINQ).

        ' Each line of names.csv consists of a last name, a first name, and an
        ' ID number, separated by commas. For example, Omelchenko,Svetlana,111
        Dim names As String() = System.IO.File.ReadAllLines("../../../names.csv")

        ' Each line of scores.csv consists of an ID number and four test
        ' scores, separated by commas. For example, 111, 97, 92, 81, 60
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")

        ' The following query merges the content of two dissimilar spreadsheets
        ' based on common ID values.
        ' Multiple From clauses are used instead of a Join clause
        ' in order to store the results of scoreLine.Split.
        ' Note the dynamic creation of a list of integers for the
        ' ExamScores member. The first item is skipped in the split string
        ' because it is the student ID, not an exam score.
        Dim queryNamesScores = From nameLine In names
                          Let splitName = nameLine.Split(New Char() {","})
                          From scoreLine In scores
                          Let splitScoreLine = scoreLine.Split(New Char() {","})
                          Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
                          Select New Student() With {
                               .FirstName = splitName(1), .LastName = splitName(0), .ID = splitName(2),
                               .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                                             Select Convert.ToInt32(scoreAsText)).ToList()}

        ' Optional. Store the query results for faster access in future
        ' queries. This could be useful with very large data files.
        Dim students As List(Of Student) = queryNamesScores.ToList()

        ' Display each student's name and exam score average.
        For Each s In students
            Console.WriteLine("The average score of " & s.FirstName & " " &
                              s.LastName & " is " & s.ExamScores.Average())
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()
    End Sub
End Class

' Output:
' The average score of Svetlana Omelchenko is 82.5
' The average score of Claire O'Donnell is 72.25
' The average score of Sven Mortensen is 84.5
' The average score of Cesar Garcia is 88.25
' The average score of Debra Garcia is 67
' The average score of Fadi Fakhouri is 92.25
' The average score of Hanying Feng is 88
' The average score of Hugo Garcia is 85.75
' The average score of Lance Tucker is 81.75
' The average score of Terry Adams is 85.25
' The average score of Eugene Zabokritski is 83
' The average score of Michael Tucker is 92
```

<span data-ttu-id="b52d5-114">En el [cláusula Select](../../../../visual-basic/language-reference/queries/select-clause.md) cláusula, un inicializador de objeto se usa para crear instancias de cada nuevo `Student` objeto mediante el uso de los datos de los dos orígenes.</span><span class="sxs-lookup"><span data-stu-id="b52d5-114">In the [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>

<span data-ttu-id="b52d5-115">Si no tiene que almacenar los resultados de una consulta, los tipos anónimos pueden ser más convenientes que los tipos con nombre.</span><span class="sxs-lookup"><span data-stu-id="b52d5-115">If you don't have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="b52d5-116">Los tipos con nombre son necesarios si pasa los resultados de la consulta fuera del método en el que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="b52d5-116">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="b52d5-117">En el ejemplo siguiente se lleva a cabo la misma tarea que en el ejemplo anterior, con la diferencia de que se usan tipos anónimos en lugar de tipos con nombre:</span><span class="sxs-lookup"><span data-stu-id="b52d5-117">The following example performs the same task as the previous example, but uses anonymous types instead of named types:</span></span>

```vb
' Merge the data by using an anonymous type.
' Note the dynamic creation of a list of integers for the
' ExamScores member. We skip 1 because the first string
' in the array is the student ID, not an exam score.
Dim queryNamesScores2 =
    From nameLine In names
    Let splitName = nameLine.Split(New Char() {","})
    From scoreLine In scores
    Let splitScoreLine = scoreLine.Split(New Char() {","})
    Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
    Select New With
           {.Last = splitName(0),
            .First = splitName(1),
            .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                           Select Convert.ToInt32(scoreAsText)).ToList()}

' Display each student's name and exam score average.
For Each s In queryNamesScores2
    Console.WriteLine("The average score of " & s.First & " " &
                      s.Last & " is " & s.ExamScores.Average())
Next
```

## <a name="compiling-the-code"></a><span data-ttu-id="b52d5-118">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="b52d5-118">Compiling the code</span></span>

<span data-ttu-id="b52d5-119">Cree y compile un proyecto cuyo destino sea una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b52d5-119">Create and compile a project that targets one of the following options:</span></span>

- <span data-ttu-id="b52d5-120">Versión 3.5 de .NET Framework 5 con una referencia a System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="b52d5-120">.NET Framework version 3.5 with a reference to System.Core.dll.</span></span>
- <span data-ttu-id="b52d5-121">.NET Framework versión 4.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b52d5-121">.NET Framework version 4.0 or higher.</span></span>
- <span data-ttu-id="b52d5-122">.NET Core versión 1.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b52d5-122">.NET Core version 1.0 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="b52d5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b52d5-123">See also</span></span>

- [<span data-ttu-id="b52d5-124">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b52d5-124">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
