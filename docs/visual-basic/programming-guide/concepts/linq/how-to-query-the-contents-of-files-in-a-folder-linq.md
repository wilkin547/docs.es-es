---
title: Procedimiento Consultar el contenido de archivos en una carpeta (LINQ) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: edacbcd3-f3e4-4429-a8be-28a58dc0dd70
ms.openlocfilehash: 6bebb4bd7444516c51551a5c56171d08f9d0ef2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566935"
---
# <a name="how-to-query-the-contents-of-files-in-a-folder-linq-visual-basic"></a><span data-ttu-id="cdcc8-102">Procedimiento Consultar el contenido de archivos en una carpeta (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cdcc8-102">How to: Query the Contents of Files in a Folder (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="cdcc8-103">En este ejemplo se muestra cómo consultar todos los archivos en un árbol de directorios especificado, abrir cada archivo e inspeccionar su contenido.</span><span class="sxs-lookup"><span data-stu-id="cdcc8-103">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="cdcc8-104">Este tipo de técnica puede usarse para crear índices o índices inversos del contenido de un árbol de directorios.</span><span class="sxs-lookup"><span data-stu-id="cdcc8-104">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="cdcc8-105">En este ejemplo, se realiza una búsqueda de cadena simple.</span><span class="sxs-lookup"><span data-stu-id="cdcc8-105">A simple string search is performed in this example.</span></span> <span data-ttu-id="cdcc8-106">Pero los tipos más complejos de coincidencia de patrones se pueden realizar con una expresión regular.</span><span class="sxs-lookup"><span data-stu-id="cdcc8-106">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="cdcc8-107">Para obtener más información, vea [Cómo: Combinar consultas LINQ con expresiones regulares (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="cdcc8-107">For more information, see [How to: Combine LINQ Queries with Regular Expressions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdcc8-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cdcc8-108">Example</span></span>  
  
```vb  
Module Module1  
    'QueryContents  
    Public Sub Main()  
  
        ' Modify this path as necessary.  
        Dim startFolder = "c:\program files\Microsoft Visual Studio 9.0\VB\"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(startFolder)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        Dim searchTerm = "Visual Studio"  
  
        ' Search the contents of each file.  
        ' A regular expression created with the RegEx class  
        ' could be used instead of the Contains method.  
        Dim queryMatchingFiles = From file In fileList _  
                                 Where file.Extension = ".htm" _  
                                 Let fileText = GetFileText(file.FullName) _  
                                 Where fileText.Contains(searchTerm) _  
                                 Select file.FullName  
  
        Console.WriteLine("The term " & searchTerm & " was found in:")  
  
        ' Execute the query.  
        For Each filename In queryMatchingFiles  
            Console.WriteLine(filename)  
        Next  
  
        ' Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit")  
        Console.ReadKey()  
  
    End Sub  
  
    ' Read the contents of the file. This is done in a separate  
    ' function in order to handle potential file system errors.  
    Function GetFileText(ByVal name As String) As String  
  
        ' If the file has been deleted, the right thing  
        ' to do in this case is return an empty string.  
        Dim fileContents = String.Empty  
  
        ' If the file has been deleted since we took   
        ' the snapshot, ignore it and return the empty string.  
        If System.IO.File.Exists(name) Then  
            fileContents = System.IO.File.ReadAllText(name)  
        End If  
  
        Return fileContents  
  
    End Function  
End Module  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cdcc8-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="cdcc8-109">Compiling the Code</span></span>  
 <span data-ttu-id="cdcc8-110">Cree un proyecto que tenga como destino la versión 3.5 de .NET Framework, o bien una posterior, con una referencia a System.Core.dll y una instrucción `Imports` para el espacio de nombres System.Linq.</span><span class="sxs-lookup"><span data-stu-id="cdcc8-110">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdcc8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdcc8-111">See also</span></span>
- [<span data-ttu-id="cdcc8-112">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cdcc8-112">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="cdcc8-113">LINQ y directorios de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cdcc8-113">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
