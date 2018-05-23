---
title: Información general sobre operadores de consulta estándar (C#)
ms.date: 07/20/2015
ms.assetid: 812fa119-5f65-4139-b4fa-55dccd8dc3ac
ms.openlocfilehash: 36bd5927e64ffacb97beac28b8e7790204e08c5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="standard-query-operators-overview-c"></a>Información general sobre operadores de consulta estándar (C#)
Los *operadores de consulta estándar* son los métodos que constituyen el modelo LINQ. La mayoría de estos métodos funciona en secuencias; donde una secuencia es un objeto cuyo tipo implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> o la interfaz <xref:System.Linq.IQueryable%601>. Los operadores de consulta estándar ofrecen funcionalidades de consulta, como las funciones de filtrado, proyección, agregación y ordenación, entre otras.  
  
 Hay dos conjuntos de operadores de consulta estándar de LINQ, uno que actúa sobre objetos de tipo <xref:System.Collections.Generic.IEnumerable%601> y otro que actúa en objetos de tipo <xref:System.Linq.IQueryable%601>. Los métodos que forman cada conjunto son miembros estáticos de las clases <xref:System.Linq.Enumerable> y <xref:System.Linq.Queryable>, respectivamente. Se definen como *métodos de extensión* del tipo en el que actúan. Esto significa que se pueden llamar mediante sintaxis de método estático o sintaxis de método de instancia.  
  
 Además, varios métodos de operador de consulta estándar funcionan en tipos distintos de los que se basan en <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>. El tipo <xref:System.Linq.Enumerable> define dos métodos que funcionan en objetos de tipo <xref:System.Collections.IEnumerable>. Estos métodos, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> y <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, le permiten habilitar una colección no genérica o no parametrizada para consultarse en el patrón LINQ. Para ello, se crea una colección de objetos fuertemente tipados. La clase <xref:System.Linq.Queryable> define dos métodos similares, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> y <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, que funcionan en objetos de tipo <xref:System.Linq.Queryable>.  
  
 Los operadores de consulta estándar difieren en sus intervalos de ejecución, dependiendo de que devuelvan un valor singleton o una secuencia de valores. Esos métodos que devuelven un valor singleton (por ejemplo, <xref:System.Linq.Enumerable.Average%2A> y <xref:System.Linq.Enumerable.Sum%2A>) se ejecutan inmediatamente. Los métodos que devuelven una secuencia aplazan la ejecución de la consulta y devuelven un objeto enumerable.  
  
 En el caso de los métodos que actúan en colecciones en memoria, es decir, los métodos que extienden <xref:System.Collections.Generic.IEnumerable%601>, el objeto enumerable devuelto captura los argumentos que se han pasado al método. Cuando se enumera ese objeto, se emplea la lógica del operador de consulta y se devuelven los resultados de la consulta.  
  
 En cambio, los métodos que extienden <xref:System.Linq.IQueryable%601> no implementan ningún comportamiento de consulta, pero crean un árbol de la expresión que representa la consulta que se va a realizar. El procesamiento de consultas se controla mediante el objeto <xref:System.Linq.IQueryable%601> de origen.  
  
 Las llamadas a métodos de consulta se pueden encadenar juntas en una consulta, lo que permite que las consultas se conviertan en complejas de forma arbitraria.  
  
 En el ejemplo de código siguiente se muestra el uso de los operadores de consulta estándar para obtener información sobre una secuencia.  
  
```csharp  
string sentence = "the quick brown fox jumps over the lazy dog";  
// Split the string into individual words to create a collection.  
string[] words = sentence.Split(' ');  
  
// Using query expression syntax.  
var query = from word in words  
            group word.ToUpper() by word.Length into gr  
            orderby gr.Key  
            select new { Length = gr.Key, Words = gr };  
  
// Using method-based query syntax.  
var query2 = words.  
    GroupBy(w => w.Length, w => w.ToUpper()).  
    Select(g => new { Length = g.Key, Words = g }).  
    OrderBy(o => o.Length);  
  
foreach (var obj in query)  
{  
    Console.WriteLine("Words of length {0}:", obj.Length);  
    foreach (string word in obj.Words)  
        Console.WriteLine(word);  
}  
  
// This code example produces the following output:  
//  
// Words of length 3:  
// THE  
// FOX  
// THE  
// DOG  
// Words of length 4:  
// OVER  
// LAZY  
// Words of length 5:  
// QUICK  
// BROWN  
// JUMPS   
```  
  
## <a name="query-expression-syntax"></a>Sintaxis de expresiones de consulta  
 Algunos de los operadores de consulta estándar que se usan con más frecuencia tienen una sintaxis especial de palabras clave dedicadas de lenguaje C# y Visual Basic para que se puedan invocar como parte de una *expresión* *de consulta*. Para obtener más información sobre los operadores de consulta estándar que incluyen palabras clave dedicadas y sus sintaxis correspondientes, vea [Query Expression Syntax for Standard Query Operators (C#)](../../../../csharp/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md) (Sintaxis de las expresiones de consulta para operadores de consulta estándar [C#]).  
  
## <a name="extending-the-standard-query-operators"></a>Extender los operadores de consulta estándar  
 Puede aumentar el conjunto de operadores de consulta estándar creando métodos específicos de dominio que sean adecuados para su tecnología o dominio de destino. También puede reemplazar los operadores de consulta estándar con sus propias implementaciones que proporcionen otros servicios tales como evaluación remota, traducción de consultas y optimización. Vea <xref:System.Linq.Enumerable.AsEnumerable%2A> para obtener un ejemplo.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Los vínculos siguientes le llevan a temas que ofrecen información adicional sobre los distintos operadores de consulta estándar según la funcionalidad.  
  
 [Sorting Data (C#)](../../../../csharp/programming-guide/concepts/linq/sorting-data.md) (Ordenación de datos [C#])  
  
 [Set Operations (C#)](../../../../csharp/programming-guide/concepts/linq/set-operations.md) (Operaciones set [C#])  
  
 [Filtering Data (C#)](../../../../csharp/programming-guide/concepts/linq/filtering-data.md) (Filtrado de datos [C#])  
  
 [Quantifier Operations (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md) (Operaciones cuantificadoras [C#])  
  
 [Projection Operations (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md) (Operaciones de proyección [C#])  
  
 [Partitioning Data](../../../../csharp/programming-guide/concepts/linq/partitioning-data.md) (Realizar particiones de datos [C#])  
  
 [Join Operations (C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md) (Operaciones de combinación [C#])  
  
 [Grouping Data (C#)](../../../../csharp/programming-guide/concepts/linq/grouping-data.md) (Agrupar datos [C#])  
  
 [Generation Operations (C#)](../../../../csharp/programming-guide/concepts/linq/generation-operations.md) (Operaciones de generación [C#])  
  
 [Equality Operations (C#)](../../../../csharp/programming-guide/concepts/linq/equality-operations.md) (Operaciones de igualdad [C#])  
  
 [Element Operations (C#)](../../../../csharp/programming-guide/concepts/linq/element-operations.md) (Operaciones de elementos [C#])  
  
 [Converting Data Types (C#)](../../../../csharp/programming-guide/concepts/linq/converting-data-types.md) (Convertir tipos de datos [C#])  
  
 [Concatenation Operations (C#)](../../../../csharp/programming-guide/concepts/linq/concatenation-operations.md) (Operaciones de concatenación [C#])  
  
 [Aggregation Operations (C#)](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md) (Operaciones de agregación [C#])  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.Enumerable>  
 <xref:System.Linq.Queryable>  
 [Introducción a las consultas LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 [Sintaxis de las expresiones de consulta para operadores de consulta estándar (C#)](../../../../csharp/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)  
 [Clasificación de operadores de consulta estándar por modo de ejecución (C#)](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)  
 [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
