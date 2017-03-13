---
redirect_url: /dotnet/articles/csharp/linq/perform-inner-joins
caps.handback.revision: 25
---
# C&#243;mo: Realizar combinaciones internas (Gu&#237;a de programaci&#243;n de C#)
En términos de bases de datos relacionales, una *combinación interna* genera un conjunto de resultados en el que cada elemento de la primera colección aparece una vez para cada elemento correspondiente de la segunda colección.  Si un elemento de la primera colección no tiene ningún elemento correspondiente, no aparece en el conjunto de resultados.  El método <xref:System.Linq.Enumerable.Join%2A>, que se invoca mediante la cláusula `join` en C\#, implementa una combinación interna.  
  
 En este tema se muestra cómo realizar cuatro variaciones de una combinación interna:  
  
-   Una combinación interna simple que correlaciona elementos de dos orígenes de datos según una clave simple.  
  
-   Una combinación interna que correlaciona elementos de dos orígenes de datos según una clave *compuesta* .  Una clave compuesta, que es una clave que se compone de más de un valor, permite correlacionar elementos según más de una propiedad.  
  
-   Una *combinación múltiple* en la que se anexan operaciones de combinación sucesivas.  
  
-   Una combinación interna que se implementa mediante una combinación agrupada.  
  
## Ejemplo  
  
## Ejemplo de combinación de clave simple  
 En el ejemplo siguiente se crean dos colecciones que contienen objetos de dos tipos definidos por el usuario, `Person` y `Pet`.  La consulta usa la cláusula `join` en C\# para establecer correspondencias entre los objetos `Person` y los objetos `Pet` cuyo `Owner` es ese objeto `Person`.  La cláusula `select` en C\# define el aspecto de los objetos resultantes.  En este ejemplo, los objetos resultantes son tipos anónimos que consisten en el nombre del propietario y el nombre del animal doméstico.  
  
 [!code-cs[CsLINQProgJoining#1](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-inner-joins_1.cs)]  
  
 Observe cómo el objeto `Person` cuyo `LastName` es "Huff" no aparece en el conjunto de resultados porque no es ningún objeto `Pet` cuyo `Pet.Owner` sea igual a ese objeto `Person`.  
  
## Ejemplo  
  
## Ejemplo de combinación de clave compuesta  
 En lugar de correlacionar elementos según una sola propiedad, puede utilizar una clave compuesta para comparar los elementos según varias propiedades.  Para ello, especifique la función del selector de claves para cada colección para devolver un tipo anónimo formado por las propiedades que desea comparar.  Si etiqueta las propiedades, deben tener la misma etiqueta en el tipo anónimo de cada clave.  Las propiedades también deben aparecer en el mismo orden.  
  
 En el ejemplo siguiente se utiliza una lista de objetos `Employee` y una lista de objetos `Student` para determinar qué empleados son también estudiantes.  Ambos tipos tienen una propiedad `FirstName` y `LastName` de tipo <xref:System.String>.  Las funciones que crean las claves de combinación a partir de los elementos de cada lista devuelven un tipo anónimo formado por las propiedades `FirstName` y `LastName` de cada elemento.  La operación de combinación compara la igualdad de estas claves compuestas y devuelve pares de objetos de cada lista que tengan el mismo nombre y apellido.  
  
 [!code-cs[CsLINQProgJoining#2](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-inner-joins_2.cs)]  
  
## Ejemplo  
  
## Ejemplo de combinación múltiple  
 Es posible anexar cualquier número de operaciones de combinación para realizar una combinación múltiple.  Cada cláusula `join` en C\# relaciona un origen de datos especificado con los resultados de la combinación anterior.  
  
 En el ejemplo siguiente se crean tres colecciones: una lista de objetos `Person`, una lista de objetos `Cat` y una lista de objetos `Dog`.  
  
 En C\#, la primera cláusula `join` establece correspondencias entre las personas y los gatos en función de las coincidencias entre `Cat.Owner` y `Person`.  Devuelve una secuencia de tipos anónimos que contiene el objeto `Person` y `Cat.Name`.  
  
 En C\#, la segunda cláusula `join` relaciona los tipos anónimos devueltos por la primera combinación con los objetos `Dog` de la lista de perros proporcionada en función de una clave compuesta formada por la propiedad `Owner` del tipo `Person` y la primera letra del nombre del animal.  Devuelve una secuencia de tipos anónimos que contiene las propiedades `Cat.Name` y `Dog.Name` de cada par coincidente.  Dado que se trata de una combinación interna, se devuelven sólo los objetos del primer origen de datos que tienen una correspondencia en el segundo origen de datos.  
  
 [!code-cs[CsLINQProgJoining#3](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-inner-joins_3.cs)]  
  
## Ejemplo  
  
## Ejemplo de combinación interna mediante una combinación agrupada  
 En el ejemplo siguiente se muestra cómo implementar una combinación interna mediante una combinación agrupada.  
  
 En `query1`, la lista de objetos `Person` se combina en grupo con la lista de objetos `Pet` según el objeto `Person` que coincide con la propiedad `Pet.Owner`.  La combinación agrupada crea una colección de grupos intermedios, donde cada grupo está compuesto de un objeto `Person` y una secuencia de objetos `Pet` coincidentes.  
  
 Al agregar una segunda cláusula `from` a la consulta, esta secuencia de secuencias se combina \(o simplifica\) en una secuencia más larga.  La cláusula `select` especifica el tipo de los elementos de la secuencia final.  En este ejemplo, se trata de un tipo anónimo formado por las propiedades `Person.FirstName` y `Pet.Name` de cada par coincidente.  
  
 El resultado de `query1` es equivalente al conjunto de resultados que se obtendrían usando la cláusula `join` sin la cláusula `into` para realizar una combinación interna.  La variable `query2` muestra esta consulta equivalente.  
  
 [!code-cs[CsLINQProgJoining#4](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-inner-joins_4.cs)]  
  
## Compilar el código  
  
-   Cree un nuevo proyecto de aplicación de consola en [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)].  
  
-   Agregue una referencia a System.Core.dll si ésta no existe aún.  
  
-   Incluya el espacio de nombres <xref:System.Linq>.  
  
-   Copie el código del ejemplo y péguelo en el archivo program.cs , bajo el método `Main`.  Agregue una línea de código al método `Main` para llamar al método que pegó.  
  
-   Ejecute el programa.  
  
## Vea también  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Cómo: Realizar combinaciones agrupadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [Cómo: Realizar operaciones de combinación externa izquierda](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [Cómo combinar dos colecciones](../Topic/How%20to:%20Join%20Two%20Collections%20\(C%23\)%20\(LINQ%20to%20XML\).md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)