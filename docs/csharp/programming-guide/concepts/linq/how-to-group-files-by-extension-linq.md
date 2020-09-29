---
title: Procedimiento para agrupar archivos por extensión (LINQ) (C#)
description: Aprenda a usar LINQ para realizar operaciones avanzadas de agrupación y ordenación en listas de archivos o carpetas en C#. En el ejemplo se muestra cómo paginar la salida en la consola.
ms.date: 07/20/2015
ms.assetid: 21a98320-a5a1-4981-82d8-6a637e7d9018
ms.openlocfilehash: c17328980c20dd6ec32e8d0ce176081122443344
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159051"
---
# <a name="how-to-group-files-by-extension-linq-c"></a><span data-ttu-id="14b50-104">Procedimiento para agrupar archivos por extensión (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="14b50-104">How to group files by extension (LINQ) (C#)</span></span>

<span data-ttu-id="14b50-105">En este ejemplo se muestra cómo se puede usar LINQ para efectuar operaciones avanzadas de agrupación y ordenación en listas de archivos o de carpetas.</span><span class="sxs-lookup"><span data-stu-id="14b50-105">This example shows how LINQ can be used to perform advanced grouping and sorting operations on lists of files or folders.</span></span> <span data-ttu-id="14b50-106">También muestra cómo paginar la salida en la ventana de consola mediante los métodos <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Take%2A>.</span><span class="sxs-lookup"><span data-stu-id="14b50-106">It also shows how to page output in the console window by using the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14b50-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14b50-107">Example</span></span>  

 <span data-ttu-id="14b50-108">En la siguiente consulta se muestra cómo agrupar el contenido de un árbol de directorio especificado por la extensión de nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="14b50-108">The following query shows how to group the contents of a specified directory tree by the file name extension.</span></span>  
  
```csharp  
class GroupByExtension  
{  
    // This query will sort all the files under the specified folder  
    //  and subfolder into groups keyed by the file extension.  
    private static void Main()  
    {  
        // Take a snapshot of the file system.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\Common7";  
  
        // Used in WriteLine to trim output lines.  
        int trimLength = startFolder.Length;  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        // Create the query.  
        var queryGroupByExt =  
            from file in fileList  
            group file by file.Extension.ToLower() into fileGroup  
            orderby fileGroup.Key  
            select fileGroup;  
  
        // Display one group at a time. If the number of
        // entries is greater than the number of lines  
        // in the console window, then page the output.  
        PageOutput(trimLength, queryGroupByExt);  
    }  
  
    // This method specifically handles group queries of FileInfo objects with string keys.  
    // It can be modified to work for any long listings of data. Note that explicit typing  
    // must be used in method signatures. The groupbyExtList parameter is a query that produces  
    // groups of FileInfo objects with string keys.  
    private static void PageOutput(int rootLength,  
                                    IEnumerable<System.Linq.IGrouping<string, System.IO.FileInfo>> groupByExtList)  
    {  
        // Flag to break out of paging loop.  
        bool goAgain = true;  
  
        // "3" = 1 line for extension + 1 for "Press any key" + 1 for input cursor.  
        int numLines = Console.WindowHeight - 3;  
  
        // Iterate through the outer collection of groups.  
        foreach (var filegroup in groupByExtList)  
        {  
            // Start a new extension at the top of a page.  
            int currentLine = 0;  
  
            // Output only as many lines of the current group as will fit in the window.  
            do  
            {  
                Console.Clear();  
                Console.WriteLine(filegroup.Key == String.Empty ? "[none]" : filegroup.Key);  
  
                // Get 'numLines' number of items starting at number 'currentLine'.  
                var resultPage = filegroup.Skip(currentLine).Take(numLines);  
  
                //Execute the resultPage query  
                foreach (var f in resultPage)  
                {  
                    Console.WriteLine("\t{0}", f.FullName.Substring(rootLength));  
                }  
  
                // Increment the line counter.  
                currentLine += numLines;  
  
                // Give the user a chance to escape.  
                Console.WriteLine("Press any key to continue or the 'End' key to break...");  
                ConsoleKey key = Console.ReadKey().Key;  
                if (key == ConsoleKey.End)  
                {  
                    goAgain = false;  
                    break;  
                }  
            } while (currentLine < filegroup.Count());  
  
            if (goAgain == false)  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="14b50-109">La salida de este programa puede ser larga, dependiendo de los detalles del sistema de archivos local y de la configuración de `startFolder`.</span><span class="sxs-lookup"><span data-stu-id="14b50-109">The output from this program can be long, depending on the details of the local file system and what the `startFolder` is set to.</span></span> <span data-ttu-id="14b50-110">Para habilitar la visualización de todos los resultados, en este ejemplo se muestra cómo paginar los resultados.</span><span class="sxs-lookup"><span data-stu-id="14b50-110">To enable viewing of all results, this example shows how to page through results.</span></span> <span data-ttu-id="14b50-111">Se pueden aplicar las mismas técnicas a las aplicaciones web y Windows.</span><span class="sxs-lookup"><span data-stu-id="14b50-111">The same techniques can be applied to Windows and Web applications.</span></span> <span data-ttu-id="14b50-112">Observe que, como el código pagina los elementos en un grupo, se necesita un bucle `foreach` anidado.</span><span class="sxs-lookup"><span data-stu-id="14b50-112">Notice that because the code pages the items in a group, a nested `foreach` loop is required.</span></span> <span data-ttu-id="14b50-113">También hay alguna lógica adicional para calcular la posición actual en la lista y para permitir que el usuario detenga la paginación y salga del programa.</span><span class="sxs-lookup"><span data-stu-id="14b50-113">There is also some additional logic to compute the current position in the list, and to enable the user to stop paging and exit the program.</span></span> <span data-ttu-id="14b50-114">En este caso en concreto, la consulta de paginación se ejecuta en los resultados almacenados en caché de la consulta original.</span><span class="sxs-lookup"><span data-stu-id="14b50-114">In this particular case, the paging query is run against the cached results from the original query.</span></span> <span data-ttu-id="14b50-115">En otros contextos, como en LINQ to SQL, este almacenamiento en caché no es necesario.</span><span class="sxs-lookup"><span data-stu-id="14b50-115">In other contexts, such as LINQ to SQL, such caching is not required.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="14b50-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="14b50-116">Compiling the Code</span></span>  

 <span data-ttu-id="14b50-117">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="14b50-117">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b50-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="14b50-118">See also</span></span>

- [<span data-ttu-id="14b50-119">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="14b50-119">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="14b50-120">LINQ y directorios de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="14b50-120">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
