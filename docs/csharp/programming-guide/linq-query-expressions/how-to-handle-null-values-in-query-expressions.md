---
redirect_url: /dotnet/articles/csharp/linq/handle-null-values-in-query-expressions
caps.handback.revision: 6
---
# C&#243;mo: Controlar valores Null en expresiones de consultas (Gu&#237;a de programaci&#243;n de C#)
Este ejemplo muestra cómo tratar los posibles valores nulos \(null\) en colecciones de origen.  Una colección de objetos tal como un <xref:System.Collections.Generic.IEnumerable%601> puede contener elementos cuyo valor es [null](../../../csharp/language-reference/keywords/null.md).  Si una colección de origen es nula o contiene algún elemento cuyo valor es nulo, y la consulta no controla los valores nulos, se iniciará una excepción <xref:System.NullReferenceException> al ejecutar la consulta.  
  
## Ejemplo  
 Puede escribir el código adecuado para evitar una excepción de referencia nula como se muestra en el siguiente ejemplo:  
  
 [!code-cs[csProgGuideLINQ#82](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#82)]  
  
 En el ejemplo anterior, la cláusula `where` deja fuera del filtro todos los elementos nulos de la secuencia de categorías.  Esta técnica es independiente de la comprobación de valores nulos de la cláusula join.  La expresión condicional con null de este ejemplo funciona porque `Products.CategoryID` es de tipo `int?`, que es una forma abreviada de `Nullable<int>`.  
  
## Ejemplo  
 En una cláusula join, si sólo una de las claves de comparación es de un tipo de valor que acepta valores null, puede convertir el otro a un tipo que acepte valores null en la expresión de consulta.  En el ejemplo siguiente, suponga que `EmployeeID` es una columna que contiene valores de tipo `int?`:  
  
 [!code-cs[csProgGuideLINQ#83](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#83)]  
  
## Vea también  
 <xref:System.Nullable%601>   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)