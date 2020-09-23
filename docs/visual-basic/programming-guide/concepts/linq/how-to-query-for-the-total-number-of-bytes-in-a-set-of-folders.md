---
title: Procedimiento para buscar el número total de bytes en un conjunto de carpetas (LINQ)
ms.date: 07/20/2015
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
ms.openlocfilehash: c8e1ee66c2c9b570acd2c815bdc1ba0324380eda
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100209"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a><span data-ttu-id="c7407-102">Cómo: buscar el número total de bytes en un conjunto de carpetas (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7407-102">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="c7407-103">En este ejemplo se muestra cómo recuperar el número total de bytes usados por todos los archivos en una carpeta especificada y en todas sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="c7407-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7407-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7407-104">Example</span></span>  

 <span data-ttu-id="c7407-105">El método <xref:System.Linq.Enumerable.Sum%2A> agrega los valores de todos los elementos seleccionados en la cláusula `select`.</span><span class="sxs-lookup"><span data-stu-id="c7407-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="c7407-106">Puede modificar fácilmente esta consulta para recuperar el archivo más grande y más pequeño en el árbol de directorio especificado llamando al método <xref:System.Linq.Enumerable.Min%2A> o <xref:System.Linq.Enumerable.Max%2A> en lugar de <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7407-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
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
  
 <span data-ttu-id="c7407-107">Si solo tiene que contar el número de bytes en un árbol de directorio especificado, puede hacerlo de forma más eficaz sin crear una consulta LINQ, ya que conlleva la sobrecarga de crear la colección de listas como un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c7407-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="c7407-108">La utilidad del enfoque de LINQ aumenta a medida que la consulta se vuelve más compleja, o cuando se tienen que ejecutar varias consultas en el mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c7407-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="c7407-109">La consulta llama a un método independiente para obtener la longitud del archivo.</span><span class="sxs-lookup"><span data-stu-id="c7407-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="c7407-110">Lo hace para consumir la excepción que probablemente se producirá si el archivo se ha eliminado en otro subproceso después de que se creara el objeto <xref:System.IO.FileInfo> en la llamada a `GetFiles`.</span><span class="sxs-lookup"><span data-stu-id="c7407-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="c7407-111">Aunque ya se haya creado el objeto <xref:System.IO.FileInfo>, puede producirse una excepción porque un objeto <xref:System.IO.FileInfo> intentará actualizar su propiedad <xref:System.IO.FileInfo.Length%2A> con la longitud más actual la primera vez que se tenga acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c7407-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="c7407-112">Al incluir esta operación en un bloque try-catch fuera de la consulta, el código sigue la regla de evitar las operaciones en las consultas que pueden producir efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="c7407-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="c7407-113">En general, debe tener mucho cuidado al consumir excepciones para asegurarse de que no deja una aplicación en un estado desconocido.</span><span class="sxs-lookup"><span data-stu-id="c7407-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="c7407-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c7407-114">Compile the code</span></span>  

<span data-ttu-id="c7407-115">Cree un proyecto de aplicación de consola de Visual Basic, con una `Imports` instrucción para el espacio de nombres System. Linq.</span><span class="sxs-lookup"><span data-stu-id="c7407-115">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c7407-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7407-116">See also</span></span>

- [<span data-ttu-id="c7407-117">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7407-117">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
- [<span data-ttu-id="c7407-118">LINQ y directorios de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7407-118">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
