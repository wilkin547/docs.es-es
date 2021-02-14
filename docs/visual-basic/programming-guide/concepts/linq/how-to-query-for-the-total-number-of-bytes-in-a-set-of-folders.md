---
description: 'Más información acerca de cómo: consultar el número total de bytes en un conjunto de carpetas (LINQ) (Visual Basic)'
title: Procedimiento para buscar el número total de bytes en un conjunto de carpetas (LINQ)
ms.date: 07/20/2015
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
ms.openlocfilehash: 493caa8c3f42a9f00ccca539ec8349b9f8d361b8
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435049"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a>Cómo: buscar el número total de bytes en un conjunto de carpetas (LINQ) (Visual Basic)

En este ejemplo se muestra cómo recuperar el número total de bytes usados por todos los archivos en una carpeta especificada y en todas sus subcarpetas.  
  
## <a name="example"></a>Ejemplo  

 El método <xref:System.Linq.Enumerable.Sum%2A> agrega los valores de todos los elementos seleccionados en la cláusula `select`. Puede modificar fácilmente esta consulta para recuperar el archivo más grande y más pequeño en el árbol de directorio especificado llamando al método <xref:System.Linq.Enumerable.Min%2A> o <xref:System.Linq.Enumerable.Max%2A> en lugar de <xref:System.Linq.Enumerable.Sum%2A>.  
  
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
  
 Si solo tiene que contar el número de bytes en un árbol de directorio especificado, puede hacerlo de forma más eficaz sin crear una consulta LINQ, ya que conlleva la sobrecarga de crear la colección de listas como un origen de datos. La utilidad del enfoque de LINQ aumenta a medida que la consulta se vuelve más compleja, o cuando se tienen que ejecutar varias consultas en el mismo origen de datos.  
  
 La consulta llama a un método independiente para obtener la longitud del archivo. Lo hace para consumir la excepción que probablemente se producirá si el archivo se ha eliminado en otro subproceso después de que se creara el objeto <xref:System.IO.FileInfo> en la llamada a `GetFiles`. Aunque ya se haya creado el objeto <xref:System.IO.FileInfo>, puede producirse una excepción porque un objeto <xref:System.IO.FileInfo> intentará actualizar su propiedad <xref:System.IO.FileInfo.Length%2A> con la longitud más actual la primera vez que se tenga acceso a la propiedad. Al incluir esta operación en un bloque try-catch fuera de la consulta, el código sigue la regla de evitar las operaciones en las consultas que pueden producir efectos secundarios. En general, debe tener mucho cuidado al consumir excepciones para asegurarse de que no deja una aplicación en un estado desconocido.  
  
## <a name="compile-the-code"></a>Compilar el código  

Cree un proyecto de aplicación de consola de Visual Basic, con una `Imports` instrucción para el espacio de nombres System. Linq.
  
## <a name="see-also"></a>Consulte también

- [LINQ to Objects (Visual Basic)](linq-to-objects.md)
- [LINQ y directorios de archivos (Visual Basic)](linq-and-file-directories.md)
