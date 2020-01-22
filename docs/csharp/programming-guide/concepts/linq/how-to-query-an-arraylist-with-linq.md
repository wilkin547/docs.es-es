---
title: Procedimiento para consultar un objeto ArrayList con LINQ (C#)
ms.date: 07/20/2015
ms.assetid: 2bfb471c-6e9a-4e60-bd83-4a1778abde11
ms.openlocfilehash: b8edb90d33c92324d4f76c7e6977641fe4499d9d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345705"
---
# <a name="how-to-query-an-arraylist-with-linq-c"></a>Procedimiento para consultar un objeto ArrayList con LINQ (C#)
Cuando use LINQ para consultar colecciones no genéricas <xref:System.Collections.IEnumerable> como <xref:System.Collections.ArrayList>, debe declarar explícitamente el tipo de variable de rango para reflejar el tipo específico de los objetos de la colección. Por ejemplo, si tiene una <xref:System.Collections.ArrayList> de objetos `Student`, la [cláusula from](../../../language-reference/keywords/from-clause.md) debe tener un aspecto similar a este:  
  
```csharp
var query = from Student s in arrList  
//...
```  
  
 Al especificar el tipo de la variable de rango, se convierte cada elemento de la <xref:System.Collections.ArrayList> en un `Student`.  
  
 El uso de una variable de rango con tipo explícito en una expresión de consulta es equivalente a llamar al método <xref:System.Linq.Enumerable.Cast%2A>. <xref:System.Linq.Enumerable.Cast%2A> genera una excepción si la conversión especificada no puede realizarse. <xref:System.Linq.Enumerable.Cast%2A> y <xref:System.Linq.Enumerable.OfType%2A> son los dos métodos de operador de consulta estándar que funcionan en tipos <xref:System.Collections.IEnumerable> no genéricos. Para obtener más información, vea [Relaciones entre tipos en operaciones de consulta LINQ](./type-relationships-in-linq-query-operations.md).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra una consulta simple sobre un <xref:System.Collections.ArrayList>. Tenga en cuenta que en este ejemplo se usan inicializadores de objeto cuando el código llama al método <xref:System.Collections.ArrayList.Add%2A>, pero esto no es un requisito.  
  
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
  
## <a name="see-also"></a>Vea también

- [LINQ to Objects (C#)](./linq-to-objects.md)
