---
redirect_url: /dotnet/articles/csharp/linq/query-a-collection-of-objects
caps.handback.revision: 8
---
# C&#243;mo: Realizar una consulta en una colecci&#243;n de objetos (Gu&#237;a de programaci&#243;n de C#)
En este ejemplo se muestra cómo realizar una consulta simple en una lista de objetos `Student`.  Cada objeto `Student` contiene información básica sobre el alumno y una lista que representa las puntuaciones de éste en cuatro exámenes.  
  
 Esta aplicación actúa como marco de trabajo de muchos otros ejemplos de esta sección que utilizan el mismo origen de datos `students` .  
  
## Ejemplo  
 La consulta siguiente devuelve los alumnos que obtuvieron una puntuación de 90 o más en su primer examen.  
  
 [!code-cs[csProgGuideLINQ#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-query-a-collection-of-objects_1.cs)]  
  
 Esta consulta es deliberadamente simple para permitirle experimentar.  Por ejemplo, puede probar más predicados en la cláusula `where` o utiliza una cláusula `orderby` para ordenar los resultados.  
  
## Compilar el código  
  
-   Cree un proyecto de [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] para la versión 3.5 de .NET Framework.  De manera predeterminada, el proyecto incluye una referencia a System.Core.dll y una directiva `using` para el espacio de nombres System.Linq.  
  
-   Copie el código en el proyecto.  
  
-   Presione F5 para compilar y ejecutar el programa.  
  
-   Presione cualquier tecla para salir de la ventana de consola.  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)