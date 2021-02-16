---
description: 'Más información sobre: Cómo: buscar la diferencia de conjuntos entre dos listas (LINQ) (Visual Basic)'
title: Procedimiento para buscar la diferencia de conjuntos entre dos listas (LINQ)
ms.date: 07/20/2015
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
ms.openlocfilehash: c877be03c3ff82d4be4814035a6401385d907e60
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483695"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a><span data-ttu-id="a7cea-103">Cómo: buscar la diferencia de conjuntos entre dos listas (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7cea-103">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="a7cea-104">En este ejemplo se muestra cómo usar LINQ para comparar dos listas de cadenas y generar estas líneas, que están en names1.txt pero no en names2.txt.</span><span class="sxs-lookup"><span data-stu-id="a7cea-104">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="a7cea-105">Para crear los archivos de datos</span><span class="sxs-lookup"><span data-stu-id="a7cea-105">To create the data files</span></span>  
  
1. <span data-ttu-id="a7cea-106">Copie names1.txt y names2.txt en la carpeta de la solución, tal y como se muestra en [Cómo: combinar y comparar colecciones de cadenas (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md).</span><span class="sxs-lookup"><span data-stu-id="a7cea-106">Copy names1.txt and names2.txt to your solution folder as shown in [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7cea-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7cea-107">Example</span></span>  
  
```vb  
Class CompareLists  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data sources.  
        Dim names1 As String() = System.IO.File.ReadAllLines("../../../names1.txt")  
        Dim names2 As String() = System.IO.File.ReadAllLines("../../../names2.txt")  
  
        ' Create the query. Note that method syntax must be used here.  
        Dim differenceQuery = names1.Except(names2)  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt")  
  
        ' Execute the query.  
        For Each name As String In differenceQuery  
            Console.WriteLine(name)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' The following lines are in names1.txt but not names2.txt  
' Potra, Cristina  
' Noriega, Fabricio  
' Aw, Kam Foo  
' Toyoshima, Tim  
' Guy, Wey Yuan  
' Garcia, Debra  
```  
  
 <span data-ttu-id="a7cea-108">Algunos tipos de operaciones de consulta en Visual Basic, como <xref:System.Linq.Enumerable.Except%2A> , <xref:System.Linq.Enumerable.Distinct%2A> , <xref:System.Linq.Enumerable.Union%2A> y <xref:System.Linq.Enumerable.Concat%2A> , solo se pueden expresar en la sintaxis basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="a7cea-108">Some types of query operations in Visual Basic, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="a7cea-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a7cea-109">Compile the code</span></span>  

<span data-ttu-id="a7cea-110">Cree un proyecto de aplicación de consola de Visual Basic, con una `Imports` instrucción para el espacio de nombres System. Linq.</span><span class="sxs-lookup"><span data-stu-id="a7cea-110">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7cea-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7cea-111">See also</span></span>

- [<span data-ttu-id="a7cea-112">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7cea-112">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
