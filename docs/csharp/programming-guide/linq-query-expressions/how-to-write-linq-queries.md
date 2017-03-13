---
redirect_url: /dotnet/articles/csharp/linq/write-linq-queries
caps.handback.revision: 25
---
# C&#243;mo: Escribir consultas con LINQ en C# #
En este tema se muestran las tres formas en que se puede escribir una consulta [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] en C\#:  
  
1.  Mediante la sintaxis de consulta.  
  
2.  Mediante la sintaxis de método.  
  
3.  Mediante una combinación de sintaxis de consulta y sintaxis de método.  
  
 En los ejemplos siguientes se muestran algunas consultas [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] sencillas con cada uno de los procedimientos enumerados anteriormente.  La regla general consiste en utilizar \(1\) siempre que sea posible y utilizar \(2\) y \(3\) cuando sea necesario.  
  
> [!NOTE]
>  Estas consultas funcionan en colecciones en memoria simples; sin embargo, la sintaxis básica es idéntica a la que se utiliza en [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq-md.md)] y [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  
  
## Ejemplo  
  
## Sintaxis de consulta  
 La forma recomendada de escribir la mayoría de las consultas es utilizar la *sintaxis de consulta* para crear *expresiones de consulta*.  En el ejemplo siguiente se muestran tres expresiones de consulta.  La primera expresión de consulta muestra cómo filtrar o restringir los resultados aplicando condiciones con una cláusula `where`.  Devuelve todos los elementos de la secuencia de origen cuyos valores son mayores que 7 o menores que 3.  La segunda expresión muestra cómo ordenar los resultados devueltos.  La tercera expresión muestra cómo agrupar los resultados según una clave.  Esta consulta devuelve dos grupos basándose en la primera letra de la palabra.  
  
 [!code-cs[csProgGuideLINQ#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-write-linq-queries_1.cs)]  
  
 Observe que el tipo de las consultas es <xref:System.Collections.Generic.IEnumerable%601>.  Todas estas consultas podrían escribirse utilizando `var`, tal y como se muestra en el ejemplo siguiente:  
  
 `var query = from num in numbers...`  
  
 En cada uno de los ejemplos anteriores, las consultas no se ejecutan realmente hasta que se procesa una iteración de la variable de consulta en una instrucción `foreach`.  Para obtener más información, vea [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
## Ejemplo  
  
## Sintaxis de método  
 Algunas operaciones de consulta deben expresarse como una llamada a un método.  Los métodos más habituales de este tipo son aquellos que devuelven valores numéricos singleton, como <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, etc.  Siempre se debe llamar a estos métodos en último lugar en cualquier consulta porque representan un solo valor y no sirven como origen de una operación de consulta adicional.  En el ejemplo siguiente se muestra una llamada a un método en una expresión de consulta:  
  
 [!code-cs[csProgGuideLINQ#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-write-linq-queries_2.cs)]  
  
## Ejemplo  
 Si el método incluye parámetros, éstos se proporcionan en forma de expresión [lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md), tal y como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideLINQ#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-write-linq-queries_3.cs)]  
  
 De todas las consultas anteriores, sólo la número 4 se ejecuta inmediatamente.  Esto se debe a que devuelve un solo valor y no una colección <xref:System.Collections.Generic.IEnumerable%601> genérica.  El propio método tiene que usar `foreach` para calcular su valor.  
  
 Cada una de las consultas anteriores puede escribirse usando tipos implícitos con [var](../../../csharp/language-reference/keywords/var.md), tal y como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideLINQ#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-write-linq-queries_4.cs)]  
  
## Ejemplo  
  
## Sintaxis mixta de consulta y método  
 En este ejemplo se muestra cómo usar la sintaxis de método en los resultados de una cláusula de consulta.  Simplemente hay que incluir la expresión de consulta entre paréntesis y, a continuación, aplicar el operador de punto y llamar al método.  En el ejemplo siguiente, la consulta número 7 devuelve un recuento de los números cuyo valor se encuentra comprendido entre 3 y 7.  Sin embargo, en general es mejor utilizar una segunda variable para almacenar el resultado de la llamada al método.  De esta forma, es menos probable que la consulta se confunda con los resultados de la consulta.  
  
 [!code-cs[csProgGuideLINQ#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-write-linq-queries_5.cs)]  
  
 La consulta número 7 se ejecuta inmediatamente porque devuelve un solo valor y no una colección.  
  
 La consulta anterior puede escribirse usando tipos implícitos con `var`, de la siguiente forma:  
  
```  
var numCount = (from num in numbers...  
```  
  
 Puede escribirse mediante la sintaxis de método, de la siguiente forma:  
  
```  
var numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
 Puede escribirse mediante tipos implícitos, de la siguiente forma:  
  
```  
int numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
## Vea también  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Walkthrough: Writing Queries in C\#](../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [where \(cláusula\)](../../../csharp/language-reference/keywords/where-clause.md)