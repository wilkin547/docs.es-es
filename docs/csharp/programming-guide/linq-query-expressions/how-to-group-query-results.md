---
redirect_url: /dotnet/articles/csharp/linq/group-query-results
caps.handback.revision: 19
---
# C&#243;mo: Agrupar los resultados de consultas (Gu&#237;a de programaci&#243;n de C#)
La agrupación es una de las funciones más eficaces de [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].  En los ejemplos siguientes se muestra cómo agrupar datos de distintas formas:  
  
-   Por una propiedad única.  
  
-   Por la primera letra de una propiedad de cadena.  
  
-   Por un intervalo numérico calculado.  
  
-   Por un predicado booleano u otra expresión.  
  
-   Por una clave compuesta.  
  
 Además, las dos últimas consultas proyectan sus resultados en un nuevo tipo anónimo que sólo contiene el nombre y el apellido del alumno.  Para obtener más información, vea [group \(cláusula\)](../../../csharp/language-reference/keywords/group-clause.md).  
  
## Ejemplo  
 Todos los ejemplos de este tema utilizan las clases auxiliares y los orígenes de datos siguientes.  
  
 [!code-cs[csProgGuideLINQ#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_1.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo agrupar elementos de origen utilizando una propiedad única del elemento como clave de grupo.  En este caso, la clave es `string`, el apellido del alumno.  También se puede utilizar una subcadena para la clave.  La operación de agrupación utiliza el comparador de igualdad predeterminado para el tipo.  
  
 Pegue el siguiente método en la clase `StudentClass`.  Cambie la instrucción de llamada del método `Main` a `sc.GroupBySingleProperty()`.  
  
 [!code-cs[csProgGuideLINQ#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_2.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo agrupar elementos de origen utilizando un elemento que no sea una propiedad del objeto para la clave de grupo.  En este ejemplo, la clave es la primera letra del apellido del alumno.  
  
 Pegue el siguiente método en la clase `StudentClass`.  Cambie la instrucción de llamada del método `Main` a `sc.GroupBySubstring()`.  
  
 [!code-cs[csProgGuideLINQ#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_3.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo agrupar elementos de origen utilizando un intervalo numérico como clave de grupo.  La consulta proyecta a continuación los resultados en un tipo anónimo que sólo contiene el nombre y el apellido del alumno y el intervalo percentil al que éste pertenece.  Se utiliza un tipo anónimo porque no es necesario utilizar el objeto `Student` completo para mostrar los resultados.  `GetPercentile` es una función auxiliar que calcula un percentil en función de la puntuación media del alumno.  El método devuelve un entero comprendido entre 0 y 10.  
  
 [!code-cs[csProgGuideLINQ#50](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_4.cs)]  
  
 Pegue el siguiente método en la clase `StudentClass`.  Cambie la instrucción de llamada del método `Main` a `sc.GroupByRange()`.  
  
 [!code-cs[csProgGuideLINQ#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_5.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo agrupar elementos de origen utilizando una expresión de comparación booleana.  En este ejemplo, la expresión booleana comprueba si la puntuación media de los exámenes de un alumno es mayor que 75.  Como en ejemplos anteriores, los resultados se proyectan en un tipo anónimo porque no se necesita el elemento de origen completo.  Tenga en cuenta que las propiedades del tipo anónimo pasan a ser propiedades del miembro `Key` y se puede tener acceso a las mismas por su nombre al ejecutar la consulta.  
  
 Pegue el siguiente método en la clase `StudentClass`.  Cambie la instrucción de llamada del método `Main` a `sc.GroupByBoolean()`.  
  
 [!code-cs[csProgGuideLINQ#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_6.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar un tipo anónimo para encapsular una clave que contiene varios valores.  En este ejemplo, el primer valor de clave es la primera letra del apellido del alumno.  El segundo valor de clave es un valor booleano que especifica si el alumno ha obtenido una puntuación superior a 85 en el primer examen.  Puede ordenar los grupos por cualquier propiedad de la clave.  
  
 Pegue el siguiente método en la clase `StudentClass`.  Cambie la instrucción de llamada del método `Main` a `sc.GroupByCompositeKey()`.  
  
 [!code-cs[csProgGuideLINQ#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_7.cs)]  
  
## Compilar el código  
 Copie y pegue cada método que desee probar en la clase `StudentClass`.  Agregue una instrucción de llamada para el método en el método `Main` y presione F5.  
  
 Cuando adapte estos métodos a su propia aplicación, recuerde que LINQ requiere la versión 3.5 o 4 de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] y que el proyecto debe contener una referencia a System.Core.dll y una directiva using para System.Linq.  Los tipos LINQ to SQL, LINQ to XML y LINQ to DataSet requieren directivas using y referencias adicionales.  Para obtener más información, vea [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Vea también  
 <xref:System.Linq.Enumerable.GroupBy%2A>   
 <xref:System.Linq.IGrouping%602>   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group \(cláusula\)](../../../csharp/language-reference/keywords/group-clause.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Cómo: Realizar una subconsulta en una operación de agrupación](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)   
 [Cómo: Crear grupos anidados](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)   
 [Grouping Data](../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)