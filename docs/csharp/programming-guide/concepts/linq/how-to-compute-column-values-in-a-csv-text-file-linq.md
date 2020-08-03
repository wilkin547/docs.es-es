---
title: Procedimiento para calcular valores de columna en un archivo de texto CSV (LINQ) (C#)
description: En este ejemplo se muestra cómo realizar cálculos agregados mediante LINQ en C#, como sumas, promedios, mínimos y máximos, en las columnas de un archivo .csv.
ms.date: 07/20/2015
ms.assetid: 4747f37a-a198-4df2-8efe-5b0731e0ea27
ms.openlocfilehash: 9137779f9767c8a9531489f7894ba3e69eb1faee
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105320"
---
# <a name="how-to-compute-column-values-in-a-csv-text-file-linq-c"></a><span data-ttu-id="2f367-103">Procedimiento para calcular valores de columna en un archivo de texto CSV (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2f367-103">How to compute column values in a CSV text file (LINQ) (C#)</span></span>
<span data-ttu-id="2f367-104">En este ejemplo se muestra cómo efectuar cálculos agregados (como sumas, promedios, mínimos y máximos) en las columnas de un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="2f367-104">This example shows how to perform aggregate computations such as Sum, Average, Min, and Max on the columns of a .csv file.</span></span> <span data-ttu-id="2f367-105">Los principios de ejemplo que se muestran aquí se pueden aplicar a otros tipos de textos estructurados.</span><span class="sxs-lookup"><span data-stu-id="2f367-105">The example principles that are shown here can be applied to other types of structured text.</span></span>  
  
## <a name="to-create-the-source-file"></a><span data-ttu-id="2f367-106">Para crear el archivo de origen</span><span class="sxs-lookup"><span data-stu-id="2f367-106">To create the source file</span></span>  
  
1. <span data-ttu-id="2f367-107">Copie las líneas siguientes en un archivo llamado scores.csv y guárdelo en la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2f367-107">Copy the following lines into a file that is named scores.csv and save it in your project folder.</span></span> <span data-ttu-id="2f367-108">Imagínese que la primera columna representa un identificador de estudiante y que las columnas siguientes representan las notas de cuatro exámenes.</span><span class="sxs-lookup"><span data-stu-id="2f367-108">Assume that the first column represents a student ID, and subsequent columns represent scores from four exams.</span></span>  
  
    ```csv
    111, 97, 92, 81, 60  
    112, 75, 84, 91, 39  
    113, 88, 94, 65, 91  
    114, 97, 89, 85, 82  
    115, 35, 72, 91, 70  
    116, 99, 86, 90, 94  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    119, 68, 79, 88, 92  
    120, 99, 82, 81, 79  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    ```  
  
## <a name="example"></a><span data-ttu-id="2f367-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f367-109">Example</span></span>  
  
```csharp  
class SumColumns  
{  
    static void Main(string[] args)  
    {  
        string[] lines = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Specifies the column to compute.  
        int exam = 3;  
  
        // Spreadsheet format:  
        // Student ID    Exam#1  Exam#2  Exam#3  Exam#4  
        // 111,          97,     92,     81,     60  
  
        // Add one to exam to skip over the first column,  
        // which holds the student ID.  
        SingleColumn(lines, exam + 1);  
        Console.WriteLine();  
        MultiColumns(lines);  
  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    static void SingleColumn(IEnumerable<string> strs, int examNum)  
    {  
        Console.WriteLine("Single Column Query:");  
  
        // Parameter examNum specifies the column to
        // run the calculations on. This value could be  
        // passed in dynamically at runtime.
  
        // Variable columnQuery is an IEnumerable<int>.  
        // The following query performs two steps:  
        // 1) use Split to break each row (a string) into an array
        //    of strings,
        // 2) convert the element at position examNum to an int  
        //    and select it.  
        var columnQuery =  
            from line in strs  
            let elements = line.Split(',')  
            select Convert.ToInt32(elements[examNum]);  
  
        // Execute the query and cache the results to improve  
        // performance. This is helpful only with very large files.  
        var results = columnQuery.ToList();  
  
        // Perform aggregate calculations Average, Max, and  
        // Min on the column specified by examNum.  
        double average = results.Average();  
        int max = results.Max();  
        int min = results.Min();  
  
        Console.WriteLine("Exam #{0}: Average:{1:##.##} High Score:{2} Low Score:{3}",  
                 examNum, average, max, min);  
    }  
  
    static void MultiColumns(IEnumerable<string> strs)  
    {  
        Console.WriteLine("Multi Column Query:");  
  
        // Create a query, multiColQuery. Explicit typing is used  
        // to make clear that, when executed, multiColQuery produces
        // nested sequences. However, you get the same results by  
        // using 'var'.  
  
        // The multiColQuery query performs the following steps:  
        // 1) use Split to break each row (a string) into an array
        //    of strings,
        // 2) use Skip to skip the "Student ID" column, and store the
        //    rest of the row in scores.  
        // 3) convert each score in the current row from a string to  
        //    an int, and select that entire sequence as one row
        //    in the results.  
        IEnumerable<IEnumerable<int>> multiColQuery =  
            from line in strs  
            let elements = line.Split(',')  
            let scores = elements.Skip(1)  
            select (from str in scores  
                    select Convert.ToInt32(str));  
  
        // Execute the query and cache the results to improve  
        // performance.
        // ToArray could be used instead of ToList.  
        var results = multiColQuery.ToList();  
  
        // Find out how many columns you have in results.  
        int columnCount = results[0].Count();  
  
        // Perform aggregate calculations Average, Max, and  
        // Min on each column.
        // Perform one iteration of the loop for each column
        // of scores.  
        // You can use a for loop instead of a foreach loop
        // because you already executed the multiColQuery
        // query by calling ToList.  
        for (int column = 0; column < columnCount; column++)  
        {  
            var results2 = from row in results  
                           select row.ElementAt(column);  
            double average = results2.Average();  
            int max = results2.Max();  
            int min = results2.Min();  
  
            // Add one to column because the first exam is Exam #1,  
            // not Exam #0.  
            Console.WriteLine("Exam #{0} Average: {1:##.##} High Score: {2} Low Score: {3}",  
                          column + 1, average, max, min);  
        }  
    }  
}  
/* Output:  
    Single Column Query:  
    Exam #4: Average:76.92 High Score:94 Low Score:39  
  
    Multi Column Query:  
    Exam #1 Average: 86.08 High Score: 99 Low Score: 35  
    Exam #2 Average: 86.42 High Score: 94 Low Score: 72  
    Exam #3 Average: 84.75 High Score: 91 Low Score: 65  
    Exam #4 Average: 76.92 High Score: 94 Low Score: 39  
 */  
```  
  
 <span data-ttu-id="2f367-110">La consulta funciona usando el método <xref:System.String.Split%2A> para convertir cada línea de texto en una matriz.</span><span class="sxs-lookup"><span data-stu-id="2f367-110">The query works by using the <xref:System.String.Split%2A> method to convert each line of text into an array.</span></span> <span data-ttu-id="2f367-111">Cada elemento de matriz representa una columna.</span><span class="sxs-lookup"><span data-stu-id="2f367-111">Each array element represents a column.</span></span> <span data-ttu-id="2f367-112">Por último, el texto de cada columna se convierte en su representación numérica.</span><span class="sxs-lookup"><span data-stu-id="2f367-112">Finally, the text in each column is converted to its numeric representation.</span></span> <span data-ttu-id="2f367-113">Si el archivo es un archivo separado por tabulaciones, actualice el argumento del método `Split` a `\t`.</span><span class="sxs-lookup"><span data-stu-id="2f367-113">If your file is a tab-separated file, just update the argument in the `Split` method to `\t`.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2f367-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="2f367-114">Compiling the Code</span></span>  
 <span data-ttu-id="2f367-115">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="2f367-115">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f367-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f367-116">See also</span></span>

- [<span data-ttu-id="2f367-117">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="2f367-117">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="2f367-118">LINQ y directorios de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="2f367-118">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
