---
title: Procedimiento para buscar archivos duplicados en un árbol de directorios (LINQ)
ms.date: 07/20/2015
ms.assetid: 387d7c97-95dd-4a50-9761-7e9cf8ae9e6a
ms.openlocfilehash: 71c656fba3962f08733e27279ac9bfa94d957aa8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058916"
---
# <a name="how-to-query-for-duplicate-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="e6ade-102">Cómo: consultar Archivos duplicados en un árbol de directorios (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6ade-102">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="e6ade-103">A veces, los archivos que tienen el mismo nombre pueden estar en más de una carpeta.</span><span class="sxs-lookup"><span data-stu-id="e6ade-103">Sometimes files that have the same name may be located in more than one folder.</span></span> <span data-ttu-id="e6ade-104">Por ejemplo, en la carpeta de instalación de Visual Studio, hay varias carpetas que tienen un archivo readme.htm.</span><span class="sxs-lookup"><span data-stu-id="e6ade-104">For example, under the Visual Studio installation folder, several folders have a readme.htm file.</span></span> <span data-ttu-id="e6ade-105">En este ejemplo se muestra cómo buscar estos nombres de archivos duplicados en una carpeta raíz especificada.</span><span class="sxs-lookup"><span data-stu-id="e6ade-105">This example shows how to query for such duplicate file names under a specified root folder.</span></span> <span data-ttu-id="e6ade-106">En el segundo ejemplo se muestra cómo buscar archivos cuyo tamaño y fecha de creación también coinciden.</span><span class="sxs-lookup"><span data-stu-id="e6ade-106">The second example shows how to query for files whose size and creation times also match.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6ade-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6ade-107">Example</span></span>  
  
```vb  
Module QueryDuplicateFileNames  
  
    Public Sub Main()  
  
        Dim path As String = "C:\Program Files\Microsoft Visual Studio 9.0\Common7"  
        QueryDuplicates1(path)  
        ' Uncomment to run this query instead  
        ' QueryDuplicates2(path)  
  
    End Sub  
    Sub QueryDuplicates1(ByVal root As String)  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim duplicates = From aFile In dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories) _  
                                 Order By aFile.Name _  
                                 Group aFile By aFile.Name Into newGroup = Group _  
                                 Where newGroup.Count() >= 2 _  
                                 Select newGroup  
  
        ' Page the display so that the results can be read.  
        Dim trimLength = root.Length  
        PageOutput(duplicates, trimLength)  
  
    End Sub  
    Sub QueryDuplicates2(ByVal root As String)  
  
        ' This time a composite key is used. This sub finds all files  
        ' that have been copied into multiple subfolders.  
        Dim dir As New System.IO.DirectoryInfo(root)  
  
        Dim duplicates = From aFile In Dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories) _  
                                 Order By aFile.Name _  
                                 Group aFile By aFile.Name, aFile.CreationTime, aFile.Length Into newGroup = Group _  
                                 Where newGroup.Count() >= 2 _  
                                 Select newGroup  
  
        ' Page the display so that the results can be read.  
        Dim trimLength = root.Length  
        PageOutput(duplicates, trimLength)  
  
    End Sub  
    ' Pages console display for large query results. No more than one group per page.  
    ' This sub specifically works with group queries of FileInfo objects  
    ' but can be modified for any type.  
    Sub PageOutput(ByVal groupQuery, ByVal charsToSkip)  
  
        ' "3" = 1 line for extension key + 1 for "Press any key" + 1 for input cursor.  
        Dim numLines As Integer = Console.WindowHeight - 3  
        ' Flag to indicate whether there are more results to display  
        Dim goAgain As Boolean = True  
  
        For Each fg As IEnumerable(Of System.IO.FileInfo) In groupQuery  
            ' Start a new extension at the top of a page.  
            Dim currentLine As Integer = 0  
  
            Do While (currentLine < fg.Count())  
                Console.Clear()  
  
                ' Get the next page of results  
                ' No more than one filename per page  
                Dim resultPage = From file In fg _  
                                Skip currentLine Take numLines  
  
                ' Execute the query. Trim the paths in the output.  
                For Each line In resultPage  
                    Console.WriteLine(vbTab & line.FullName.Substring(charsToSkip))  
                Next  
  
                ' Advance the current position  
                currentLine = numLines + currentLine  
  
                ' Give the user a chance to break out of the loop  
                Console.WriteLine("Press any key for next page or the 'End' key to exit.")  
                Dim key As ConsoleKey = Console.ReadKey().Key  
                If key = ConsoleKey.End Then  
                    goAgain = False  
                    Exit For  
                End If  
            Loop  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="e6ade-108">En la primera consulta se usa una clave simple para determinar una coincidencia; se buscan archivos que tengan el mismo nombre, pero cuyo contenido podría ser diferente.</span><span class="sxs-lookup"><span data-stu-id="e6ade-108">The first query uses a simple key to determine a match; this finds files that have the same name but whose contents might be different.</span></span> <span data-ttu-id="e6ade-109">En la segunda consulta se usa una clave compuesta para coincidir con tres propiedades del objeto <xref:System.IO.FileInfo>.</span><span class="sxs-lookup"><span data-stu-id="e6ade-109">The second query uses a compound key to match against three properties of the <xref:System.IO.FileInfo> object.</span></span> <span data-ttu-id="e6ade-110">En esta consulta es mucho más probable que se encuentren archivos que tienen el mismo nombre y un contenido similar o idéntico.</span><span class="sxs-lookup"><span data-stu-id="e6ade-110">This query is much more likely to find files that have the same name and similar or identical content.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="e6ade-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e6ade-111">Compile the code</span></span>  

<span data-ttu-id="e6ade-112">Cree un proyecto de aplicación de consola de Visual Basic, con una `Imports` instrucción para el espacio de nombres System. Linq.</span><span class="sxs-lookup"><span data-stu-id="e6ade-112">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e6ade-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6ade-113">See also</span></span>

- [<span data-ttu-id="e6ade-114">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6ade-114">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
- [<span data-ttu-id="e6ade-115">LINQ y directorios de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6ade-115">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
