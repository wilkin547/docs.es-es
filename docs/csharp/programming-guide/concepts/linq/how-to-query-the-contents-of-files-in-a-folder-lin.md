---
title: 'Cómo: Consultar el contenido de los archivos de texto de una carpeta (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: f5b4dce7-1a34-4eb4-9bf1-60d5bdda264c
ms.openlocfilehash: 4e421e1bdb5008816989c26b725faaf2b4ae8caf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-query-the-contents-of-text-files-in-a-folder-linq-c"></a>Cómo: Consultar el contenido de los archivos de texto de una carpeta (LINQ) (C#)
En este ejemplo se muestra cómo consultar todos los archivos en un árbol de directorios especificado, abrir cada archivo e inspeccionar su contenido. Este tipo de técnica puede usarse para crear índices o índices inversos del contenido de un árbol de directorios. En este ejemplo, se realiza una búsqueda de cadena simple. Pero los tipos más complejos de coincidencia de patrones se pueden realizar con una expresión regular. Para obtener más información, vea [How to: Combine LINQ Queries with Regular Expressions (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md) (Cómo: Combinar consultas LINQ con expresiones regulares [C#]).  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
class QueryContents  
{  
    public static void Main()  
    {  
        // Modify this path as necessary.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        string searchTerm = @"Visual Studio";  
  
        // Search the contents of each file.  
        // A regular expression created with the RegEx class  
        // could be used instead of the Contains method.  
        // queryMatchingFiles is an IEnumerable<string>.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = GetFileText(file.FullName)  
            where fileText.Contains(searchTerm)  
            select file.FullName;  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm);  
        foreach (string filename in queryMatchingFiles)  
        {  
            Console.WriteLine(filename);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Read the contents of the file.  
    static string GetFileText(string name)  
    {  
        string fileContents = String.Empty;  
  
        // If the file has been deleted since we took   
        // the snapshot, ignore it and return the empty string.  
        if (System.IO.File.Exists(name))  
        {  
            fileContents = System.IO.File.ReadAllText(name);  
        }  
        return fileContents;  
    }  
}  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Cree un proyecto destinado a .NET Framework versión 3.5 o posterior, con una referencia a System.Core.dll y directivas `using` para los espacios de nombres System.Linq y System.IO.  
  
## <a name="see-also"></a>Vea también  
 [LINQ y directorios de archivos (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)  
 [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
