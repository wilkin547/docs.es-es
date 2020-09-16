---
title: Operadores de consulta estándar en consultas de LINQ to Entities
ms.date: 08/21/2018
ms.assetid: 7fa55a9b-6219-473d-b1e5-2884a32dcdff
ms.openlocfilehash: a61296d924ab1ff32b5bee523d6f0a06dda95db3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557780"
---
# <a name="standard-query-operators-in-linq-to-entities-queries"></a>Operadores de consulta estándar en consultas de LINQ to Entities
En una consulta, se especifica la información que se desea recuperar del origen de datos. Una consulta también puede especificar cómo se debe ordenar, agrupar y conformar esa información antes de que se devuelva. LINQ proporciona un conjunto de métodos de consulta estándar que se puede utilizar en una consulta. La mayoría de estos métodos funciona en secuencias; en este contexto, una secuencia es un objeto cuyo tipo implementa la <xref:System.Collections.Generic.IEnumerable%601> interfaz o la <xref:System.Linq.IQueryable%601> interfaz. La funcionalidad de consulta de los operadores de consulta estándar incluye las operaciones de filtrado, proyección, agregación, ordenación, agrupamiento y paginación, entre otras. Algunos de los operadores de consulta estándar que se usan con más frecuencia tienen una sintaxis de palabras clave especial para que se puedan invocar utilizando la sintaxis de las expresiones de consulta. Una expresión de consulta constituye una forma diferente de expresar una consulta, más legible que su equivalente basada en métodos. Las cláusulas de las expresiones de consulta se convierten en llamadas a los métodos de consulta en tiempo de compilación. Para obtener una lista de operadores de consulta estándar que tienen cláusulas de expresión de consulta equivalentes, vea [información general sobre operadores de consulta estándar](/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).  
  
 No todos los operadores de consulta estándar se admiten en consultas de LINQ to Entities. Para obtener más información, vea [métodos LINQ admitidos y no admitidos (LINQ to Entities)](supported-and-unsupported-linq-methods-linq-to-entities.md). En este tema se proporciona información sobre los operadores de consulta estándar que son específicos de LINQ to Entities. Para obtener más información acerca de los problemas conocidos de las consultas de LINQ to Entities, consulte [problemas conocidos y consideraciones en LINQ to Entities](known-issues-and-considerations-in-linq-to-entities.md).  
  
## <a name="projection-and-filtering-methods"></a>Métodos de proyección y filtrado  
 La *proyección* hace referencia a la transformación de los elementos de un conjunto de resultados en un formato deseado. Por ejemplo, se puede proyectar un subconjunto de las propiedades que se necesitan de cada objeto del conjunto de resultados, se puede proyectar una propiedad y realizar un cálculo matemático con ella, o se puede proyectar el objeto completo del conjunto de resultados. Los métodos de proyección son `Select` y `SelectMany`.  
  
 El *filtrado* hace referencia a la operación de restringir el conjunto de resultados para que contenga solo los elementos que coinciden con una condición especificada. El método de filtrado es `Where`.  
  
 En LINQ to Entities se admiten la mayoría de las sobrecargas de los métodos de proyección y de filtrado, con la excepción de los que aceptan un argumento posicional.  
  
## <a name="join-methods"></a>Métodos de combinación  
 La combinación es una operación importante de las consultas dirigidas a orígenes de datos que no tienen relaciones navegables entre sí. Una combinación de dos orígenes de datos es la asociación de objetos en un origen de datos con objetos de otro origen de datos que comparten un atributo o propiedad comunes. Los métodos de combinación son `Join` y `GroupJoin`.  
  
 Se admiten la mayoría de las sobrecargas de los métodos de combinación, a excepción de las que usan <xref:System.Collections.Generic.IEqualityComparer%601>. Esto se debe a que el comparador no se puede convertir en el origen de datos.  
  
## <a name="set-methods"></a>Métodos Set  
 Las operaciones Set de LINQ son operaciones de consulta que basan sus conjuntos de resultados en la presencia o ausencia de elementos equivalentes dentro de la misma o de otra colección (o conjunto). Los métodos Set son `All`, `Any`, `Concat`, `Contains`, `DefaultIfEmpty`, `Distinct`, `EqualAll`, `Except`, `Intersect` y `Union`.  
  
 La mayoría de las sobrecargas de los métodos set se admiten en LINQ to Entities, aunque hay algunas diferencias en el comportamiento en comparación con LINQ to Objects. Sin embargo, los métodos set que usan <xref:System.Collections.Generic.IEqualityComparer%601> no se admiten porque el comparador no se puede convertir en el origen de datos.  
  
## <a name="ordering-methods"></a>Métodos de ordenación  
 La ordenación hace referencia a la forma de ordenar los elementos de un conjunto de resultados según uno o varios atributos. Si se especifica más de un criterio de ordenación, se pueden romper los enlaces dentro de un grupo.  
  
 Se admiten la mayoría de las sobrecargas de los métodos de ordenación, a excepción de las que usan <xref:System.Collections.Generic.IComparer%601>. Esto se debe a que el comparador no se puede convertir en el origen de datos. Los métodos de ordenación son `OrderBy`, `OrderByDescending`, `ThenBy`, `ThenByDescending` y `Reverse`.  
  
 Dado que la consulta se ejecuta en el origen de datos, el comportamiento de la ordenación puede diferir de las consultas ejecutadas en CLR. Esto se debe a que las opciones de ordenación, como la ordenación por mayúsculas y minúsculas, la ordenación kanji y la ordenación por NULL, se pueden establecer en el origen de datos. Dependiendo del origen de datos, estas opciones de ordenación pueden generar resultados diferentes a los obtenidos en CLR.  
  
 Si se especifica el mismo selector de claves en más de una operación de ordenación, se generará una ordenación duplicada. Esto no es válido y se producirá una excepción.  
  
