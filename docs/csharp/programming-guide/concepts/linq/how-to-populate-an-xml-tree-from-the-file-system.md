---
title: "Cómo: Rellenar un árbol XML desde el sistema de archivos (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 2aa2ccac-4a22-47ae-9107-3bb8df232576
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b3537a63f6fd39b3c1216190b24ca0e8c654e2f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-populate-an-xml-tree-from-the-file-system-c"></a><span data-ttu-id="a123a-102">Cómo: Rellenar un árbol XML desde el sistema de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="a123a-102">How to: Populate an XML Tree from the File System (C#)</span></span>
<span data-ttu-id="a123a-103">Una aplicación habitual y útil de los árboles XML es un almacén de datos de nombres y valores jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="a123a-103">A common and useful application of XML trees is as a hierarchical name/value data store.</span></span> <span data-ttu-id="a123a-104">Puede rellenar un árbol XML con datos jerárquicos y, a continuación, consultarlo, transformarlo y, si es necesario, serializarlo.</span><span class="sxs-lookup"><span data-stu-id="a123a-104">You can populate an XML tree with hierarchical data, and then query it, transform it, and if necessary, serialize it.</span></span> <span data-ttu-id="a123a-105">En este escenario de uso, gran parte de la semántica específica XML (por ejemplo, el comportamiento de los espacios en blanco y los espacios de nombres) no es importante.</span><span class="sxs-lookup"><span data-stu-id="a123a-105">In this usage scenario, many of the XML specific semantics, such as namespaces and white space behavior, are not important.</span></span> <span data-ttu-id="a123a-106">En su lugar, usará el árbol XML como una base de datos jerárquica, pequeña y en memoria, de usuario único.</span><span class="sxs-lookup"><span data-stu-id="a123a-106">Instead, you are using the XML tree as a small, in memory, single user hierarchical database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a123a-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a123a-107">Example</span></span>  
 <span data-ttu-id="a123a-108">El ejemplo siguiente rellena un árbol XML desde el sistema de archivos local mediante la recursividad.</span><span class="sxs-lookup"><span data-stu-id="a123a-108">The following example populates an XML tree from the local file system using recursion.</span></span> <span data-ttu-id="a123a-109">A continuación, consulta el árbol y calcula el total de los tamaños de todos los archivos del árbol.</span><span class="sxs-lookup"><span data-stu-id="a123a-109">It then queries the tree, calculating the total of the sizes of all files in the tree.</span></span>  
  
```csharp  
class Program  
{  
    static XElement CreateFileSystemXmlTree(string source)  
    {  
        DirectoryInfo di = new DirectoryInfo(source);  
        return new XElement("Dir",  
            new XAttribute("Name", di.Name),  
            from d in Directory.GetDirectories(source)  
            select CreateFileSystemXmlTree(d),  
            from fi in di.GetFiles()  
            select new XElement("File",  
                new XElement("Name", fi.Name),  
                new XElement("Length", fi.Length)  
            )  
        );  
    }  
  
    static void Main(string[] args)  
    {  
        XElement fileSystemTree = CreateFileSystemXmlTree("C:/Tmp");  
        Console.WriteLine(fileSystemTree);  
        Console.WriteLine("------");  
        long totalFileSize =  
            (from f in fileSystemTree.Descendants("File")  
             select (long)f.Element("Length")).Sum();  
        Console.WriteLine("Total File Size:{0}", totalFileSize);  
    }  
}  
```  
  
 <span data-ttu-id="a123a-110">Este ejemplo genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a123a-110">This example produces output similar to the following:</span></span>  
  
```xml  
<Dir Name="Tmp">  
  <Dir Name="ConsoleApplication1">  
    <Dir Name="bin">  
      <Dir Name="Debug">  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe</Name>  
          <Length>9568</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe.manifest</Name>  
          <Length>473</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="obj">  
      <Dir Name="Debug">  
        <Dir Name="TempPE" />  
        <File>  
          <Name>ConsoleApplication1.csproj.FileListAbsolute.txt</Name>  
          <Length>322</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="Properties">  
      <File>  
        <Name>AssemblyInfo.cs</Name>  
        <Length>1454</Length>  
      </File>  
    </Dir>  
    <File>  
      <Name>ConsoleApplication1.csproj</Name>  
      <Length>2546</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.sln</Name>  
      <Length>937</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.suo</Name>  
      <Length>10752</Length>  
    </File>  
    <File>  
      <Name>Program.cs</Name>  
      <Length>269</Length>  
    </File>  
  </Dir>  
</Dir>  
------  
Total File Size:59089  
```  
  
## <a name="see-also"></a><span data-ttu-id="a123a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a123a-111">See Also</span></span>  
 <span data-ttu-id="a123a-112">[Advanced Query Techniques (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md) (Técnicas de consulta avanzadas (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="a123a-112">[Advanced Query Techniques (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)</span></span>
