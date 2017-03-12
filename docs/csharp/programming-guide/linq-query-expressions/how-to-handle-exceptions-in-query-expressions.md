---
redirect_url: /dotnet/articles/csharp/linq/handle-exceptions-in-query-expressions
caps.handback.revision: 15
---
# C&#243;mo: Controlar excepciones con expresiones de consultas (Gu&#237;a de programaci&#243;n de C#)
Es posible llamar a cualquier método en el contexto de una expresión de consulta.  Sin embargo, se recomienda que evite llamar a cualquier método en una expresión de consulta que pueda crear un efecto secundario, como modificar el contenido del origen de datos o producir una excepción.  En este ejemplo se muestra cómo evitar que se produzcan excepciones al llamar a métodos en una expresión de consulta sin infringir las directrices generales de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] sobre el control de excepciones.  Dichas directrices indican que es aceptable detectar una excepción específica cuando se entiende por qué se producirá en un contexto determinado.  Para obtener más información, vea [Procedimientos recomendados para excepciones](../Topic/Best%20Practices%20for%20Exceptions.md).  
  
 En el último ejemplo se muestra cómo controlar los casos en los que se debe producir una excepción durante la ejecución de una consulta.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo mover código de control de excepciones fuera de una expresión de consulta.  Esto sólo es posible cuando el método no depende de variables locales de la consulta.  
  
 [!code-cs[csProgGuideLINQ#10](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#10)]  
  
## Ejemplo  
 En algunos casos, la mejor respuesta a una excepción que se produce desde una consulta puede ser detener la ejecución de la consulta inmediatamente.  En el ejemplo siguiente se muestra cómo controlar excepciones que pueden producirse desde el cuerpo de una consulta.  Suponga que `SomeMethodThatMightThrow` puede producir una excepción que requiere que se detenga la ejecución de la consulta.  
  
 Observe que el bloque `try` incluye el bucle `foreach` y no la consulta en sí.  Esto se debe a que el bucle `foreach` es el punto en el que se ejecuta la consulta realmente.  Para obtener más información, vea [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!code-cs[csProgGuideLINQ#12](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#12)]  
  
## Compilar el código  
  
-   Cree un proyecto de [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] para la versión 3.5 de .NET Framework.  De manera predeterminada, el proyecto incluye una referencia a System.Core.dll y una directiva `using` para el espacio de nombres System.Linq.  
  
-   Copie el código en el proyecto.  
  
-   Presione F5 para compilar y ejecutar el programa.  
  
 Presione cualquier tecla para salir de la ventana de consola.  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)