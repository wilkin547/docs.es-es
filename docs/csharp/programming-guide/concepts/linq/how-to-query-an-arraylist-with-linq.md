---
title: Procedimiento para consultar un objeto ArrayList con LINQ (C#)
description: En este ejemplo se usa LINQ para consultar un objeto ArrayList en C#. Debe declarar el tipo de la variable de rango para reflejar el tipo de los objetos de la colección.
ms.date: 07/20/2015
ms.assetid: 2bfb471c-6e9a-4e60-bd83-4a1778abde11
ms.openlocfilehash: 278c05cfc864ee4f53e1215a2acb739efd87f8b1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91154007"
---
# <a name="how-to-query-an-arraylist-with-linq-c"></a><span data-ttu-id="4b03d-104">Procedimiento para consultar un objeto ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="4b03d-104">How to query an ArrayList with LINQ (C#)</span></span>

<span data-ttu-id="4b03d-105">Cuando use LINQ para consultar colecciones no genéricas <xref:System.Collections.IEnumerable> como <xref:System.Collections.ArrayList>, debe declarar explícitamente el tipo de variable de rango para reflejar el tipo específico de los objetos de la colección.</span><span class="sxs-lookup"><span data-stu-id="4b03d-105">When using LINQ to query non-generic <xref:System.Collections.IEnumerable> collections such as <xref:System.Collections.ArrayList>, you must explicitly declare the type of the range variable to reflect the specific type of the objects in the collection.</span></span> <span data-ttu-id="4b03d-106">Por ejemplo, si tiene una <xref:System.Collections.ArrayList> de objetos `Student`, la [cláusula from](../../../language-reference/keywords/from-clause.md) debe tener un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="4b03d-106">For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [from clause](../../../language-reference/keywords/from-clause.md) should look like this:</span></span>  
  
```csharp
var query = from Student s in arrList  
//...
```  
  
 <span data-ttu-id="4b03d-107">Al especificar el tipo de la variable de rango, se convierte cada elemento de la <xref:System.Collections.ArrayList> en un `Student`.</span><span class="sxs-lookup"><span data-stu-id="4b03d-107">By specifying the type of the range variable, you are casting each item in the <xref:System.Collections.ArrayList> to a `Student`.</span></span>  
  
 <span data-ttu-id="4b03d-108">El uso de una variable de rango con tipo explícito en una expresión de consulta es equivalente a llamar al método <xref:System.Linq.Enumerable.Cast%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b03d-108">The use of an explicitly typed range variable in a query expression is equivalent to calling the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="4b03d-109"><xref:System.Linq.Enumerable.Cast%2A> genera una excepción si la conversión especificada no puede realizarse.</span><span class="sxs-lookup"><span data-stu-id="4b03d-109"><xref:System.Linq.Enumerable.Cast%2A> throws an exception if the specified cast cannot be performed.</span></span> <span data-ttu-id="4b03d-110"><xref:System.Linq.Enumerable.Cast%2A> y <xref:System.Linq.Enumerable.OfType%2A> son los dos métodos de operador de consulta estándar que funcionan en tipos <xref:System.Collections.IEnumerable> no genéricos.</span><span class="sxs-lookup"><span data-stu-id="4b03d-110"><xref:System.Linq.Enumerable.Cast%2A> and <xref:System.Linq.Enumerable.OfType%2A> are the two Standard Query Operator methods that operate on non-generic <xref:System.Collections.IEnumerable> types.</span></span> <span data-ttu-id="4b03d-111">Para obtener más información, vea [Relaciones entre tipos en operaciones de consulta LINQ](./type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4b03d-111">For more information, see [Type Relationships in LINQ Query Operations](./type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b03d-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b03d-112">Example</span></span>  

 <span data-ttu-id="4b03d-113">En el siguiente ejemplo se muestra una consulta simple sobre un <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="4b03d-113">The following example shows a simple query over an <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="4b03d-114">Tenga en cuenta que en este ejemplo se usan inicializadores de objeto cuando el código llama al método <xref:System.Collections.ArrayList.Add%2A>, pero esto no es un requisito.</span><span class="sxs-lookup"><span data-stu-id="4b03d-114">Note that this example uses object initializers when the code calls the <xref:System.Collections.ArrayList.Add%2A> method, but this is not a requirement.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using System.Linq;  
  
namespace NonGenericLINQ  
{  
    public class Student  
    {  
        public string FirstName { get; set; }  
        public string LastName { get; set; }  
        public int[] Scores { get; set; }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ArrayList arrList = new ArrayList();  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Svetlana", LastName = "Omelchenko", Scores = new int[] { 98, 92, 81, 60 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Claire", LastName = "O’Donnell", Scores = new int[] { 75, 84, 91, 39 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Sven", LastName = "Mortensen", Scores = new int[] { 88, 94, 65, 91 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Cesar", LastName = "Garcia", Scores = new int[] { 97, 89, 85, 82 }  
                    });  
  
            var query = from Student student in arrList  
                        where student.Scores[0] > 95  
                        select student;  
  
            foreach (Student s in query)  
                Console.WriteLine(s.LastName + ": " + s.Scores[0]);  
  
            // Keep the console window open in debug mode.  
            Console.WriteLine("Press any key to exit.");  
            Console.ReadKey();  
        }  
    }  
}  
/* Output:
    Omelchenko: 98  
    Garcia: 97  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b03d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b03d-115">See also</span></span>

- [<span data-ttu-id="4b03d-116">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="4b03d-116">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
