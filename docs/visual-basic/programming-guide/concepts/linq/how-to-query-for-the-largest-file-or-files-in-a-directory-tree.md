---
title: Procedimiento para buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ)
ms.date: 07/20/2015
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
ms.openlocfilehash: 107f3457fe7361fab16c2c8ce837c90484fc7633
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397952"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="b1cf0-102">Cómo buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1cf0-102">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="b1cf0-103">En este ejemplo se muestran cinco consultas relacionadas con el tamaño de archivo en bytes:</span><span class="sxs-lookup"><span data-stu-id="b1cf0-103">This example shows five queries related to file size in bytes:</span></span>  
  
- <span data-ttu-id="b1cf0-104">Cómo recuperar el tamaño en bytes del archivo más grande.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-104">How to retrieve the size in bytes of the largest file.</span></span>  
  
- <span data-ttu-id="b1cf0-105">Cómo recuperar el tamaño en bytes del archivo más pequeño.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-105">How to retrieve the size in bytes of the smallest file.</span></span>  
  
- <span data-ttu-id="b1cf0-106">Cómo recuperar el archivo de mayor o menor tamaño del objeto <xref:System.IO.FileInfo> de una o más carpetas en una carpeta raíz especificada.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-106">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
- <span data-ttu-id="b1cf0-107">Cómo recuperar una secuencia, como los 10 archivos de mayor tamaño.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-107">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
- <span data-ttu-id="b1cf0-108">Cómo ordenar los archivos en grupos según su tamaño en bytes, sin incluir los archivos inferiores a un tamaño especificado.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-108">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1cf0-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1cf0-109">Example</span></span>  
 <span data-ttu-id="b1cf0-110">El ejemplo siguiente contiene cinco consultas independientes que muestran cómo consultar y agrupar archivos, en función de su tamaño en bytes.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-110">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="b1cf0-111">Puede modificar fácilmente estos ejemplos para basar la consulta en otra propiedad del objeto <xref:System.IO.FileInfo>.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-111">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
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
  
 <span data-ttu-id="b1cf0-112">Para devolver uno o más objetos <xref:System.IO.FileInfo> completos, la consulta debe examinar cada uno de ellos en los datos de origen y, después, ordenarlos por el valor de su propiedad Length.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-112">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="b1cf0-113">Después, puede devolver el objeto único o la secuencia con la mayor longitud.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-113">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="b1cf0-114">Use <xref:System.Linq.Enumerable.First%2A> para devolver el primer elemento de una lista.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-114">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="b1cf0-115">Use <xref:System.Linq.Enumerable.Take%2A> para devolver el primer número n de elementos.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-115">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="b1cf0-116">Especifique un criterio de ordenación descendente para colocar los elementos más pequeños al principio de la lista.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-116">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="b1cf0-117">La consulta llama a un método independiente para obtener el tamaño del archivo en bytes para consumir la posible excepción que se generará en el caso de que se haya eliminado un archivo en otro subproceso en el período de tiempo desde que se ha creado el objeto <xref:System.IO.FileInfo> en la llamada a `GetFiles`.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-117">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="b1cf0-118">Aunque ya se haya creado el objeto <xref:System.IO.FileInfo>, puede producirse una excepción porque un objeto <xref:System.IO.FileInfo> intentará actualizar su propiedad <xref:System.IO.FileInfo.Length%2A> con el tamaño más actual la primera vez que se tenga acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-118">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="b1cf0-119">Al incluir esta operación en un bloque try-catch fuera de la consulta, seguimos la regla de evitar las operaciones en las consultas que pueden producir efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-119">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="b1cf0-120">En general, debe tener mucho cuidado al consumir excepciones para asegurarse de que no deja una aplicación en un estado desconocido.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-120">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="b1cf0-121">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b1cf0-121">Compile the code</span></span>  
<span data-ttu-id="b1cf0-122">Cree un proyecto de aplicación de consola de Visual Basic, con una `Imports` instrucción para el espacio de nombres System. Linq.</span><span class="sxs-lookup"><span data-stu-id="b1cf0-122">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b1cf0-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1cf0-123">See also</span></span>

- [<span data-ttu-id="b1cf0-124">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1cf0-124">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
- [<span data-ttu-id="b1cf0-125">LINQ y directorios de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1cf0-125">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
