---
redirect_url: /dotnet/articles/csharp/linq/perform-a-subquery-on-a-grouping-operation
caps.handback.revision: 15
---
# C&#243;mo: Realizar una subconsulta en una operaci&#243;n de agrupaci&#243;n (Gu&#237;a de programaci&#243;n de C#)
En este tema se muestran dos formas distintas de crear una consulta que ordena los datos de origen en grupos y, a continuación, realiza una subconsulta en cada grupo individualmente.  La técnica básica de cada ejemplo consiste en agrupar los elementos de origen utilizando una *continuación* denominada `newGroup` y, a continuación, generar una nueva subconsulta en `newGroup`.  Esta subconsulta se ejecuta en cada grupo nuevo creado por la consulta externa.  Tenga en cuenta que en este ejemplo determinado el resultado final no es un grupo, sino una secuencia simple de tipos anónimos.  
  
 Para obtener más información sobre cómo agrupar, vea [group \(cláusula\)](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Para obtener más información sobre las continuaciones, vea [into](../../../csharp/language-reference/keywords/into.md).  En el ejemplo siguiente se utiliza una estructura de datos en memoria como origen de datos, pero se aplican los mismos principios a cualquier tipo de origen de datos [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].  
  
## Ejemplo  
 [!code-cs[csProgGuideLINQ#23](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#23)]  
  
## Compilar el código  
 Este ejemplo contiene referencias a objetos definidos en la aplicación de ejemplo del tema [Cómo: Consultar una colección de objetos](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md).  Para compilar y ejecutar este método, péguelo en la clase `StudentClass` de esa aplicación y agregue una llamada a éste desde el método `Main`.  
  
 Cuando adapte este método a su propia aplicación, recuerde que LINQ requiere la versión 3.5 de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] y que el proyecto debe contener una referencia a System.Core.dll y una directiva using para System.Linq.  Los tipos LINQ to SQL, LINQ to XML y LINQ to DataSet requieren directivas using y referencias adicionales.  Para obtener más información, vea [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)