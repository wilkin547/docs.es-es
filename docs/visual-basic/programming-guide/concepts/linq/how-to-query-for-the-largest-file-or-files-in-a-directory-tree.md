---
title: 'Cómo: Cómo buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ)'
ms.date: 07/20/2015
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
ms.openlocfilehash: 34f2cd97cafbe142c9462e8d0cf7c17f9f0d16f9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346068"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a>Cómo buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (Visual Basic)
En este ejemplo se muestran cinco consultas relacionadas con el tamaño de archivo en bytes:  
  
- Cómo recuperar el tamaño en bytes del archivo más grande.  
  
- Cómo recuperar el tamaño en bytes del archivo más pequeño.  
  
- Cómo recuperar el archivo de mayor o menor tamaño del objeto <xref:System.IO.FileInfo> de una o más carpetas en una carpeta raíz especificada.  
  
- Cómo recuperar una secuencia, como los 10 archivos de mayor tamaño.  
  
- Cómo ordenar los archivos en grupos según su tamaño en bytes, sin incluir los archivos inferiores a un tamaño especificado.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente contiene cinco consultas independientes que muestran cómo consultar y agrupar archivos, en función de su tamaño en bytes. Puede modificar fácilmente estos ejemplos para basar la consulta en otra propiedad del objeto <xref:System.IO.FileInfo>.  
  
```vb  
Module QueryBySize  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Return the size of the largest file  
        Dim maxSize = Aggregate aFile In fileList Into Max(GetFileLength(aFile))  
  
        'Dim maxSize = fileLengths.Max  
        Console.WriteLine("The length of the largest file under {0} is {1}", _  
                          root, maxSize)  
  
        ' Return the FileInfo object of the largest file  
        ' by sorting and selecting from the beginning of the list  
        Dim filesByLengDesc = From file In fileList _  
                              Let filelength = GetFileLength(file) _  
                              Where filelength > 0 _  
                              Order By filelength Descending _  
                              Select file  
  
        Dim longestFile = filesByLengDesc.First  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes", _  
                          root, longestFile.FullName, longestFile.Length)  
  
        Dim smallestFile = filesByLengDesc.Last  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes", _  
                                root, smallestFile.FullName, smallestFile.Length)  
  
        ' Return the FileInfos for the 10 largest files  
        ' Based on a previous query, but nothing is executed  
        ' until the For Each statement below.  
        Dim tenLargest = From file In filesByLengDesc Take 10  
  
        Console.WriteLine("The 10 largest files under {0} are:", root)  
  
        For Each fi As System.IO.FileInfo In tenLargest  
            Console.WriteLine("{0}: {1} bytes", fi.FullName, fi.Length)  
        Next  
  
        ' Group files according to their size,  
        ' leaving out the ones under 200K  
        Dim sizeGroups = From file As System.IO.FileInfo In fileList _  
                         Where file.Length > 0 _  
                         Let groupLength = file.Length / 100000 _  
                         Group file By groupLength Into fileGroup = Group _  
                         Where groupLength >= 2 _  
                         Order By groupLength Descending  
  
        For Each group In sizeGroups  
            Console.WriteLine(group.groupLength + "00000")  
  
            For Each item As System.IO.FileInfo In group.fileGroup  
                Console.WriteLine("   {0}: {1}", item.Name, item.Length)  
            Next  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    ' In this particular case, it is safe to ignore the exception.  
    Function GetFileLength(ByVal fi As System.IO.FileInfo) As Long  
        Dim retval As Long  
        Try  
            retval = fi.Length  
        Catch ex As FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 Para devolver uno o más objetos <xref:System.IO.FileInfo> completos, la consulta debe examinar cada uno de ellos en los datos de origen y, después, ordenarlos por el valor de su propiedad Length. Después, puede devolver el objeto único o la secuencia con la mayor longitud. Use <xref:System.Linq.Enumerable.First%2A> para devolver el primer elemento de una lista. Use <xref:System.Linq.Enumerable.Take%2A> para devolver el primer número n de elementos. Especifique un criterio de ordenación descendente para colocar los elementos más pequeños al principio de la lista.  
  
 La consulta llama a un método independiente para obtener el tamaño del archivo en bytes para consumir la posible excepción que se generará en el caso de que se haya eliminado un archivo en otro subproceso en el período de tiempo desde que se ha creado el objeto <xref:System.IO.FileInfo> en la llamada a `GetFiles`. Aunque ya se haya creado el objeto <xref:System.IO.FileInfo>, puede producirse una excepción porque un objeto <xref:System.IO.FileInfo> intentará actualizar su propiedad <xref:System.IO.FileInfo.Length%2A> con el tamaño más actual la primera vez que se tenga acceso a la propiedad. Al incluir esta operación en un bloque try-catch fuera de la consulta, seguimos la regla de evitar las operaciones en las consultas que pueden producir efectos secundarios. En general, debe tener mucho cuidado al consumir excepciones para asegurarse de que no deja una aplicación en un estado desconocido.  
  
## <a name="compile-the-code"></a>Compilar el código  
Cree un proyecto de aplicación de consola de Visual Basic, con una instrucción de `Imports` para el espacio de nombres System. Linq.
  
## <a name="see-also"></a>Vea también

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [LINQ y directorios de archivos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
