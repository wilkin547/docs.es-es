---
title: 'Cómo: Buscar archivos con un nombre o atributo especificados'
ms.date: 07/20/2015
ms.assetid: b26026a3-3f43-448f-a582-259997af6be0
ms.openlocfilehash: 970fb862b843016425e3a0f0c2bcf00e6fcba3a6
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342136"
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-visual-basic"></a>Cómo: buscar archivos con un nombre o atributo especificados (Visual Basic)
En este ejemplo se muestra cómo encontrar todos los archivos con una determinada extensión de nombre de archivo (por ejemplo, ".txt") en un árbol de directorios especificado. También se muestra cómo devolver el archivo más reciente o más antiguo del árbol por fecha de creación.  
  
## <a name="example"></a>Ejemplo  
  
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
  
## <a name="compile-the-code"></a>Compilar el código  
Cree un proyecto de aplicación de consola de Visual Basic, con una instrucción de `Imports` para el espacio de nombres System. Linq.
  
## <a name="see-also"></a>Vea también

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [LINQ y directorios de archivos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
