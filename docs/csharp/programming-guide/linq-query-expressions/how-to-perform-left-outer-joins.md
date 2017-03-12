---
redirect_url: /dotnet/articles/csharp/linq/perform-left-outer-joins
caps.handback.revision: 23
---
# C&#243;mo: Realizar operaciones de combinaci&#243;n externa izquierda (Gu&#237;a de programaci&#243;n de C#)
Una combinación externa izquierda es una combinación en la que se devuelve un resultado para cada elemento de la primera colección, independientemente de si éste tiene elementos correlacionados en la segunda colección.  Puede utilizar [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] para realizar una combinación externa izquierda llamando al método de <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en los resultados de una combinación agrupada.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el método <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en los resultados de una combinación agrupada para realizar una combinación externa izquierda.  
  
 El primer paso para generar una combinación externa izquierda de dos colecciones consiste en realizar una combinación interna utilizando una combinación agrupada.  \(Vea [Cómo: Realizar combinaciones internas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md) para obtener una explicación de este proceso.\) En este ejemplo, la lista de objetos de `Person` INNER\- está unida a la lista de objetos de `Pet` basándose en un objeto de `Person` que coincida con `Pet.Owner`.  
  
 El segundo paso consiste en incluir cada elemento de la primera colección \(izquierda\) en el conjunto de resultados, incluso cuando no haya coincidencias para el elemento en la colección derecha.  Esto se realiza llamando a <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en cada secuencia de elementos coincidentes de la combinación agrupada.  En este ejemplo, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> se llama en cada secuencia de objetos de `Pet` coincidentes.  El método devuelve una colección que contiene un único, valor predeterminado si la secuencia de objetos de `Pet` coincidentes está vacía para cualquier objeto de `Person`, con lo que cada objeto de `Person` se representa en la colección de resultados.  
  
> [!NOTE]
>  El valor predeterminado para un tipo de referencia es `null`; por consiguiente, el ejemplo busca una referencia null antes de tener acceso a cada elemento de cada colección de `Pet`.  
  
 [!code-cs[CsLINQProgJoining#7](../../../csharp/programming-guide/linq-query-expressions/codesnippet/csharp/Joins/joins.cs#7)]  
  
## Compilar el código  
  
-   Cree un nuevo proyecto de aplicación de consola en [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)].  
  
-   Agregue una referencia a System.Core.dll si ésta no existe aún.  
  
-   Incluya el espacio de nombres <xref:System.Linq>.  
  
-   Copie el código de ejemplo en el archivo program.cs, debajo del método de `Main` en la clase de `Program`.  Agregue una línea de código al método de `Main` para llamar al método de `LeftOuterJoinExample`.  
  
-   Ejecute el programa.  
  
## Vea también  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Cómo: Realizar combinaciones internas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Cómo: Realizar combinaciones agrupadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)