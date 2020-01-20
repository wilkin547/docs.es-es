---
title: Procedimiento para buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 20c8a917-0552-4514-b489-0b8b6a4c3b4c
ms.openlocfilehash: dee501dc8d0cabd718307b45c99ca049ae4250aa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344565"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-c"></a><span data-ttu-id="fbfe0-102">Procedimiento para buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="fbfe0-102">How to query for the largest file or files in a directory tree (LINQ) (C#)</span></span>
<span data-ttu-id="fbfe0-103">En este ejemplo se muestran cinco consultas relacionadas con el tamaño de archivo en bytes:</span><span class="sxs-lookup"><span data-stu-id="fbfe0-103">This example shows five queries related to file size in bytes:</span></span>  
  
- <span data-ttu-id="fbfe0-104">Cómo recuperar el tamaño en bytes del archivo más grande.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-104">How to retrieve the size in bytes of the largest file.</span></span>  
  
- <span data-ttu-id="fbfe0-105">Cómo recuperar el tamaño en bytes del archivo más pequeño.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-105">How to retrieve the size in bytes of the smallest file.</span></span>  
  
- <span data-ttu-id="fbfe0-106">Cómo recuperar el archivo de mayor o menor tamaño del objeto <xref:System.IO.FileInfo> de una o más carpetas en una carpeta raíz especificada.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-106">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
- <span data-ttu-id="fbfe0-107">Cómo recuperar una secuencia, como los 10 archivos de mayor tamaño.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-107">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
- <span data-ttu-id="fbfe0-108">Cómo ordenar los archivos en grupos según su tamaño en bytes, sin incluir los archivos inferiores a un tamaño especificado.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-108">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbfe0-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fbfe0-109">Example</span></span>  
 <span data-ttu-id="fbfe0-110">El ejemplo siguiente contiene cinco consultas independientes que muestran cómo consultar y agrupar archivos, en función de su tamaño en bytes.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-110">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="fbfe0-111">Puede modificar fácilmente estos ejemplos para basar la consulta en otra propiedad del objeto <xref:System.IO.FileInfo>.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-111">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
```csharp  
class QueryBySize  
{  
    static void Main(string[] args)  
    {  
        QueryFilesBySize();  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    private static void QueryFilesBySize()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Return the size of the largest file  
        long maxSize =  
            (from file in fileList  
             let len = GetFileLength(file)  
             select len)  
             .Max();  
  
        Console.WriteLine("The length of the largest file under {0} is {1}",  
            startFolder, maxSize);  
  
        // Return the FileInfo object for the largest file  
        // by sorting and selecting from beginning of list  
        System.IO.FileInfo longestFile =  
            (from file in fileList  
             let len = GetFileLength(file)  
             where len > 0  
             orderby len descending  
             select file)  
            .First();  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes",  
                            startFolder, longestFile.FullName, longestFile.Length);  
  
        //Return the FileInfo of the smallest file  
        System.IO.FileInfo smallestFile =  
            (from file in fileList  
             let len = GetFileLength(file)  
             where len > 0  
             orderby len ascending  
             select file).First();  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes",  
                            startFolder, smallestFile.FullName, smallestFile.Length);  
  
        //Return the FileInfos for the 10 largest files  
        // queryTenLargest is an IEnumerable<System.IO.FileInfo>  
        var queryTenLargest =  
            (from file in fileList  
             let len = GetFileLength(file)  
             orderby len descending  
             select file).Take(10);  
  
        Console.WriteLine("The 10 largest files under {0} are:", startFolder);  
  
        foreach (var v in queryTenLargest)  
        {  
            Console.WriteLine("{0}: {1} bytes", v.FullName, v.Length);  
        }  
  
        // Group the files according to their size, leaving out  
        // files that are less than 200000 bytes.   
        var querySizeGroups =  
            from file in fileList  
            let len = GetFileLength(file)  
            where len > 0  
            group file by (len / 100000) into fileGroup  
            where fileGroup.Key >= 2  
            orderby fileGroup.Key descending  
            select fileGroup;  
  
        foreach (var filegroup in querySizeGroups)  
        {  
            Console.WriteLine(filegroup.Key.ToString() + "00000");  
            foreach (var item in filegroup)  
            {  
                Console.WriteLine("\t{0}: {1}", item.Name, item.Length);  
            }  
        }  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the FileInfo.Length property.  
    // In this particular case, it is safe to swallow the exception.  
    static long GetFileLength(System.IO.FileInfo fi)  
    {  
        long retval;  
        try  
        {  
            retval = fi.Length;  
        }  
        catch (System.IO.FileNotFoundException)  
        {  
            // If a file is no longer present,  
            // just add zero bytes to the total.  
            retval = 0;  
        }  
        return retval;  
    }  
  
}  
```  
  
 <span data-ttu-id="fbfe0-112">Para devolver uno o más objetos <xref:System.IO.FileInfo> completos, la consulta debe examinar cada uno de ellos en los datos de origen y, después, ordenarlos por el valor de su propiedad Length.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-112">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="fbfe0-113">Después, puede devolver el objeto único o la secuencia con la mayor longitud.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-113">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="fbfe0-114">Use <xref:System.Linq.Enumerable.First%2A> para devolver el primer elemento de una lista.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-114">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="fbfe0-115">Use <xref:System.Linq.Enumerable.Take%2A> para devolver el primer número n de elementos.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-115">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="fbfe0-116">Especifique un criterio de ordenación descendente para colocar los elementos más pequeños al principio de la lista.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-116">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="fbfe0-117">La consulta llama a un método independiente para obtener el tamaño del archivo en bytes para consumir la posible excepción que se generará en el caso de que se haya eliminado un archivo en otro subproceso en el período de tiempo desde que se ha creado el objeto <xref:System.IO.FileInfo> en la llamada a `GetFiles`.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-117">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="fbfe0-118">Aunque ya se haya creado el objeto <xref:System.IO.FileInfo>, puede producirse una excepción porque un objeto <xref:System.IO.FileInfo> intentará actualizar su propiedad <xref:System.IO.FileInfo.Length%2A> con el tamaño más actual la primera vez que se tenga acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-118">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="fbfe0-119">Al incluir esta operación en un bloque try-catch fuera de la consulta, seguimos la regla de evitar las operaciones en las consultas que pueden producir efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-119">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="fbfe0-120">En general, debe tener mucho cuidado al consumir excepciones para asegurarse de que no deja una aplicación en un estado desconocido.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-120">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fbfe0-121">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="fbfe0-121">Compiling the Code</span></span>  
<span data-ttu-id="fbfe0-122">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="fbfe0-122">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="fbfe0-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbfe0-123">See also</span></span>

- [<span data-ttu-id="fbfe0-124">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="fbfe0-124">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="fbfe0-125">LINQ y directorios de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="fbfe0-125">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
