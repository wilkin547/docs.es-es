---
title: Procedimiento para combinar y comparar colecciones de cadenas (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 25926e5b-fde2-4dc1-86a0-16ead7aa13d2
ms.openlocfilehash: f73a31e109933a4b6dd0078934d89d3bb770de5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169459"
---
# <a name="how-to-combine-and-compare-string-collections-linq-c"></a><span data-ttu-id="00cb3-102">Procedimiento para combinar y comparar colecciones de cadenas (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="00cb3-102">How to combine and compare string collections (LINQ) (C#)</span></span>
<span data-ttu-id="00cb3-103">En este ejemplo se muestra cómo combinar archivos que contienen líneas de texto y después ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="00cb3-103">This example shows how to merge files that contain lines of text and then sort the results.</span></span> <span data-ttu-id="00cb3-104">En concreto, se muestra cómo realizar una concatenación simple, una unión y una intersección en los dos conjuntos de líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="00cb3-104">Specifically, it shows how to perform a simple concatenation, a union, and an intersection on the two sets of text lines.</span></span>  
  
### <a name="to-set-up-the-project-and-the-text-files"></a><span data-ttu-id="00cb3-105">Para configurar el proyecto y los archivos de texto</span><span class="sxs-lookup"><span data-stu-id="00cb3-105">To set up the project and the text files</span></span>  
  
1. <span data-ttu-id="00cb3-106">Copie estos nombres en un archivo de texto denominado names1.txt y guárdelo en la carpeta del proyecto:</span><span class="sxs-lookup"><span data-stu-id="00cb3-106">Copy these names into a text file that is named names1.txt and save it in your project folder:</span></span>  
  
    ```text  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Beebe, Ann  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
    ```  
  
2. <span data-ttu-id="00cb3-107">Copie estos nombres en un archivo de texto denominado names2.txt y guárdelo en la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="00cb3-107">Copy these names into a text file that is named names2.txt and save it in your project folder.</span></span> <span data-ttu-id="00cb3-108">Tenga en cuenta que los dos archivos tienen algunos nombres en común.</span><span class="sxs-lookup"><span data-stu-id="00cb3-108">Note that the two files have some names in common.</span></span>  
  
    ```text  
    Liu, Jinghao  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Beebe, Ann  
    Gilchrist, Beth  
    Myrcha, Jacek  
    Giakoumakis, Leo  
    McLin, Nkenge  
    El Yassir, Mehdi  
    ```  
  
## <a name="example"></a><span data-ttu-id="00cb3-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00cb3-109">Example</span></span>  
  
```csharp  
class MergeStrings  
    {  
        static void Main(string[] args)  
        {  
            //Put text files in your solution folder  
            string[] fileA = System.IO.File.ReadAllLines(@"../../../names1.txt");  
            string[] fileB = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
            //Simple concatenation and sort. Duplicates are preserved.  
            IEnumerable<string> concatQuery =  
                fileA.Concat(fileB).OrderBy(s => s);  
  
            // Pass the query variable to another function for execution.  
            OutputQueryResults(concatQuery, "Simple concatenate and sort. Duplicates are preserved:");  
  
            // Concatenate and remove duplicate names based on  
            // default string comparer.  
            IEnumerable<string> uniqueNamesQuery =  
                fileA.Union(fileB).OrderBy(s => s);  
            OutputQueryResults(uniqueNamesQuery, "Union removes duplicate names:");  
  
            // Find the names that occur in both files (based on  
            // default string comparer).  
            IEnumerable<string> commonNamesQuery =  
                fileA.Intersect(fileB);  
            OutputQueryResults(commonNamesQuery, "Merge based on intersect:");  
  
            // Find the matching fields in each list. Merge the two
            // results by using Concat, and then  
            // sort using the default string comparer.  
            string nameMatch = "Garcia";  
  
            IEnumerable<String> tempQuery1 =  
                from name in fileA  
                let n = name.Split(',')  
                where n[0] == nameMatch  
                select name;  
  
            IEnumerable<string> tempQuery2 =  
                from name2 in fileB  
                let n2 = name2.Split(',')  
                where n2[0] == nameMatch  
                select name2;  
  
            IEnumerable<string> nameMatchQuery =  
                tempQuery1.Concat(tempQuery2).OrderBy(s => s);  
            OutputQueryResults(nameMatchQuery, $"Concat based on partial name match \"{nameMatch}\":");
  
            // Keep the console window open in debug mode.  
            Console.WriteLine("Press any key to exit");  
            Console.ReadKey();  
        }  
  
        static void OutputQueryResults(IEnumerable<string> query, string message)  
        {  
            Console.WriteLine(System.Environment.NewLine + message);  
            foreach (string item in query)  
            {  
                Console.WriteLine(item);  
            }  
            Console.WriteLine("{0} total names in list", query.Count());  
        }  
    }  
    /* Output:  
        Simple concatenate and sort. Duplicates are preserved:  
        Aw, Kam Foo  
        Bankov, Peter  
        Bankov, Peter  
        Beebe, Ann  
        Beebe, Ann  
        El Yassir, Mehdi  
        Garcia, Debra  
        Garcia, Hugo  
        Garcia, Hugo  
        Giakoumakis, Leo  
        Gilchrist, Beth  
        Guy, Wey Yuan  
        Holm, Michael  
        Holm, Michael  
        Liu, Jinghao  
        McLin, Nkenge  
        Myrcha, Jacek  
        Noriega, Fabricio  
        Potra, Cristina  
        Toyoshima, Tim  
        20 total names in list  
  
        Union removes duplicate names:  
        Aw, Kam Foo  
        Bankov, Peter  
        Beebe, Ann  
        El Yassir, Mehdi  
        Garcia, Debra  
        Garcia, Hugo  
        Giakoumakis, Leo  
        Gilchrist, Beth  
        Guy, Wey Yuan  
        Holm, Michael  
        Liu, Jinghao  
        McLin, Nkenge  
        Myrcha, Jacek  
        Noriega, Fabricio  
        Potra, Cristina  
        Toyoshima, Tim  
        16 total names in list  
  
        Merge based on intersect:  
        Bankov, Peter  
        Holm, Michael  
        Garcia, Hugo  
        Beebe, Ann  
        4 total names in list  
  
        Concat based on partial name match "Garcia":  
        Garcia, Debra  
        Garcia, Hugo  
        Garcia, Hugo  
        3 total names in list  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="00cb3-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="00cb3-110">Compiling the Code</span></span>  
 <span data-ttu-id="00cb3-111">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="00cb3-111">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00cb3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="00cb3-112">See also</span></span>

- [<span data-ttu-id="00cb3-113">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="00cb3-113">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- <span data-ttu-id="00cb3-114">[LINQ and File Directories (C#)](./linq-and-file-directories.md) (LINQ y directorios de archivos [C#])</span><span class="sxs-lookup"><span data-stu-id="00cb3-114">[LINQ and File Directories (C#)](./linq-and-file-directories.md)</span></span>
