---
title: Procedimiento para rellenar colecciones de objetos de varios orígenes (LINQ) (C#)
ms.date: 06/12/2018
ms.assetid: 8ad7d480-b46c-4ccc-8c57-76f2d04ccc6d
ms.openlocfilehash: 3d841e5ca25afde94674af0fedc9a824c382be5b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345753"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-c"></a><span data-ttu-id="3f048-102">Procedimiento para rellenar colecciones de objetos de varios orígenes (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="3f048-102">How to populate object collections from multiple sources (LINQ) (C#)</span></span>

<span data-ttu-id="3f048-103">En este ejemplo se muestra cómo combinar datos de orígenes diferentes en una secuencia de tipos nuevos.</span><span class="sxs-lookup"><span data-stu-id="3f048-103">This example shows how to merge data from different sources into a sequence of new types.</span></span>

> [!NOTE]
> <span data-ttu-id="3f048-104">No intente unir datos en memoria o datos del sistema de archivos con datos que todavía están en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="3f048-104">Don't try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="3f048-105">Dichas combinaciones entre dominios pueden producir resultados indefinidos porque hay diferentes maneras de definir las operaciones de combinación para las consultas de base de datos y otros tipos de orígenes.</span><span class="sxs-lookup"><span data-stu-id="3f048-105">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="3f048-106">Además, existe el riesgo de que esta operación produzca una excepción de memoria insuficiente si la cantidad de datos existente en la base de datos es considerable.</span><span class="sxs-lookup"><span data-stu-id="3f048-106">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="3f048-107">Para combinar datos de una base de datos con datos en memoria, primero debe llamar a `ToList` o a `ToArray` en la base de datos de consulta y, luego, debe efectuar la combinación en la colección devuelta.</span><span class="sxs-lookup"><span data-stu-id="3f048-107">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>

## <a name="to-create-the-data-file"></a><span data-ttu-id="3f048-108">Para crear el archivo de datos</span><span class="sxs-lookup"><span data-stu-id="3f048-108">To create the data file</span></span>

<span data-ttu-id="3f048-109">Copie los archivos names.csv y scores.csv en la carpeta del proyecto, como se describe en [Procedimiento para combinar contenido de archivos no similares (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md).</span><span class="sxs-lookup"><span data-stu-id="3f048-109">Copy the names.csv and scores.csv files into your project folder, as described in [How to join content from dissimilar files (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="3f048-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f048-110">Example</span></span>

<span data-ttu-id="3f048-111">En el ejemplo siguiente se muestra cómo usar un tipo `Student` con nombre para almacenar los datos combinados de dos colecciones de cadenas en memoria que simulan datos de hoja de cálculo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="3f048-111">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="3f048-112">La primera colección de cadenas representa los nombres y los identificadores de los estudiantes, mientras que la segunda colección representa el identificador de los estudiantes (en la primera columna) y cuatro notas de exámenes.</span><span class="sxs-lookup"><span data-stu-id="3f048-112">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="3f048-113">El identificador se usa como clave externa.</span><span class="sxs-lookup"><span data-stu-id="3f048-113">The ID is used as the foreign key.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

class Student
{
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public int ID { get; set; }
    public List<int> ExamScores { get; set; }
}

class PopulateCollection
{
    static void Main()
    {
        // These data files are defined in How to join content from
        // dissimilar files (LINQ).

        // Each line of names.csv consists of a last name, a first name, and an
        // ID number, separated by commas. For example, Omelchenko,Svetlana,111
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");

        // Each line of scores.csv consists of an ID number and four test
        // scores, separated by commas. For example, 111, 97, 92, 81, 60
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");

        // Merge the data sources using a named type.
        // var could be used instead of an explicit type. Note the dynamic
        // creation of a list of ints for the ExamScores member. The first item
        // is skipped in the split string because it is the student ID,
        // not an exam score.
        IEnumerable<Student> queryNamesScores =
            from nameLine in names
            let splitName = nameLine.Split(',')
            from scoreLine in scores
            let splitScoreLine = scoreLine.Split(',')
            where Convert.ToInt32(splitName[2]) == Convert.ToInt32(splitScoreLine[0])
            select new Student()
            {
                FirstName = splitName[0],
                LastName = splitName[1],
                ID = Convert.ToInt32(splitName[2]),
                ExamScores = (from scoreAsText in splitScoreLine.Skip(1)
                              select Convert.ToInt32(scoreAsText)).
                              ToList()
            };

        // Optional. Store the newly created student objects in memory
        // for faster access in future queries. This could be useful with
        // very large data files.
        List<Student> students = queryNamesScores.ToList();

        // Display each student's name and exam score average.
        foreach (var student in students)
        {
            Console.WriteLine("The average score of {0} {1} is {2}.",
                student.FirstName, student.LastName,
                student.ExamScores.Average());
        }

        //Keep console window open in debug mode
        Console.WriteLine("Press any key to exit.");
        Console.ReadKey();
    }
}
/* Output:
    The average score of Omelchenko Svetlana is 82.5.
    The average score of O'Donnell Claire is 72.25.
    The average score of Mortensen Sven is 84.5.
    The average score of Garcia Cesar is 88.25.
    The average score of Garcia Debra is 67.
    The average score of Fakhouri Fadi is 92.25.
    The average score of Feng Hanying is 88.
    The average score of Garcia Hugo is 85.75.
    The average score of Tucker Lance is 81.75.
    The average score of Adams Terry is 85.25.
    The average score of Zabokritski Eugene is 83.
    The average score of Tucker Michael is 92.
 */
```

<span data-ttu-id="3f048-114">En la cláusula [select](../../../language-reference/keywords/select-clause.md) se usa un inicializador de objeto para crear una instancia de cada objeto `Student` nuevo usando los datos de los dos orígenes.</span><span class="sxs-lookup"><span data-stu-id="3f048-114">In the [select](../../../language-reference/keywords/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>

<span data-ttu-id="3f048-115">Si no tiene que almacenar los resultados de una consulta, los tipos anónimos pueden ser más convenientes que los tipos con nombre.</span><span class="sxs-lookup"><span data-stu-id="3f048-115">If you don't have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="3f048-116">Los tipos con nombre son necesarios si pasa los resultados de la consulta fuera del método en el que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="3f048-116">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="3f048-117">En el ejemplo siguiente se ejecuta la misma tarea que en el ejemplo anterior, con la diferencia de que se usan tipos anónimos en lugar de tipos con nombre:</span><span class="sxs-lookup"><span data-stu-id="3f048-117">The following example executes the same task as the previous example, but uses anonymous types instead of named types:</span></span>

```csharp
// Merge the data sources by using an anonymous type.
// Note the dynamic creation of a list of ints for the
// ExamScores member. We skip 1 because the first string
// in the array is the student ID, not an exam score.
var queryNamesScores2 =
    from nameLine in names
    let splitName = nameLine.Split(',')
    from scoreLine in scores
    let splitScoreLine = scoreLine.Split(',')
    where Convert.ToInt32(splitName[2]) == Convert.ToInt32(splitScoreLine[0])
    select new
    {
        First = splitName[0],
        Last = splitName[1],
        ExamScores = (from scoreAsText in splitScoreLine.Skip(1)
                      select Convert.ToInt32(scoreAsText))
                      .ToList()
    };

// Display each student's name and exam score average.
foreach (var student in queryNamesScores2)
{
    Console.WriteLine("The average score of {0} {1} is {2}.",
        student.First, student.Last, student.ExamScores.Average());
}
```

## <a name="see-also"></a><span data-ttu-id="3f048-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f048-118">See also</span></span>

- [<span data-ttu-id="3f048-119">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="3f048-119">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="3f048-120">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="3f048-120">Object and Collection Initializers</span></span>](../../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="3f048-121">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="3f048-121">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
