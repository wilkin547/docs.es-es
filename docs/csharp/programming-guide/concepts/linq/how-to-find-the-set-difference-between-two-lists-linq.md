---
title: Procedimiento para buscar la diferencia de conjuntos entre dos listas (LINQ) (C#)
description: Aprenda a usar LINQ en C# para comparar dos listas de cadenas y generar estas líneas, que están en una lista, pero no en la otra.
ms.date: 07/20/2015
ms.assetid: 8e8945f0-4aba-439d-8d5d-c8d1eeef4e71
ms.openlocfilehash: 24509488d91f9861ee9bf84277238bea7031e5f6
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105085"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-c"></a><span data-ttu-id="d30f3-103">Procedimiento para buscar la diferencia de conjuntos entre dos listas (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d30f3-103">How to find the set difference between two lists (LINQ) (C#)</span></span>
<span data-ttu-id="d30f3-104">En este ejemplo se muestra cómo usar LINQ para comparar dos listas de cadenas y generar estas líneas, que están en names1.txt pero no en names2.txt.</span><span class="sxs-lookup"><span data-stu-id="d30f3-104">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="d30f3-105">Para crear los archivos de datos</span><span class="sxs-lookup"><span data-stu-id="d30f3-105">To create the data files</span></span>  
  
1. <span data-ttu-id="d30f3-106">Copie names1.txt y names2.txt en la carpeta de la solución, como se muestra en [Procedimiento para combinar y comparar colecciones de cadenas (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md).</span><span class="sxs-lookup"><span data-stu-id="d30f3-106">Copy names1.txt and names2.txt to your solution folder as shown in [How to combine and compare string collections (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d30f3-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d30f3-107">Example</span></span>  
  
```csharp  
class CompareLists  
{
    static void Main()  
    {  
        // Create the IEnumerable data sources.  
        string[] names1 = System.IO.File.ReadAllLines(@"../../../names1.txt");  
        string[] names2 = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
        // Create the query. Note that method syntax must be used here.  
        IEnumerable<string> differenceQuery =  
          names1.Except(names2);  
  
        // Execute the query.  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt");  
        foreach (string s in differenceQuery)  
            Console.WriteLine(s);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
     The following lines are in names1.txt but not names2.txt  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
     */  
```  
  
 <span data-ttu-id="d30f3-108">Algunos tipos de operaciones de consulta en C#, como <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A> y <xref:System.Linq.Enumerable.Concat%2A>, solo pueden expresarse en una sintaxis basada en método.</span><span class="sxs-lookup"><span data-stu-id="d30f3-108">Some types of query operations in C#, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d30f3-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d30f3-109">Compiling the Code</span></span>  
 <span data-ttu-id="d30f3-110">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="d30f3-110">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d30f3-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d30f3-111">See also</span></span>

- [<span data-ttu-id="d30f3-112">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="d30f3-112">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
