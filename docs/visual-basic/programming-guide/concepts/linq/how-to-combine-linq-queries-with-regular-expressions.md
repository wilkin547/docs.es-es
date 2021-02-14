---
description: 'Más información sobre: Cómo combinar consultas LINQ con expresiones regulares (Visual Basic)'
title: 'Procedimiento para: Combinar consultas LINQ con expresiones regulares'
ms.date: 07/20/2015
ms.assetid: 3da1bd10-b0d8-4d5b-a637-966891c13592
ms.openlocfilehash: a2fd06f76c5c278ad1a67f3822151e5f73a2630e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424519"
---
# <a name="how-to-combine-linq-queries-with-regular-expressions-visual-basic"></a><span data-ttu-id="ea46f-103">Cómo combinar consultas LINQ con expresiones regulares (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea46f-103">How to combine LINQ queries with regular expressions (Visual Basic)</span></span>

<span data-ttu-id="ea46f-104">En este ejemplo se muestra cómo usar la clase <xref:System.Text.RegularExpressions.Regex> para crear una expresión regular para coincidencias más complejas en cadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="ea46f-104">This example shows how to use the <xref:System.Text.RegularExpressions.Regex> class to create a regular expression for more complex matching in text strings.</span></span> <span data-ttu-id="ea46f-105">Con la consulta LINQ, resulta fácil filtrar por los archivos exactos que se quieren buscar con la expresión regular y dar forma a los resultados.</span><span class="sxs-lookup"><span data-stu-id="ea46f-105">The LINQ query makes it easy to filter on exactly the files that you want to search with the regular expression, and to shape the results.</span></span>

## <a name="example"></a><span data-ttu-id="ea46f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea46f-106">Example</span></span>

```vb
Imports System.IO
Imports System.Text.RegularExpressions

Class LinqRegExVB

    Shared Sub Main()

        ' Root folder to query, along with all subfolders.
        ' Modify this path as necessary so that it accesses your Visual Studio folder.
        Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio 14.0\"
        ' One of the following paths may be more appropriate on your computer.
        'Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio\2017\"

        ' Take a snapshot of the file system.
        Dim fileList As IEnumerable(Of FileInfo) = GetFiles(startFolder)

        ' Create a regular expression to find all things "Visual".
        Dim searchTerm As New Regex("Visual (Basic|C#|C\+\+|Studio)")

        ' Search the contents of each .htm file.
        ' Remove the where clause to find even more matches!
        ' This query produces a list of files where a match
        ' was found, and a list of the matches in that file.
        ' Note: Explicit typing of "Match" in select clause.
        ' This is required because MatchCollection is not a
        ' generic IEnumerable collection.
        Dim queryMatchingFiles = From afile In fileList
                                Where afile.Extension = ".htm"
                                Let fileText = File.ReadAllText(afile.FullName)
                                Let matches = searchTerm.Matches(fileText)
                                Where (matches.Count > 0)
                                Select Name = afile.FullName,
                                       Matches = From match As Match In matches
                                                 Select match.Value

        ' Execute the query.
        Console.WriteLine("The term " & searchTerm.ToString() & " was found in:")

        For Each fileMatches In queryMatchingFiles
            ' Trim the path a bit, then write
            ' the file name in which a match was found.
            Dim s = fileMatches.Name.Substring(startFolder.Length - 1)
            Console.WriteLine(s)

            ' For this file, write out all the matching strings
            For Each match In fileMatches.Matches
                Console.WriteLine("  " + match)
            Next
        Next

        ' Keep the console window open in debug mode
        Console.WriteLine("Press any key to exit")
        Console.ReadKey()
    End Sub

    ' Function to retrieve a list of files. Note that this is a copy
    ' of the file information.
    Shared Function GetFiles(root As String) As IEnumerable(Of FileInfo)
        Return From file In My.Computer.FileSystem.GetFiles(
                   root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")
               Select New FileInfo(file)
    End Function

End Class
```

<span data-ttu-id="ea46f-107">Tenga en cuenta que también puede consultar el objeto <xref:System.Text.RegularExpressions.MatchCollection> devuelto por una búsqueda `RegEx`.</span><span class="sxs-lookup"><span data-stu-id="ea46f-107">Note that you can also query the <xref:System.Text.RegularExpressions.MatchCollection> object that is returned by a `RegEx` search.</span></span> <span data-ttu-id="ea46f-108">En este ejemplo se genera solo el valor de cada coincidencia en los resultados.</span><span class="sxs-lookup"><span data-stu-id="ea46f-108">In this example only the value of each match is produced in the results.</span></span> <span data-ttu-id="ea46f-109">Pero también es posible usar LINQ para realizar todo tipo de filtrado, ordenación y agrupación en esa colección.</span><span class="sxs-lookup"><span data-stu-id="ea46f-109">However, it is also possible to use LINQ to perform all kinds of filtering, sorting, and grouping on that collection.</span></span> <span data-ttu-id="ea46f-110">Dado que <xref:System.Text.RegularExpressions.MatchCollection> no es una colección genérica <xref:System.Collections.IEnumerable>, tendrá que indicar explícitamente el tipo de la variable de rango en la consulta.</span><span class="sxs-lookup"><span data-stu-id="ea46f-110">Because <xref:System.Text.RegularExpressions.MatchCollection> is a non-generic <xref:System.Collections.IEnumerable> collection, you have to explicitly state the type of the range variable in the query.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="ea46f-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ea46f-111">Compile the code</span></span>

<span data-ttu-id="ea46f-112">Cree un proyecto de aplicación de consola de Visual Basic, copie y pegue el ejemplo de código y ajuste el valor del objeto startup en las propiedades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ea46f-112">Create a Visual Basic console application project, copy and paste the code sample, and adjust the Startup object value in the project properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea46f-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea46f-113">See also</span></span>

- [<span data-ttu-id="ea46f-114">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea46f-114">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="ea46f-115">LINQ y directorios de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea46f-115">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
