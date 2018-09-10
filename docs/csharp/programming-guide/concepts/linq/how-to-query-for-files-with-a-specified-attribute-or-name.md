---
title: Buscar archivos con un nombre o atributo especificados (C#)
ms.date: 07/20/2015
ms.assetid: 560e3879-b0b3-4549-ad02-0a53aff2f83c
ms.openlocfilehash: 2b353ec17284235a97135003bc07f7224082cb4a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500912"
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-c"></a><span data-ttu-id="9c817-102">Buscar archivos con un nombre o atributo especificados (C#)</span><span class="sxs-lookup"><span data-stu-id="9c817-102">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>
<span data-ttu-id="9c817-103">En este ejemplo se muestra cómo encontrar todos los archivos con una determinada extensión de nombre de archivo (por ejemplo, ".txt") en un árbol de directorios especificado.</span><span class="sxs-lookup"><span data-stu-id="9c817-103">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="9c817-104">También se muestra cómo devolver el archivo más reciente o más antiguo del árbol por fecha de creación.</span><span class="sxs-lookup"><span data-stu-id="9c817-104">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c817-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c817-105">Example</span></span>  
  
```csharp  
class FindFileByExtension  
{  
    // This query will produce the full path for all .txt files  
    // under the specified folder including subfolders.  
    // It orders the list according to the file name.  
    static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Create the query  
        IEnumerable<System.IO.FileInfo> fileQuery =  
            from file in fileList  
            where file.Extension == ".txt"  
            orderby file.Name  
            select file;  
  
        //Execute the query. This might write out a lot of files!  
        foreach (System.IO.FileInfo fi in fileQuery)  
        {  
            Console.WriteLine(fi.FullName);  
        }  
  
        // Create and execute a new query by using the previous   
        // query as a starting point. fileQuery is not   
        // executed again until the call to Last()  
        var newestFile =  
            (from file in fileQuery  
             orderby file.CreationTime  
             select new { file.FullName, file.CreationTime })  
            .Last();  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}",  
            newestFile.FullName, newestFile.CreationTime);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9c817-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9c817-106">Compiling the Code</span></span>  
 <span data-ttu-id="9c817-107">Cree un proyecto destinado a .NET Framework versión 3.5 o posterior, con una referencia a System.Core.dll y directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="9c817-107">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to   System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c817-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c817-108">See Also</span></span>

- [<span data-ttu-id="9c817-109">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="9c817-109">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
- [<span data-ttu-id="9c817-110">LINQ y directorios de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="9c817-110">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