## <a name="grouping-methods"></a>Métodos de agrupamiento  
 El agrupamiento hace referencia a la operación de colocar los datos en grupos de manera que los elementos de cada grupo compartan un atributo común. El método de agrupamiento es `GroupBy`.  
  
 Se admiten la mayoría de las sobrecargas de los métodos de agrupamiento, a excepción de las que usan <xref:System.Collections.Generic.IEqualityComparer%601>. Esto se debe a que el comparador no se puede convertir en el origen de datos.  
  
 Los métodos de agrupamiento se asignan al origen de datos utilizando una subconsulta distinta para el selector de claves. La subconsulta de comparación del selector de claves se ejecuta utilizando la semántica del origen de datos, incluidos los problemas relacionados con la comparación de valores `null`.  
  
## <a name="aggregate-methods"></a>Métodos de agregación  
 Una operación de agregación calcula un valor único a partir de una colección de valores. Por ejemplo, el cálculo de la temperatura media diaria a partir de los valores de la temperatura diaria de un mes es una operación de agregación. Los métodos de agregación son `Aggregate`, `Average`, `Count`, `LongCount`, `Max`, `Min` y `Sum`.  
  
 Se admite la mayor parte de las sobrecargas de los métodos de agregación. Para el comportamiento relacionado con valores NULL, los métodos de agregación utilizan la semántica del origen de datos. El comportamiento de los métodos de agregación cuando hay valores NULL implicados puede ser diferente, en función de qué origen de datos back-end se esté utilizando. El comportamiento de los métodos de agregación que usa la semántica del origen de datos también puede ser diferente de lo que cabe esperar de los métodos CLR. Por ejemplo, el comportamiento predeterminado para el método `Sum` en SQL Server es omitir cualquier valor NULL en lugar de producir una excepción.  
  
 Las excepciones derivadas de la agregación, como un desbordamiento de la función `Sum`, se producen como excepciones del origen de datos o como excepciones de Entity Framework durante la materialización de los resultados de la consulta.  
  
 En el caso de los métodos que implican un cálculo sobre una secuencia, como `Sum` o `Average`, el cálculo real se realiza en el servidor. Como consecuencia, pueden producirse en el servidor conversiones de tipos y pérdida de precisión, y los resultados pueden diferir de lo que se espera al usar la semántica de CLR.  
  
 El comportamiento predeterminado de los métodos de agregación para valores NULL y NO NULL se muestra en la tabla siguiente:  
  
|Método|Sin datos|Todos los valores NULL|Algunos valores NULL|Valores NO NULL|  
|------------|-------------|---------------------|----------------------|--------------------|  
|`Average`|Devuelve NULL.|Devuelve NULL.|Devuelve el promedio de todos los valores NO NULL de una secuencia.|Calcula el promedio de una secuencia de valores numéricos.|  
|`Count`|Devuelve 0.|Devuelve el número de valores NULL de la secuencia.|Devuelve el número de valores NULL y NO NULL de la secuencia.|Devuelve el número de elementos de la secuencia.|  
|`Max`|Devuelve NULL.|Devuelve NULL.|Devuelve el valor NO NULL máximo de una secuencia.|Devuelve el valor máximo de una secuencia.|  
|`Min`|Devuelve NULL.|Devuelve NULL.|Devuelve el valor NO NULL mínimo de una secuencia.|Devuelve el valor mínimo de una secuencia.|  
|`Sum`|Devuelve NULL.|Devuelve NULL.|Devuelve la suma del valor NO NULL de una secuencia.|Calcula la suma de una secuencia de valores numéricos.|  
  
## <a name="type-methods"></a>Métodos de tipos  
 Los dos métodos LINQ que se ocupan de la conversión y prueba de tipos se admiten en el contexto de la Entity Framework. Esto significa que los únicos tipos admitidos son tipos que se asignan al tipo de Entity Framework adecuado. Para obtener una lista de estos tipos, vea [tipos de modelos conceptuales (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl). Los métodos de tipos son `Convert` y `OfType`.  
  
 `OfType` se admite para los tipos de entidad. `Convert` se admite para los tipos primitivos de modelo conceptual.  Los métodos de C# `is` y `as` también se admiten.  
  
## <a name="paging-methods"></a>Métodos de paginación  
 Las operaciones de paginación devuelven un único elemento o varios elementos de una secuencia. Los métodos de paginación admitidos son `First` ,, `FirstOrDefault` `Single` , `SingleOrDefault` , `Skip` y `Take` .  
  
 No se admiten varios métodos de paginación, debido a la incapacidad de asignar funciones al origen de datos o a la falta de ordenación implícita de los conjuntos en el origen de datos. Los métodos que devuelven un valor predeterminado están restringidos a los tipos primitivos de modelo conceptual y los tipos de referencia con valores predeterminados NULL. Los métodos de paginación que se ejecuten en una secuencia vacía devolverán NULL.  
  
## <a name="see-also"></a>Vea también

- [Métodos de LINQ compatibles y no compatibles (LINQ to Entities)](supported-and-unsupported-linq-methods-linq-to-entities.md)
- [Información general sobre operadores de consulta estándar](/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120))
