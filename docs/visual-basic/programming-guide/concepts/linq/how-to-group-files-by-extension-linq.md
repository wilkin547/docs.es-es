---
title: "Cómo: agrupar archivos por extensión (LINQ) (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 904dc6d7-7162-4655-a7f4-5785d669bc5a
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f78785b4da3ae3b362603eea34d81207ed48a657
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-group-files-by-extension-linq-visual-basic"></a>Cómo: agrupar archivos por extensión (LINQ) (Visual Basic)
Este ejemplo muestra cómo se puede usar LINQ para realizar avanzadas de agrupación y ordenación de operaciones en las listas de archivos o carpetas. También muestra cómo paginar los resultados en la ventana de consola utilizando la <xref:System.Linq.Enumerable.Skip%2A>y <xref:System.Linq.Enumerable.Take%2A>métodos.</xref:System.Linq.Enumerable.Take%2A> </xref:System.Linq.Enumerable.Skip%2A>  
  
## <a name="example"></a>Ejemplo  
 La consulta siguiente muestra cómo agrupar el contenido de un árbol de directorio especificado por la extensión de nombre de archivo.  
  
```vb  
Module GroupByExtension  
    Public Sub Main()  
  
        ' Root folder to query, along with all subfolders.  
        Dim startFolder As String = "C:\program files\Microsoft Visual Studio 9.0\VB\"  
  
        ' Used in WriteLine() to skip over startfolder in output lines.  
        Dim rootLength As Integer = startFolder.Length  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(startFolder)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Create the query.  
        Dim queryGroupByExt = From file In fileList _  
                          Group By file.Extension.ToLower() Into fileGroup = Group _  
                          Order By ToLower _  
                          Select fileGroup  
  
        ' Execute the query. By storing the result we can  
        ' page the display with good performance.  
        Dim groupByExtList = queryGroupByExt.ToList()  
  
        ' Display one group at a time. If the number of   
        ' entries is greater than the number of lines  
        ' in the console window, then page the output.  
        Dim trimLength = startFolder.Length  
        PageOutput(groupByExtList, trimLength)  
  
    End Sub  
  
    ' Pages console diplay for large query results. No more than one group per page.  
    ' This sub specifically works with group queries of FileInfo objects  
    ' but can be modified for any type.  
    Sub PageOutput(ByVal groupQuery, ByVal charsToSkip)  
  
        ' "3" = 1 line for extension key + 1 for "Press any key" + 1 for input cursor.  
        Dim numLines As Integer = Console.WindowHeight - 3  
        ' Flag to indicate whether there are more results to diplay  
        Dim goAgain As Boolean = True  
  
        For Each fg As IEnumerable(Of System.IO.FileInfo) In groupQuery  
            ' Start a new extension at the top of a page.  
            Dim currentLine As Integer = 0  
  
            Do While (currentLine < fg.Count())  
                Console.Clear()  
                Console.WriteLine(fg(0).Extension)  
  
                ' Get the next page of results  
                ' No more than one filename per page  
                Dim resultPage = From file In fg _  
                                Skip currentLine Take numLines  
  
                ' Execute the query. Trim the display output.  
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
  
 El resultado de este programa puede ser largo, dependiendo de los detalles del sistema de archivos local y lo que el `startFolder` está establecido en. Para habilitar la visualización de todos los resultados, este ejemplo muestra cómo paginar los resultados. Las mismas técnicas pueden aplicarse a las aplicaciones Web y de Windows. Observe que, debido a que el código página los elementos de un grupo, anidado `For Each` bucle es necesario. También hay alguna lógica adicional para calcular la posición actual en la lista y para permitir al usuario detener la paginación y salir del programa. En este caso, la consulta de paginación se ejecuta contra los resultados almacenados en caché de la consulta original. En otros contextos, como LINQ to SQL, no se requiere tal almacenamiento en caché.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Crear un proyecto destinado a .NET Framework versión 3.5 o posterior con una referencia a System.Core.dll y una `Imports` instrucción del espacio de nombres System.Linq.  
  
## <a name="see-also"></a>Vea también  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [LINQ y directorios de archivos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
