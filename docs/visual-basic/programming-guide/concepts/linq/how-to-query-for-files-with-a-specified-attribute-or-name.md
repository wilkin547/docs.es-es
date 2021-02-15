---
description: 'Más información acerca de cómo: buscar archivos con un nombre o atributo especificado (Visual Basic)'
title: Procedimiento para buscar archivos con un nombre o atributo especificados
ms.date: 07/20/2015
ms.assetid: b26026a3-3f43-448f-a582-259997af6be0
ms.openlocfilehash: 3eb58bf683b97c5806145395cb489f0e85c2071b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425729"
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-visual-basic"></a><span data-ttu-id="3636d-103">Cómo: buscar archivos con un nombre o atributo especificados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3636d-103">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>

<span data-ttu-id="3636d-104">En este ejemplo se muestra cómo encontrar todos los archivos con una determinada extensión de nombre de archivo (por ejemplo, ".txt") en un árbol de directorios especificado.</span><span class="sxs-lookup"><span data-stu-id="3636d-104">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="3636d-105">También se muestra cómo devolver el archivo más reciente o más antiguo del árbol por fecha de creación.</span><span class="sxs-lookup"><span data-stu-id="3636d-105">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3636d-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3636d-106">Example</span></span>  
  
```vb  
Module FindFileByExtension  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' This query will produce the full path for all .txt files  
        ' under the specified folder including subfolders.  
        ' It orders the list according to the file name.  
        Dim fileQuery = From file In fileList _  
                        Where file.Extension = ".txt" _  
                        Order By file.Name _  
                        Select file  
  
        For Each file In fileQuery  
            Console.WriteLine(file.FullName)  
        Next  
  
        ' Create and execute a new query by using  
        ' the previous query as a starting point.  
        ' fileQuery is not executed again until the  
        ' call to Last  
        Dim fileQuery2 = From file In fileQuery _  
                         Order By file.CreationTime _  
                         Select file.Name, file.CreationTime  
  
        ' Execute the query  
        Dim newestFile = fileQuery2.Last  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}", _  
                newestFile.Name, newestFile.CreationTime)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
End Module  
```  
  
## <a name="compile-the-code"></a><span data-ttu-id="3636d-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3636d-107">Compile the code</span></span>  

<span data-ttu-id="3636d-108">Cree un proyecto de aplicación de consola de Visual Basic, con una `Imports` instrucción para el espacio de nombres System. Linq.</span><span class="sxs-lookup"><span data-stu-id="3636d-108">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3636d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3636d-109">See also</span></span>

- [<span data-ttu-id="3636d-110">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3636d-110">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
- [<span data-ttu-id="3636d-111">LINQ y directorios de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3636d-111">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
