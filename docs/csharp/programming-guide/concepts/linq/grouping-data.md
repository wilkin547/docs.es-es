---
title: Agrupar datos (C#) | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ef56a843117bb8b7409b10ef33ca83175849b9f
ms.lasthandoff: 03/13/2017

---
# <a name="grouping-data-c"></a>Agrupar datos (C#)
El agrupamiento hace referencia a la operación de colocar los datos en grupos de manera que los elementos de cada grupo compartan un atributo común.  
  
 La ilustración siguiente muestra los resultados de agrupar una secuencia de caracteres. La clave de cada grupo es el carácter.  
  
 ![Operaciones de agrupamiento en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")  
  
 Los métodos de operador de consulta estándar que agrupan elementos de datos se enumeran en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de la expresión de consulta de C#|Más información|  
|-----------------|-----------------|---------------------------------|----------------------|  
|GroupBy|Agrupa los elementos que comparten un atributo común. Cada grupo está representado por un objeto <xref:System.Linq.IGrouping%602>.|`group … by`<br /><br /> O bien<br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName>|  
|ToLookup|Añade los elementos a una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves.|No es aplicable.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Ejemplo de sintaxis de expresiones de consulta  
 El ejemplo de código siguiente usa la cláusula `group by` para agrupar los enteros de una lista según sean pares o impares.  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq>   
 [Información general sobre operadores de consulta estándar (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [group (cláusula)](../../../../csharp/language-reference/keywords/group-clause.md)   
 [Cómo: Crear grupos anidados](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)   
 [Cómo: Agrupar archivos por extensión (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)   
 [Cómo: Agrupar los resultados de consultas](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)   
 [Cómo: Realizar una subconsulta en una operación de agrupación](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)   
 [Cómo: Dividir un archivo en varios mediante el uso de grupos (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
