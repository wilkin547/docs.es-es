---
redirect_url: /dotnet/articles/csharp/linq/perform-grouped-joins
caps.handback.revision: 23
---
# C&#243;mo: Realizar combinaciones agrupadas (Gu&#237;a de programaci&#243;n de C#)
La combinación agrupada es útil para generar estructuras de datos jerárquicas.  Empareja cada elemento de la primera colección con un conjunto de elementos correlacionados de la segunda colección.  
  
 Por ejemplo, una clase o una tabla de base de datos relacional denominada Student podría contener dos campos: Id y Name.  Una segunda clase o tabla de base de datos relacional denominada Course podría contener dos campos: StudentId y CourseTitle.  Una combinación agrupada de estos dos orígenes de datos, basada en la coincidencia de Student.Id y Course.StudentId, agruparía cada elemento de Student con una colección de objetos de Course \(que podría estar vacía\).  
  
> [!NOTE]
>  Cada elemento de la primera colección aparece en el conjunto de resultados de una combinación agrupada, independientemente de si se encuentran elementos correlacionados en la segunda colección.  En caso de que no se encuentren elementos que puedan correlacionarse, la secuencia de elementos correlacionados para ese elemento está vacía.  El selector de resultados tiene acceso a cada elemento de la primera colección.  Esto se diferencia de una combinación no agrupada, donde el selector de resultados no puede tener acceso a elementos de la primera colección que no tengan ninguna coincidencia en la segunda colección.  
  
 En el primer ejemplo de este tema se muestra cómo realizar una combinación agrupada.  En el segundo ejemplo se muestra cómo utilizar una combinación agrupada para crear elementos XML.  
  
## Ejemplo  
  
### Ejemplo de combinación agrupada  
 http:\/\/go.microsoft.com\/fwlink\/?LinkId\=44293En el ejemplo siguiente se realiza una combinación agrupada de objetos de tipo `Person` y `Pet` basada en elementos `Person` que coinciden con la propiedad `Pet.Owner`.  A diferencia de una combinación no agrupada, que generaría un par de elementos para cada coincidencia, la combinación agrupada sólo genera un objeto resultante para cada elemento de la primera colección, que en este ejemplo es un objeto `Person`.  Los elementos correspondientes de la segunda colección, que en este ejemplo son objetos `Pet`, se agrupan en una colección.  Finalmente, la función de selector de resultados crea un tipo anónimo para cada coincidencia formada por `Person.FirstName` y una colección de objetos `Pet`.  
  
 [!code-cs[CsLINQProgJoining#5](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-grouped-joins_1.cs)]  
  
## Ejemplo  
  
### Ejemplo de combinación agrupada para crear XML  
 Las combinaciones agrupadas son ideales para crear XML utilizando [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  El ejemplo siguiente es similar al anterior, salvo que en lugar de crear tipos anónimos, la función de selector de resultados crea elementos XML que representan los objetos combinados.  Para obtener más información sobre [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)], vea [LINQ to XML](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
 [!code-cs[CsLINQProgJoining#6](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-grouped-joins_2.cs)]  
  
## Compilar el código  
  
-   Cree un nuevo proyecto de **Aplicación de consola** en [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)].  
  
-   Agregue una referencia a System.Core.dll y a System.Xml.Linq.dll si ésta no existe aún.  
  
-   Incluya los espacios de nombres <xref:System.Linq> y <xref:System.Xml.Linq>.  
  
-   Copie el código del ejemplo y péguelo en el archivo program.cs , bajo el método `Main`.  Agregue una línea de código al método `Main` para llamar al método que pegó.  
  
-   Ejecute el programa.  
  
## Vea también  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Cómo: Realizar combinaciones internas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Cómo: Realizar operaciones de combinación externa izquierda](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [LINQ to XML](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)