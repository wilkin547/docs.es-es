---
redirect_url: /dotnet/articles/csharp/linq/store-the-results-of-a-query-in-memory
caps.handback.revision: 13
---
# C&#243;mo: Almacenar los resultados de una consulta en la memoria (Gu&#237;a de programaci&#243;n de C#)
Una consulta es básicamente un conjunto de instrucciones sobre cómo recuperar y organizar datos.  Para ejecutarse, la consulta requiere una llamada a su método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.  Esta llamada se realiza al utilizar un bucle `foreach` para procesar una iteración en los elementos.  Para evaluar una consulta y almacenar los resultados sin ejecutar un bucle de `foreach`, simplemente llame a uno de los métodos siguientes en la variable de consulta:  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 Cuando almacene los resultados de la consulta, se recomienda que asigne el objeto de colección devuelto a una nueva variable, como se muestra en el ejemplo siguiente:  
  
## Ejemplo  
 [!code-cs[csProgGuideLINQ#25](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#25)]  
  
## Compilar el código  
  
-   Cree un proyecto de [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] para la versión 3.5 de .NET Framework.  De manera predeterminada, el proyecto incluye una referencia a System.Core.dll y una directiva `using` para el espacio de nombres System.Linq.  
  
-   Copie el código en el proyecto.  
  
-   Presione F5 para compilar y ejecutar el programa.  
  
-   Presione cualquier tecla para salir de la ventana de consola.  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)