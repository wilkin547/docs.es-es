---
title: 'Cómo: Comparar el contenido de dos carpetas (LINQ)'
ms.date: 07/20/2015
ms.assetid: 903c7e9a-f48d-4a07-a8a8-5450d2646efa
ms.openlocfilehash: 05031466eeafae2dc63db36e9380034ddf9cbf15
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337541"
---
# <a name="how-to-compare-the-contents-of-two-folders-linq-visual-basic"></a><span data-ttu-id="30e22-102">Cómo: comparar el contenido de dos carpetas (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30e22-102">How to: Compare the Contents of Two Folders (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="30e22-103">En este ejemplo se muestran tres maneras de comparar dos listados de archivos:</span><span class="sxs-lookup"><span data-stu-id="30e22-103">This example demonstrates three ways to compare two file listings:</span></span>

- <span data-ttu-id="30e22-104">Mediante la consulta de un valor booleano que especifica si las dos listas de archivos son idénticas.</span><span class="sxs-lookup"><span data-stu-id="30e22-104">By querying for a Boolean value that specifies whether the two file lists are identical.</span></span>

- <span data-ttu-id="30e22-105">Mediante la consulta de la intersección para recuperar los archivos que están en ambas carpetas.</span><span class="sxs-lookup"><span data-stu-id="30e22-105">By querying for the intersection to retrieve the files that are in both folders.</span></span>

- <span data-ttu-id="30e22-106">Mediante la consulta de la diferencia de conjuntos para recuperar los archivos que se encuentran en una carpeta, pero no en la otra.</span><span class="sxs-lookup"><span data-stu-id="30e22-106">By querying for the set difference to retrieve the files that are in one folder but not the other.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30e22-107">Las técnicas que se mencionan aquí pueden adaptarse para comparar secuencias de objetos de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="30e22-107">The techniques shown here can be adapted to compare sequences of objects of any type.</span></span>

<span data-ttu-id="30e22-108">La clase `FileComparer` que aparece a continuación muestra cómo usar una clase de comparador personalizada junto con los operadores de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="30e22-108">The `FileComparer` class shown here demonstrates how to use a custom comparer class together with the Standard Query Operators.</span></span> <span data-ttu-id="30e22-109">La clase no está diseñada para su uso en escenarios reales.</span><span class="sxs-lookup"><span data-stu-id="30e22-109">The class is not intended for use in real-world scenarios.</span></span> <span data-ttu-id="30e22-110">Simplemente usa el nombre y la longitud en bytes de cada archivo para determinar si el contenido de cada una de las carpetas es idéntico o no.</span><span class="sxs-lookup"><span data-stu-id="30e22-110">It just uses the name and length in bytes of each file to determine whether the contents of each folder are identical or not.</span></span> <span data-ttu-id="30e22-111">En un escenario real, debería modificar este comparador para realizar una comprobación de igualdad más rigurosa.</span><span class="sxs-lookup"><span data-stu-id="30e22-111">In a real-world scenario, you should modify this comparer to perform a more rigorous equality check.</span></span>

## <a name="example"></a><span data-ttu-id="30e22-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30e22-112">Example</span></span>

```vb
Module CompareDirs
    Public Sub Main()

        ' Create two identical or different temporary folders
        ' on a local drive and add files to them.
        ' Then set these file paths accordingly.
        Dim pathA As String = "C:\TestDir"
        Dim pathB As String = "C:\TestDir2"

        ' Take a snapshot of the file system.
        Dim dir1 As New System.IO.DirectoryInfo(pathA)
        Dim dir2 As New System.IO.DirectoryInfo(pathB)

        Dim list1 = dir1.GetFiles("*.*", System.IO.SearchOption.AllDirectories)
        Dim list2 = dir2.GetFiles("*.*", System.IO.SearchOption.AllDirectories)

        ' Create the FileCompare object we'll use in each query
        Dim myFileCompare As New FileCompare

        ' This query determines whether the two folders contain
        ' identical file lists, based on the custom file comparer
        ' that is defined in the FileCompare class.
        ' The query executes immediately because it returns a bool.
        Dim areIdentical As Boolean = list1.SequenceEqual(list2, myFileCompare)
        If areIdentical = True Then
            Console.WriteLine("The two folders are the same.")
        Else
            Console.WriteLine("The two folders are not the same.")
        End If

        ' Find common files in both folders. It produces a sequence and doesn't execute
        ' until the foreach statement.
        Dim queryCommonFiles = list1.Intersect(list2, myFileCompare)

        If queryCommonFiles.Count() > 0 Then

            Console.WriteLine("The following files are in both folders:")
            For Each fi As System.IO.FileInfo In queryCommonFiles
                Console.WriteLine(fi.FullName)
            Next
        Else
            Console.WriteLine("There are no common files in the two folders.")
        End If

        ' Find the set difference between the two folders.
        ' For this example we only check one way.
        Dim queryDirAOnly = list1.Except(list2, myFileCompare)
        Console.WriteLine("The following files are in dirA but not dirB:")
        For Each fi As System.IO.FileInfo In queryDirAOnly
            Console.WriteLine(fi.FullName)
        Next

        ' Keep the console window open in debug mode
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()
    End Sub

    ' This implementation defines a very simple comparison
    ' between two FileInfo objects. It only compares the name
    ' of the files being compared and their length in bytes.
    Public Class FileCompare
        Implements System.Collections.Generic.IEqualityComparer(Of System.IO.FileInfo)

        Public Function Equals1(ByVal x As System.IO.FileInfo, ByVal y As System.IO.FileInfo) _
            As Boolean Implements System.Collections.Generic.IEqualityComparer(Of System.IO.FileInfo).Equals

            If (x.Name = y.Name) And (x.Length = y.Length) Then
                Return True
            Else
                Return False
            End If
        End Function

        ' Return a hash that reflects the comparison criteria. According to the
        ' rules for IEqualityComparer(Of T), if Equals is true, then the hash codes must
        ' also be equal. Because equality as defined here is a simple value equality, not
        ' reference identity, it is possible that two or more objects will produce the same
        ' hash code.
        Public Function GetHashCode1(ByVal fi As System.IO.FileInfo) _
            As Integer Implements System.Collections.Generic.IEqualityComparer(Of System.IO.FileInfo).GetHashCode
            Dim s As String = fi.Name & fi.Length
            Return s.GetHashCode()
        End Function
    End Class
End Module
```

## <a name="compile-the-code"></a><span data-ttu-id="30e22-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="30e22-113">Compile the code</span></span>

<span data-ttu-id="30e22-114">Cree un proyecto de aplicación de consola de Visual Basic, con una instrucción de `Imports` para el espacio de nombres System. Linq.</span><span class="sxs-lookup"><span data-stu-id="30e22-114">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="30e22-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="30e22-115">See also</span></span>

- [<span data-ttu-id="30e22-116">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30e22-116">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="30e22-117">LINQ y directorios de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30e22-117">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
