---
redirect_url: /dotnet/articles/csharp/linq/perform-custom-join-operations
caps.handback.revision: 13
---
# C&#243;mo: Realizar operaciones de combinaci&#243;n personalizadas (Gu&#237;a de programaci&#243;n de C#)
En este ejemplo se muestra cómo realizar operaciones de combinación que no son posibles con la cláusula `join`.  En una expresión de consulta, la cláusula `join` se limita a combinaciones de igualdad, para las que está optimizada. Se trata, con diferencia, del tipo más habitual de operación de combinación.  Al realizar una combinación de igualdad, probablemente siempre obtendrá el máximo rendimiento si utiliza la cláusula `join`.  
  
 Sin embargo, la cláusula `join` no se puede usar en los siguientes casos:  
  
-   Cuando la combinación se predica en una expresión de desigualdad \(que no es una combinación de igualdad\).  
  
-   Cuando la combinación se predica en más de una expresión de igualdad o desigualdad.  
  
-   Cuando tiene que especificar una variable de rango temporal para la secuencia \(interna\) lateral derecha antes de la operación de combinación.  
  
 Para realizar combinaciones que no sean de igualdad, puede utilizar varias cláusulas `from` a fin de presentar cada origen de datos independientemente.  A continuación, aplique una expresión de predicado en una cláusula `where` a la variable de rango de cada origen.  La expresión también puede tener la forma de una llamada a un método.  
  
> [!NOTE]
>  No confunda este tipo de operación de combinación personalizada con el uso de varias cláusulas `from` para tener acceso a colecciones internas.  Para obtener más información, consulte [join \(cláusula\)](../../../csharp/language-reference/keywords/join-clause.md).  
  
## Ejemplo  
 El primer método del ejemplo siguiente muestra una combinación cruzada simple.  Las combinaciones cruzadas deben utilizarse con precaución porque pueden generar conjuntos de resultados muy grandes.  Sin embargo, pueden resultar útiles en algunos escenarios para crear secuencias de origen en las que se ejecutan consultas adicionales.  
  
 El segundo método genera una secuencia de todos los productos cuyo id. de categoría se incluye en la lista de categorías que aparece a la izquierda.  Tenga en cuenta el uso de la cláusula `let` y el método `Contains` para crear una matriz temporal.  También es posible crear la matriz antes que la consulta y eliminar la primera cláusula `from`.  
  
 [!code-cs[csProgGuideLINQ#64](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-perform-custom-join-operations_1.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente, la consulta debe combinar dos secuencias en función de las claves coincidentes que, en el caso de la secuencia interna \(lateral derecha\), no se pueden obtener antes de la propia cláusula de combinación.  Si esta combinación se realizara con una cláusula `join`, debería llamarse al método `Split` para cada elemento.  El uso de varias cláusulas `from` permite que la consulta evite la sobrecarga de la llamada a método repetida.  Sin embargo, dado que la cláusula `join` está optimizada, en este caso concreto podría ser aún más rápido que usar varias cláusulas `from`.  Los resultados variarán dependiendo principalmente de lo costosa que sea la llamada a método.  
  
 [!code-cs[csProgGuideLINQ#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-perform-custom-join-operations_2.cs)]  
  
## Compilar el código  
  
-   Cree un proyecto de aplicación de consola de [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] que tenga como destino [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 3.5 o una versión posterior.  De manera predeterminada, el proyecto incluye una referencia a System.Core.dll y una directiva `using` para el espacio de nombres System.Linq.  
  
-   Reemplace el código de la clase `Program` por el código del ejemplo anterior.  
  
-   Siga las instrucciones que se describen en [How to: Join Content from Dissimilar Files \(LINQ\)](../Topic/How%20to:%20Join%20Content%20from%20Dissimilar%20Files%20\(LINQ\).md) para configurar los archivos de datos: scores.csv y names.csv.  
  
-   Presione F5 para compilar y ejecutar el programa.  
  
-   Presione cualquier tecla para salir de la ventana de consola.  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [join \(cláusula\)](../../../csharp/language-reference/keywords/join-clause.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Cómo: Ordenar los resultados de una cláusula join](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)