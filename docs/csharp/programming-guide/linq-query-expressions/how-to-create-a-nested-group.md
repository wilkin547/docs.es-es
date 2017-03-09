---
redirect_url: /dotnet/articles/csharp/linq/create-a-nested-group
caps.handback.revision: 12
---
# C&#243;mo: Crear grupos anidados (Gu&#237;a de programaci&#243;n de C#)
En el ejemplo siguiente se muestra cómo crear grupos anidados en una expresión de consulta [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].  Cada grupo que se crea según el curso y el nivel académico se subdivide en grupos según los nombres de las personas.  
  
## Ejemplo  
 [!code-cs[csProgGuideLINQ#24](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#24)]  
  
 Observe que se requieren tres bucles `foreach` anidados para procesar una iteración en los elementos internos de un grupo anidado.  
  
## Compilar el código  
 Este ejemplo contiene referencias a objetos definidos en la aplicación de ejemplo del tema [Cómo: Consultar una colección de objetos](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md).  Para compilar y ejecutar este método, péguelo en la clase `StudentClass` de esa aplicación y agregue una llamada a éste desde el método `Main`.  
  
 Cuando adapte este método a su propia aplicación, recuerde que LINQ requiere la versión 3.5 de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] y que el proyecto debe contener una referencia a System.Core.dll y una directiva using para System.Linq.  Los tipos LINQ to SQL, LINQ to XML y LINQ to DataSet requieren directivas using y referencias adicionales.  Para obtener más información, vea [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)