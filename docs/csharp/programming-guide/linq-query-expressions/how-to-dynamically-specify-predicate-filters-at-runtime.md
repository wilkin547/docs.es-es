---
redirect_url: /dotnet/articles/csharp/linq/dynamically-specify-predicate-filters-at-runtime
caps.handback.revision: 22
---
# C&#243;mo: Especificar din&#225;micamente filtros con predicado en tiempo de ejecuci&#243;n (Gu&#237;a de programaci&#243;n de C#)
En algunos casos se desconoce hasta el momento de la ejecución cuántos predicados se deben aplicar a los elementos de origen en la cláusula `where`.  Una forma de especificar dinámicamente varios filtros con predicado es con el método <xref:System.Linq.Enumerable.Contains%2A>, como se muestra en el ejemplo siguiente:  El ejemplo se construye de dos maneras.  Primero, el proyecto se ejecuta filtrando en los valores que se proporcionan en el programa.  A continuación, el proyecto se ejecuta de nuevo utilizando la entrada proporcionada en tiempo de ejecución.  
  
### Para filtrar utilizando el método Contains  
  
1.  En Visual Studio, abra una nueva aplicación de consola.  Denomínelo `PredicateFilters`.  
  
2.  Copie la clase `StudentClass` de [Cómo: Consultar una colección de objetos](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) y péguela en el espacio de nombres `PredicateFilters` debajo de la clase `Program`.  `StudentClass` proporciona una lista de objetos `Student`.  
  
3.  Marque como comentario el método `Main` de `StudentClass`.  
  
4.  Reemplace la clase `Program` por el código siguiente.  
  
     [!code-cs[csProgGuideLINQ#26](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#26)]  
  
5.  Agregue la línea siguiente al método `Main` de la clase `DynamicPredicates`, bajo la declaración de `ids`.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
6.  Presione F5 para ejecutar el proyecto.  
  
7.  Los resultados siguientes se muestran en la ventana del símbolo del sistema:  
  
     Garcia: 114  
  
     O'Donnell: 112  
  
     Omelchenko: 111  
  
8.  El paso siguiente es ejecutar el proyecto de nuevo, esta vez utilizando la entrada en tiempo de ejecución en lugar de los `ids` de la matriz.  En el **Explorador de soluciones**, haga clic con el botón secundario en **Filtros con predicado** y, a continuación, haga clic en **Propiedades**.  
  
9. Haga clic en la ficha **Depurar**.  
  
10. En la ventana **Argumentos de la línea de comandos**, escriba 122, 117, 120 y 115, separados por espacios: `122 117 120 115`.  Cuando se ejecuta el proyecto, esos valores se convierten en elementos de `args`, el parámetro del método `Main`.  
  
11. Cambie `QueryByID(ids)` por `QueryByID(args)` en el método `Main`.  
  
12. Presione F5 para ejecutar el proyecto.  
  
13. Los resultados siguientes se muestran en la ventana del símbolo del sistema:  
  
     Adams: 120  
  
     Feng: 117  
  
     Garcia: 115  
  
     Tucker: 122  
  
### Para filtrar utilizando una instrucción switch  
  
1.  Puede utilizar una instrucción `switch` para seleccionar entre las consultas alternativas predeterminadas.  En el siguiente ejemplo, `studentQuery` utiliza una cláusula `where` diferente dependiendo de qué nivel de curso o año se especifica en tiempo de ejecución.  
  
2.  Copie el método siguiente y péguelo en la clase `DynamicPredicates`.  
  
     [!code-cs[csProgGuideLINQ#27](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#27)]  
  
3.  En la ventana **Argumentos de la línea de comandos**, reemplace los números del identificador del procedimiento anterior por un valor entero entre 1 y 4.  
  
4.  En el método `Main`, reemplace la llamada a `QueryByID` por la siguiente llamada, que envía el primer elemento de la matriz `args` como su argumento: `QueryByYear(args[0])`.  
  
5.  Presione F5 para ejecutar el proyecto.  
  
### Para utilizar este método en sus aplicaciones  
  
-   Cuando adapte este método a una aplicación, recuerde que LINQ requiere la versión 3.5 o 4 de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] y que el proyecto debe contener una referencia a System.Core.dll y una directiva `using` para `System.Linq`.  Los tipos LINQ to SQL, LINQ to XML y LINQ to DataSet requieren directivas `using` y referencias adicionales.  Para obtener más información, vea [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [where \(cláusula\)](../../../csharp/language-reference/keywords/where-clause.md)