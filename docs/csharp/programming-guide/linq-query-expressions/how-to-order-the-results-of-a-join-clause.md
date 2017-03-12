---
redirect_url: /dotnet/articles/csharp/linq/order-the-results-of-a-join-clause
caps.handback.revision: 6
---
# C&#243;mo: Ordenar los resultados de una cl&#225;usula join (Gu&#237;a de programaci&#243;n de C#)
Este ejemplo muestra cómo ordenar los resultados de una operación de unión \(join\).  Observe que la ordenación se realiza después de la unión.  Aunque puede utilizar una cláusula `orderby` con una o más de las secuencias de origen antes de la unión, generalmente no es recomendable.  Algunos proveedores de [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] podrían no conservar esa ordenación después de la unión.  
  
## Ejemplo  
 Esta consulta crea una unión de grupos y, a continuación, ordena los grupos según el elemento categoría, que todavía está dentro del ámbito.  Dentro del inicializador de tipo anónimo, una subconsulta ordena todos los elementos coincidentes de la secuencia de productos.  
  
 [!code-cs[csProgGuideLINQ#81](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#81)]  
  
## Compilar el código  
  
-   Cree un proyecto de [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] para la versión 3.5 de .NET Framework.  De manera predeterminada, el proyecto incluye una referencia a System.Core.dll y una directiva `using` para el espacio de nombres System.Linq.  
  
-   Copie el código en el proyecto.  
  
-   Presione F5 para compilar y ejecutar el programa.  
  
-   Presione cualquier tecla para salir de la ventana de consola.  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [orderby \(cláusula\)](../../../csharp/language-reference/keywords/orderby-clause.md)   
 [join \(cláusula\)](../../../csharp/language-reference/keywords/join-clause.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)