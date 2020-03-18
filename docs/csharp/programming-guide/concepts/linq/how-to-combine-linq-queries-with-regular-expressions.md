---
title: Procedimiento para combinar consultas LINQ con expresiones regulares (C#)
ms.date: 07/20/2015
ms.assetid: 6b003b65-20a4-4ca2-929e-2ee3f215aecc
ms.openlocfilehash: 104e63adb9c07a75077b92654afd791b6c82d8de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169434"
---
# <a name="how-to-combine-linq-queries-with-regular-expressions-c"></a><span data-ttu-id="3aa78-102">Procedimiento para combinar consultas LINQ con expresiones regulares (C#)</span><span class="sxs-lookup"><span data-stu-id="3aa78-102">How to combine LINQ queries with regular expressions (C#)</span></span>
<span data-ttu-id="3aa78-103">En este ejemplo se muestra cómo usar la clase <xref:System.Text.RegularExpressions.Regex> para crear una expresión regular para coincidencias más complejas en cadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="3aa78-103">This example shows how to use the <xref:System.Text.RegularExpressions.Regex> class to create a regular expression for more complex matching in text strings.</span></span> <span data-ttu-id="3aa78-104">Con la consulta LINQ, resulta fácil filtrar por los archivos exactos que se quieren buscar con la expresión regular y dar forma a los resultados.</span><span class="sxs-lookup"><span data-stu-id="3aa78-104">The LINQ query makes it easy to filter on exactly the files that you want to search with the regular expression, and to shape the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3aa78-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3aa78-105">Example</span></span>  
  
```csharp  
class QueryWithRegEx  
{  
    public static void Main()  
    {  
        // Modify this path as necessary so that it accesses your version of Visual Studio.  
        string startFolder = @"C:\Program Files (x86)\Microsoft Visual Studio 14.0\";  
        // One of the following paths may be more appropriate on your computer.  
        //string startFolder = @"C:\Program Files (x86)\Microsoft Visual Studio\2017\";  
  
        // Take a snapshot of the file system.  
        IEnumerable<System.IO.FileInfo> fileList = GetFiles(startFolder);  
  
        // Create the regular expression to find all things "Visual".  
        System.Text.RegularExpressions.Regex searchTerm =  
            new System.Text.RegularExpressions.Regex(@"Visual (Basic|C#|C\+\+|Studio)");  
  
        // Search the contents of each .htm file.  
        // Remove the where clause to find even more matchedValues!  
        // This query produces a list of files where a match  
        // was found, and a list of the matchedValues in that file.  
        // Note: Explicit typing of "Match" in select clause.  
        // This is required because MatchCollection is not a
        // generic IEnumerable collection.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = System.IO.File.ReadAllText(file.FullName)  
            let matches = searchTerm.Matches(fileText)  
            where matches.Count > 0  
            select new  
            {  
                name = file.FullName,  
                matchedValues = from System.Text.RegularExpressions.Match match in matches  
                                select match.Value  
            };  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm.ToString());  
  
        foreach (var v in queryMatchingFiles)  
        {  
            // Trim the path a bit, then write
            // the file name in which a match was found.  
            string s = v.name.Substring(startFolder.Length - 1);  
            Console.WriteLine(s);  
  
            // For this file, write out all the matching strings  
            foreach (var v2 in v.matchedValues)  
            {  
                Console.WriteLine("  " + v2);  
            }  
        }  
  
        // Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // This method assumes that the application has discovery
    // permissions for all folders under the specified path.  
    static IEnumerable<System.IO.FileInfo> GetFiles(string path)  
    {  
        if (!System.IO.Directory.Exists(path))  
            throw new System.IO.DirectoryNotFoundException();  
  
        string[] fileNames = null;  
        List<System.IO.FileInfo> files = new List<System.IO.FileInfo>();  
  
        fileNames = System.IO.Directory.GetFiles(path, "*.*", System.IO.SearchOption.AllDirectories);  
        foreach (string name in fileNames)  
        {  
            files.Add(new System.IO.FileInfo(name));  
        }  
        return files;  
    }  
}  
```  
  
 <span data-ttu-id="3aa78-106">Tenga en cuenta que también puede consultar el objeto <xref:System.Text.RegularExpressions.MatchCollection> devuelto por una búsqueda `RegEx`.</span><span class="sxs-lookup"><span data-stu-id="3aa78-106">Note that you can also query the <xref:System.Text.RegularExpressions.MatchCollection> object that is returned by a `RegEx` search.</span></span> <span data-ttu-id="3aa78-107">En este ejemplo se genera solo el valor de cada coincidencia en los resultados.</span><span class="sxs-lookup"><span data-stu-id="3aa78-107">In this example only the value of each match is produced in the results.</span></span> <span data-ttu-id="3aa78-108">Pero también es posible usar LINQ para realizar todo tipo de filtrado, ordenación y agrupación en esa colección.</span><span class="sxs-lookup"><span data-stu-id="3aa78-108">However, it is also possible to use LINQ to perform all kinds of filtering, sorting, and grouping on that collection.</span></span> <span data-ttu-id="3aa78-109">Dado que <xref:System.Text.RegularExpressions.MatchCollection> no es una colección genérica <xref:System.Collections.IEnumerable>, tendrá que indicar explícitamente el tipo de la variable de rango en la consulta.</span><span class="sxs-lookup"><span data-stu-id="3aa78-109">Because <xref:System.Text.RegularExpressions.MatchCollection> is a non-generic <xref:System.Collections.IEnumerable> collection, you have to explicitly state the type of the range variable in the query.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3aa78-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3aa78-110">Compiling the Code</span></span>  
 <span data-ttu-id="3aa78-111">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="3aa78-111">Create a C# console application project with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa78-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3aa78-112">See also</span></span>

- [<span data-ttu-id="3aa78-113">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="3aa78-113">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- <span data-ttu-id="3aa78-114">[LINQ and File Directories (C#)](./linq-and-file-directories.md) (LINQ y directorios de archivos [C#])</span><span class="sxs-lookup"><span data-stu-id="3aa78-114">[LINQ and File Directories (C#)](./linq-and-file-directories.md)</span></span>
