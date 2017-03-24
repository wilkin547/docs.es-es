---
title: "Cómo: buscar el número Total de Bytes en un conjunto de carpetas (LINQ) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 668a8a4d89f7b81c3aef9b4e1a46ad749c4a8341
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a>Cómo: buscar el número Total de Bytes en un conjunto de carpetas (LINQ) (Visual Basic)
Este ejemplo muestra cómo recuperar el número total de bytes utilizados por todos los archivos en una carpeta especificada y todas sus subcarpetas.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Linq.Enumerable.Sum%2A>método agrega los valores de todos los elementos seleccionados en el `select` cláusula.</xref:System.Linq.Enumerable.Sum%2A> Puede modificar fácilmente esta consulta para recuperar el archivo mayor o menor en el árbol de directorio especificado llamando al <xref:System.Linq.Enumerable.Min%2A> <xref:System.Linq.Enumerable.Max%2A>método en lugar de <xref:System.Linq.Enumerable.Sum%2A>.</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Max%2A> o</xref:System.Linq.Enumerable.Min%2A>  
  
```vb  
Module QueryTotalBytes  
    Sub Main()  
  
        ' Change the drive\path if necessary.  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0\VB"  
  
        'Take a snapshot of the folder contents.  
        ' This method assumes that the application has discovery permissions  
        ' for all folders under the specified path.  
        Dim fileList = My.Computer.FileSystem.GetFiles _  
                  (root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")  
  
        Dim fileQuery = From file In fileList _  
                        Select GetFileLength(file)  
  
        ' Force execution and cache the results to avoid multiple trips to the file system.  
        Dim fileLengths = fileQuery.ToArray()  
  
        ' Find the largest file  
        Dim maxSize = Aggregate aFile In fileLengths Into Max()  
  
        ' Find the total number of bytes  
        Dim totalBytes = Aggregate aFile In fileLengths Into Sum()  
  
        Console.WriteLine("The largest file is " & maxSize & " bytes")  
        Console.WriteLine("There are " & totalBytes & " total bytes in " & _  
                          fileList.Count & " files under " & root)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    Function GetFileLength(ByVal filename As String) As Long  
        Dim retval As Long  
        Try  
            Dim fi As New System.IO.FileInfo(filename)  
            retval = fi.Length  
        Catch ex As System.IO.FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 Si sólo tiene que contar el número de bytes en un árbol de directorios especificado, puede hacerlo de forma más eficaz sin crear una consulta LINQ, que implica la sobrecarga de la creación de la colección de listas como origen de datos. La utilidad del enfoque LINQ aumenta según la consulta se vuelve más compleja, o cuando tiene que ejecutar varias consultas en el mismo origen de datos.  
  
 La consulta llama a un método independiente para obtener la longitud del archivo. Para ello, con el fin de utilizar la posible excepción que se producirá si se eliminó el archivo en otro subproceso después de la <xref:System.IO.FileInfo>se creó el objeto en la llamada a `GetFiles`.</xref:System.IO.FileInfo> Aunque la <xref:System.IO.FileInfo>objeto ya se ha creado, la excepción puede producirse porque un <xref:System.IO.FileInfo>objeto intentará actualizar su <xref:System.IO.FileInfo.Length%2A>propiedad con la longitud actual más la primera vez que se tiene acceso a la propiedad.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo> Al incluir esta operación en un bloque try-catch fuera de la consulta, el código sigue la regla de evitar las operaciones en las consultas que se pueden producir efectos secundarios. En general, gran debe tener cuidado al utilizar las excepciones, para asegurarse de que una aplicación no queda en un estado desconocido.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Crear un proyecto destinado a .NET Framework versión 3.5 o posterior con una referencia a System.Core.dll y una `Imports` instrucción del espacio de nombres System.Linq.  
  
## <a name="see-also"></a>Vea también  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [LINQ y directorios de archivos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
