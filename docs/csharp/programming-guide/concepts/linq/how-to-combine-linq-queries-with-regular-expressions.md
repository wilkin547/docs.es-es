---
title: "Cómo: Combinar consultas LINQ con expresiones regulares (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6b003b65-20a4-4ca2-929e-2ee3f215aecc
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0acf66885765148b668897716d6fe1f8ad0a2fcf
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-combine-linq-queries-with-regular-expressions-c"></a><span data-ttu-id="0a52a-102">Cómo: Combinar consultas LINQ con expresiones regulares (C#)</span><span class="sxs-lookup"><span data-stu-id="0a52a-102">How to: Combine LINQ Queries with Regular Expressions (C#)</span></span>
<span data-ttu-id="0a52a-103">En este ejemplo se muestra cómo usar la clase <xref:System.Text.RegularExpressions.Regex> para crear una expresión regular para coincidencias más complejas en cadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="0a52a-103">This example shows how to use the <xref:System.Text.RegularExpressions.Regex> class to create a regular expression for more complex matching in text strings.</span></span> <span data-ttu-id="0a52a-104">Con la consulta LINQ, resulta fácil filtrar por los archivos exactos que se quieren buscar con la expresión regular y dar forma a los resultados.</span><span class="sxs-lookup"><span data-stu-id="0a52a-104">The LINQ query makes it easy to filter on exactly the files that you want to search with the regular expression, and to shape the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a52a-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a52a-105">Example</span></span>  
  
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
  
 <span data-ttu-id="0a52a-106">Tenga en cuenta que también puede consultar el objeto <xref:System.Text.RegularExpressions.MatchCollection> devuelto por una búsqueda `RegEx`.</span><span class="sxs-lookup"><span data-stu-id="0a52a-106">Note that you can also query the <xref:System.Text.RegularExpressions.MatchCollection> object that is returned by a `RegEx` search.</span></span> <span data-ttu-id="0a52a-107">En este ejemplo se genera solo el valor de cada coincidencia en los resultados.</span><span class="sxs-lookup"><span data-stu-id="0a52a-107">In this example only the value of each match is produced in the results.</span></span> <span data-ttu-id="0a52a-108">Pero también es posible usar LINQ para realizar todo tipo de filtrado, ordenación y agrupación en esa colección.</span><span class="sxs-lookup"><span data-stu-id="0a52a-108">However, it is also possible to use LINQ to perform all kinds of filtering, sorting, and grouping on that collection.</span></span> <span data-ttu-id="0a52a-109">Dado que <xref:System.Text.RegularExpressions.MatchCollection> no es una colección genérica <xref:System.Collections.IEnumerable>, tendrá que indicar explícitamente el tipo de la variable de rango en la consulta.</span><span class="sxs-lookup"><span data-stu-id="0a52a-109">Because <xref:System.Text.RegularExpressions.MatchCollection> is a non-generic <xref:System.Collections.IEnumerable> collection, you have to explicitly state the type of the range variable in the query.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0a52a-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="0a52a-110">Compiling the Code</span></span>  
 <span data-ttu-id="0a52a-111">Cree un proyecto destinado a .NET Framework versión 3.5 o posterior, con una referencia a System.Core.dll y directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="0a52a-111">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a52a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a52a-112">See Also</span></span>  
 <span data-ttu-id="0a52a-113">[LINQ y cadenas (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="0a52a-113">[LINQ and Strings (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
 [<span data-ttu-id="0a52a-114">LINQ y directorios de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="0a52a-114">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)

