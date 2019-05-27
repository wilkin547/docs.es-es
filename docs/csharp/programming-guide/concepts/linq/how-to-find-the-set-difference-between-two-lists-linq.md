---
title: Procedimiento para buscar la diferencia de conjuntos entre dos listas (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 8e8945f0-4aba-439d-8d5d-c8d1eeef4e71
ms.openlocfilehash: c8f01cb53665d01d4c7861bab758ecc9e0dcc3c8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65585711"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-c"></a>Procedimiento para buscar la diferencia de conjuntos entre dos listas (LINQ) (C#)
En este ejemplo se muestra cómo usar LINQ para comparar dos listas de cadenas y generar estas líneas, que están en names1.txt pero no en names2.txt.  
  
### <a name="to-create-the-data-files"></a>Para crear los archivos de datos  
  
1. Copie names1.txt y names2.txt en la carpeta de la solución, como se muestra en [Cómo: Combinar y comparar colecciones de cadenas (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md).  
  
## <a name="example"></a>Ejemplo  
  
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
  
 Algunos tipos de operaciones de consulta en C#, como <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A> y <xref:System.Linq.Enumerable.Concat%2A>, solo pueden expresarse en una sintaxis basada en método.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.  
  
## <a name="see-also"></a>Vea también

- [LINQ y cadenas (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)
