---
title: Operaciones básicas de consulta LINQ (C#)
description: Descubra las expresiones de consulta LINQ y algunas de las operaciones que puede realizar en una consulta.
ms.date: 07/20/2015
helpviewer_keywords:
- orderby clause [LINQ in C#]
- ordering data [LINQ in C#]
- selecting data [LINQ in C#]
- queries [LINQ in C#], basic operations
- grouping data [LINQ in C#]
- data sources [LINQ in C#]
- sorting data [LINQ in C#]
- projections [LINQ in C#]
- filtering data [LINQ in C#]
- joining data [LINQ in C#]
- select clause [LINQ in C#]
- LINQ [C#], basic query operations
- join clause [LINQ in C#]
- group clause [LINQ in C#]
ms.assetid: a7ea3421-1cf4-4df7-832a-aa22fe6379e9
ms.openlocfilehash: d9653be8b67ef4d971c157b8dd8d82b2ae3c2287
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105530"
---
# <a name="basic-linq-query-operations-c"></a>Operaciones básicas de consulta LINQ (C#)
En este tema se ofrece una breve introducción a las expresiones de consulta LINQ y algunas de las clases de operaciones típicas que se realizan en una consulta. En los temas siguientes se ofrece información más detallada:  
  
 [Expresiones de consulta LINQ](../../../linq/index.md)  
  
 [Información general sobre operadores de consulta estándar (C#)](./standard-query-operators-overview.md)  
  
 [Tutorial: Creación de consultas en C#](./walkthrough-writing-queries-linq.md)  
  
> [!NOTE]
> Si ya está familiarizado con un lenguaje de consultas como SQL o XQuery, puede omitir la mayoría de este tema. Lea la parte dedicada a la "cláusula `from`" en la sección siguiente para obtener información sobre el orden de las cláusulas en las expresiones de consulta LINQ.  
  
## <a name="obtaining-a-data-source"></a>Obtener un origen de datos  
 En una consulta LINQ, el primer paso es especificar el origen de datos. En C#, como en la mayoría de los lenguajes de programación, se debe declarar una variable antes de poder usarla. En una consulta LINQ, la cláusula `from` aparece en primer lugar para introducir el origen de datos (`customers`) y la *variable de rango* (`cust`).  
  
 [!code-csharp[csLINQGettingStarted#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#23)]  
  
 La variable de rango es como la variable de iteración en un bucle `foreach`, con la diferencia de que en una expresión de consulta realmente no se produce ninguna iteración. Cuando se ejecuta la consulta, la variable de rango actúa como referencia para cada elemento sucesivo de `customers`. Dado que el compilador puede deducir el tipo de `cust`, no tiene que especificarlo explícitamente. Una cláusula `let` puede introducir variables de rango adicionales. Para obtener más información, vea [let (Cláusula)](../../../language-reference/keywords/let-clause.md).  
  
> [!NOTE]
> Para los orígenes de datos no genéricos, como <xref:System.Collections.ArrayList>, el tipo de la variable de rango debe establecerse explícitamente. Para más información, consulte el [procedimiento para consultar un objeto ArrayList con LINQ (C#)](./how-to-query-an-arraylist-with-linq.md) y [Cláusula from](../../../language-reference/keywords/from-clause.md).  
  
## <a name="filtering"></a>Filtrado  
 Probablemente la operación de consulta más común es aplicar un filtro en forma de expresión booleana. El filtro hace que la consulta devuelva solo los elementos para los que la expresión es verdadera. El resultado se genera mediante la cláusula `where`. El filtro aplicado especifica qué elementos se deben excluir de la secuencia de origen. En el ejemplo siguiente, solo se devuelven los `customers` cuya dirección se encuentra en Londres.  
  
 [!code-csharp[csLINQGettingStarted#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#24)]  
  
 Puede usar los operadores lógicos `AND` y `OR` de C#, con los que ya estará familiarizado, para aplicar las expresiones de filtro que sean necesarias en la cláusula `where`. Por ejemplo, para devolver solo los clientes con dirección en "London" `AND` cuyo nombre sea "Devon", escribiría el código siguiente:  
  
 [!code-csharp[csLINQGettingStarted#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#25)]  
  
 Para devolver los clientes con dirección en Londres o París, escribiría el código siguiente:  
  
 [!code-csharp[csLINQGettingStarted#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#26)]  
  
 Para obtener más información, vea [where (Cláusula)](../../../language-reference/keywords/where-clause.md).  
  
## <a name="ordering"></a>Ordenación  
 A menudo es necesario ordenar los datos devueltos. La cláusula `orderby` hará que los elementos de la secuencia devuelta se ordenen según el comparador predeterminado del tipo que se va a ordenar. Por ejemplo, la consulta siguiente se puede extender para ordenar los resultados según la propiedad `Name`. Dado que `Name` es una cadena, el comparador predeterminado realiza una ordenación alfabética de la A a la Z.  
  
 [!code-csharp[csLINQGettingStarted#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#27)]  
  
 Para ordenar los resultados en orden inverso, de la Z a la A, use la cláusula `orderby…descending`.  
  
 Para obtener más información, vea [orderby (Cláusula)](../../../language-reference/keywords/orderby-clause.md).  
  
## <a name="grouping"></a>Agrupar  
 La cláusula `group` permite agrupar los resultados según la clave que se especifique. Por ejemplo, podría especificar que los resultados se agrupen por `City` para que todos los clientes de London o París estén en grupos individuales. En este caso, la clave es `cust.City`.  
  
 [!code-csharp[csLINQGettingStarted#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#28)]  
  
 Al finalizar una consulta con una cláusula `group`, los resultados adoptan la forma de una lista de listas. Cada elemento de la lista es un objeto que tiene un miembro `Key` y una lista de elementos agrupados bajo esa clave. Al procesar una iteración en una consulta que genera una secuencia de grupos, debe usar un bucle `foreach` anidado. El bucle exterior recorre en iteración cada grupo y el bucle interior recorre en iteración los miembros de cada grupo.  
  
 Si debe hacer referencia a los resultados de una operación de grupo, puede usar la palabra clave `into` para crear un identificador con el que se puedan realizar más consultas. La consulta siguiente devuelve solo los grupos que contienen más de dos clientes:  
  
 [!code-csharp[csLINQGettingStarted#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#29)]  
  
 Para obtener más información, vea [group (Cláusula)](../../../language-reference/keywords/group-clause.md).  
  
## <a name="joining"></a>Combinación  
 Las operaciones de combinación crean asociaciones entre las secuencias que no se modelan explícitamente en los orígenes de datos. Por ejemplo, puede realizar una combinación para buscar todos los clientes y distribuidores que tengan la misma ubicación. En LINQ, la cláusula `join` funciona siempre con colecciones de objetos, en lugar de con tablas de base de datos directamente.  
  
 [!code-csharp[csLINQGettingStarted#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#36)]  
  
 En LINQ no es necesario usar `join` tan a menudo como en SQL, porque las claves externas en LINQ se representan en el modelo de objetos como propiedades que contienen una colección de elementos. Por ejemplo, un objeto `Customer` contiene una colección de objetos `Order`. En lugar de realizar una combinación, tiene acceso a los pedidos usando la notación de punto:  
  
```csharp
from order in Customer.Orders...  
```  
  
 Para obtener más información, vea [join (Cláusula, Referencia de C#)](../../../language-reference/keywords/join-clause.md).  
  
## <a name="selecting-projections"></a>Selección (proyecciones)  
 La cláusula `select` genera resultados de consulta y especifica la "forma" o el tipo de cada elemento devuelto. Por ejemplo, puede especificar si sus resultados estarán compuestos de objetos `Customer` completos, un solo miembro, un subconjunto de miembros o algún tipo de resultado completamente diferente basado en un cálculo o en un objeto nuevo. Cuando la cláusula `select` genera algo distinto de una copia del elemento de origen, la operación se denomina *proyección*. El uso de proyecciones para transformar los datos es una función eficaz de las expresiones de consulta LINQ. Para obtener más información, vea [Transformaciones de datos con LINQ (C#)](./data-transformations-with-linq.md) y [select (cláusula)](../../../language-reference/keywords/select-clause.md).  
  
## <a name="see-also"></a>Consulte también

- [Expresiones de consulta LINQ](../../../linq/index.md)
- [Tutorial: Creación de consultas en C#](./walkthrough-writing-queries-linq.md)
- [Palabras clave para consultas (LINQ)](../../../language-reference/keywords/query-keywords.md)
- [Tipos anónimos](../../classes-and-structs/anonymous-types.md)
