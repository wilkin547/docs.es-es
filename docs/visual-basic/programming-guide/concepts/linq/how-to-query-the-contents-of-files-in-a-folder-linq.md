---
description: Más información acerca de cómo consultar el contenido de los archivos de una carpeta (LINQ) (Visual Basic)
title: 'Cómo: Consultar el contenido de los archivos de una carpeta (LINQ)'
ms.date: 07/20/2015
ms.assetid: edacbcd3-f3e4-4429-a8be-28a58dc0dd70
ms.openlocfilehash: 5043f64a0bb38811b6155394b18a88f702515cc5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434997"
---
# <a name="how-to-query-the-contents-of-files-in-a-folder-linq-visual-basic"></a>Cómo consultar el contenido de los archivos de una carpeta (LINQ) (Visual Basic)

En este ejemplo se muestra cómo consultar todos los archivos en un árbol de directorios especificado, abrir cada archivo e inspeccionar su contenido. Este tipo de técnica puede usarse para crear índices o índices inversos del contenido de un árbol de directorios. En este ejemplo, se realiza una búsqueda de cadena simple. Pero los tipos más complejos de coincidencia de patrones se pueden realizar con una expresión regular. Para obtener más información, vea [Cómo: combinar consultas LINQ con expresiones regulares (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md).  
  
## <a name="example"></a>Ejemplo  
  
```vb
Imports System.IO

Module Module1  
    'QueryContents  
    Public Sub Main()  
  
        ' Modify this path as necessary.  
        Dim startFolder = "C:\Program Files (x86)\Microsoft Visual Studio 14.0"  

        ' Take a snapshot of the folder contents.
        Dim dir As New DirectoryInfo(startFolder)
        Dim fileList = dir.GetFiles("*.*", SearchOption.AllDirectories)

        Dim searchTerm = "Welcome"

        ' Search the contents of each file.
        ' A regular expression created with the RegEx class
        ' could be used instead of the Contains method.
        Dim queryMatchingFiles = From file In fileList _
                                 Where file.Extension = ".html" _
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
    Function GetFileText(name As String) As String

        ' If the file has been deleted, the right thing
        ' to do in this case is return an empty string.
        Dim fileContents = String.Empty

        ' If the file has been deleted since we took
        ' the snapshot, ignore it and return the empty string.
        If File.Exists(name) Then
            fileContents = File.ReadAllText(name)
        End If

        Return fileContents

    End Function
End Module
```

## <a name="compile-the-code"></a>Compilar el código

Cree un proyecto de aplicación de consola de Visual Basic, copie y pegue el ejemplo de código y ajuste el valor del objeto startup en las propiedades del proyecto.

## <a name="see-also"></a>Consulte también

- [LINQ to Objects (Visual Basic)](linq-to-objects.md)
- [LINQ y directorios de archivos (Visual Basic)](linq-and-file-directories.md)
