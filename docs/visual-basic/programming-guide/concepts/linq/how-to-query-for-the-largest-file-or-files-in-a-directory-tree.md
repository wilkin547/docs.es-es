---
title: "Cómo: buscar el mayor tamaño o archivos en un árbol de directorios (LINQ) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 055cbdd5a5903417ab382d390e1215f0319c0b5a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a>Cómo buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (Visual Basic)
Este ejemplo muestra cinco consultas relacionadas con el tamaño de archivo en bytes:  
  
-   Cómo recuperar el tamaño en bytes del archivo más grande.  
  
-   Cómo recuperar el tamaño en bytes del archivo más pequeño.  
  
-   Cómo recuperar el <xref:System.IO.FileInfo>archivo mayor o menor de objeto de una o más carpetas bajo una carpeta raíz especificada.</xref:System.IO.FileInfo>  
  
-   Cómo recuperar una secuencia como los 10 archivos mayores.  
  
-   Cómo ordenar los archivos en grupos según su tamaño en bytes, omitiendo los archivos que son inferiores a un tamaño especificado.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente contiene cinco consultas independientes que muestran cómo consultar y agrupar archivos, dependiendo de su tamaño en bytes. Puede modificar fácilmente estos ejemplos para basar la consulta en alguna otra propiedad de la <xref:System.IO.FileInfo>objeto.</xref:System.IO.FileInfo>  
  
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
  
 Para devolver uno o más completar <xref:System.IO.FileInfo>objetos, la consulta debe examinar cada uno de los datos de origen y, a continuación, ordenarlos por el valor de su propiedad Length.</xref:System.IO.FileInfo> A continuación, puede devolver una única o la secuencia con la longitud máxima. Utilice <xref:System.Linq.Enumerable.First%2A>para devolver el primer elemento de una lista.</xref:System.Linq.Enumerable.First%2A> Utilice <xref:System.Linq.Enumerable.Take%2A>para devolver el primer número n de elementos.</xref:System.Linq.Enumerable.Take%2A> Especifique un criterio de ordenación descendente para colocar los elementos menores al principio de la lista.  
  
 La consulta llama a un método independiente para obtener el tamaño del archivo en bytes con el fin de utilizar la posible excepción que se generarán en el caso de que se eliminó un archivo en otro subproceso en el período de tiempo desde el <xref:System.IO.FileInfo>se creó el objeto en la llamada a `GetFiles`.</xref:System.IO.FileInfo> Incluso aunque el <xref:System.IO.FileInfo>objeto ya se ha creado, la excepción puede producirse porque un <xref:System.IO.FileInfo>objeto intentará actualizar su <xref:System.IO.FileInfo.Length%2A>propiedad utilizando el tamaño más actual en bytes de la primera vez que se tiene acceso a la propiedad.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo> Al incluir esta operación en un bloque try-catch fuera de la consulta, seguimos la regla de evitar las operaciones en las consultas que se pueden producir efectos secundarios. En general, gran debe tener cuidado al utilizar las excepciones, para asegurarse de que una aplicación no queda en un estado desconocido.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Crear un proyecto destinado a .NET Framework versión 3.5 o posterior con una referencia a System.Core.dll y una `Imports` instrucción del espacio de nombres System.Linq.  
  
## <a name="see-also"></a>Vea también  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [LINQ y directorios de archivos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
