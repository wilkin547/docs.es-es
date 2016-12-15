---
title: "Conceptos b&#225;sicos de las expresiones de consultas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "consultas [LINQ en C#], básicas"
  - "expresiones de consulta [LINQ en C#], básicas"
  - "expresiones de consulta [LINQ en C#], ejecución de consultas"
ms.assetid: d3e1f4e6-1cf0-4066-87e3-1a42387223a6
caps.latest.revision: 32
caps.handback.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Conceptos b&#225;sicos de las expresiones de consultas (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## ¿Qué es una consulta y qué hace?  
 Una *consulta* es un conjunto de instrucciones que describe qué datos hay que recuperar de uno o varios orígenes de datos determinados y qué forma y organización deben tener los datos devueltos.  Una cosa es una consulta y otra distinta los resultados que genera.  
  
 Normalmente, los datos del origen se organizan de forma lógica como una secuencia de elementos del mismo tipo.  Una tabla de base de datos SQL contiene una secuencia de filas.  De igual forma, un objeto [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] <xref:System.Data.DataTable> contiene una secuencia de objetos <xref:System.Data.DataRow>.  En un archivo XML, hay una "secuencia" de elementos XML \(aunque éstos se organizan jerárquicamente en una estructura de árbol\).  Una colección en memoria contiene una secuencia de objetos.  
  
 Desde el punto de vista de una aplicación, el tipo específico y la estructura de los datos originales no son aspectos importantes.  La aplicación siempre considera los datos de origen como una colección <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.  En [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], los datos de origen aparecen visibles como un \<<xref:System.Xml.Linq.XElement>\> `IEnumerable`.  En [!INCLUDE[linq_dataset](../../../csharp/programming-guide/linq-query-expressions/includes/linq_dataset_md.md)], es un \<<xref:System.Data.DataRow>\> `IEnumerable`.  En [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq_md.md)], es un `IEnumerable` o `IQueryable` de cualquier objeto personalizado que se haya definido para representar los datos de la tabla SQL.  
  
 Dada esta secuencia de origen, una consulta puede hacer una de estas tres cosas:  
  
-   Recuperar un subconjunto de los elementos para generar una nueva secuencia sin modificar los elementos individuales.  A continuación, la consulta puede ordenar o agrupar de varias maneras la secuencia devuelta, como se muestra en el ejemplo siguiente \(se supone que `scores` es un `int[]`\):  
  
     [!code-cs[csrefQueryExpBasics#45](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_1.cs)]  
  
-   Recuperar una secuencia de elementos como en el ejemplo anterior, pero transformándolos en un nuevo tipo de objeto.  Por ejemplo, una consulta puede recuperar sólo los apellidos de ciertos registros de clientes de un origen de datos.  O bien, puede recuperar el registro completo y, a continuación, utilizarlo para construir otro tipo de objeto en memoria, o incluso datos XML, antes de generar la secuencia del resultado final.  El ejemplo siguiente muestra una transformación de un tipo `int` en un  `string`.  Fíjese en el nuevo tipo de `highScoresQuery`.  
  
     [!code-cs[csrefQueryExpBasics#46](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_2.cs)]  
  
-   Recuperar un valor singleton relacionado con los datos de origen, como:  
  
    -   El número de elementos que cumplen cierta condición.  
  
    -   El elemento que presenta el valor mayor o menor.  
  
    -   El primer elemento que cumple una condición, o la suma de determinados valores en un conjunto especificado de elementos.  Por ejemplo, la consulta siguiente devuelve el número de puntuaciones superiores a 80 de la matriz de enteros `scores`:  
  
     [!code-cs[csrefQueryExpBasics#47](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_3.cs)]  
  
     En el ejemplo anterior, tenga en cuenta el uso de paréntesis alrededor de la expresión de consulta antes de la llamada al método `Count`.  También puede expresar esto utilizando una nueva variable para almacenar el resultado concreto.  Esta técnica es más legible porque mantiene la variable que almacena la consulta independiente de la consulta que almacena un resultado.  
  
     [!code-cs[csrefQueryExpBasics#48](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_4.cs)]  
  
 En el ejemplo anterior, la consulta se ejecuta en la llamada a `Count`, ya que `Count` debe iterar sobre los resultados en orden para determinar el número de elementos devuelto por `highScoresQuery`.  
  
## ¿Qué es una expresión de consulta?  
 Una *expresión de consulta* es una consulta expresada en sintaxis de consultas.  Una expresión de consulta es una construcción de lenguaje de alto nivel.  Es una expresión como cualquier otra y se utiliza en cualquier contexto en el que una expresión de C\# sea válida.  Una expresión de consulta está compuesta de un conjunto de cláusulas escritas en una sintaxis declarativa similar a SQL o XQuery.  Cada cláusula contiene a su vez una o más expresiones de C\#, y estas expresiones pueden ser una expresión de consulta o contener una expresión de consulta.  
  
 Una expresión de consulta debe comenzar con una cláusula [from](../../../csharp/language-reference/keywords/from-clause.md) y debe finalizar con una cláusula [select](../../../csharp/language-reference/keywords/select-clause.md) o [group](../../../csharp/language-reference/keywords/group-clause.md).  Entre la primera cláusula `from` y la última cláusula `select` o `group`, pueden existir una o varias de estas cláusulas opcionales: [where](../../../csharp/language-reference/keywords/where-clause.md), [orderby](../../../csharp/language-reference/keywords/orderby-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md), [let](../../../csharp/language-reference/keywords/let-clause.md), e incluso cláusulas [from](../../../csharp/language-reference/keywords/from-clause.md) adicionales.  También se puede utilizar la palabra clave [into](../../../csharp/language-reference/keywords/into.md) para hacer que el resultado de una cláusula `join` o `group` actúe como origen de datos para las cláusulas de consulta adicionales incluidas en la misma expresión de consulta.  
  
### Variable de consulta  
 En [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], una variable de consulta es toda variable que almacena una *consulta* en lugar de los *resultados* de la misma. Para ser más exactos, una variable de consulta es siempre un tipo enumerable que generará una secuencia de elementos cuando se recorre en iteración en una instrucción `foreach` o una llamada directa a su método `IEnumerator.MoveNext`.  
  
 El ejemplo de código siguiente muestra una expresión de consulta simple con un origen de datos, una cláusula de filtrado, una cláusula de clasificación y ninguna transformación de los elementos de origen.  La cláusula `select` finaliza la consulta.  
  
 [!code-cs[csrefQueryExpBasics#49](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_5.cs)]  
  
 En el ejemplo anterior, `scoreQuery` es una *variable de consulta*, a la que a veces simplemente se le llama *consulta*.  La variable de consulta no almacena ninguno de los datos de resultado reales que se generan en el bucle `foreach`.  Y cuando la instrucción `foreach` se ejecuta, los resultados de la consulta no se devuelven a través de la variable de consulta `scoreQuery`.  En su lugar, se devuelven a través de la variable de iteración `testScore`.  La variable `scoreQuery` se puede iterar en un segundo bucle `foreach`.  Generará los mismos resultados siempre que ni ella ni el origen de datos se hayan modificado.  
  
 Una variable de consulta puede almacenar una consulta expresada en sintaxis de consulta, sintaxis de método o una combinación de ambas.  En los ejemplos siguientes, `queryMajorCities` y `queryMajorCities2` son variables de consulta:  
  
 [!code-cs[csrefQueryExpBasics#50](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_6.cs)]  
  
 Por otro lado, los dos ejemplos siguientes muestran variables que no son variables de consulta, aunque cada una de ellas se inicialice con una consulta.  No son variables de consulta porque almacenan resultados:  
  
 [!code-cs[csrefQueryExpBasics#51](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_7.cs)]  
  
> [!NOTE]
>  En la documentación de [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], las variables que almacenan una consulta incluyen la palabra "query" como parte de sus nombres.  Las variables que almacenan un resultado real no incluyen "query" en sus nombres.  
  
 Para obtener más información sobre los distintos modos de expresar consultas, vea [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
#### Asignación explícita e implícita de tipos de las variables de consulta  
 Esta documentación normalmente proporciona el tipo explícito de la variable de consulta para mostrar la relación de tipos entre la variable de consulta y la [cláusula select](../../../csharp/language-reference/keywords/select-clause.md).  Sin embargo, también se puede utilizar la palabra clave [var](../../../csharp/language-reference/keywords/var.md) para indicar al compilador que debe deducir el tipo de una variable de consulta \(o cualquier otra variable local\) en tiempo de compilación.  Por ejemplo, la consulta que se mostró anteriormente en este tema también se puede expresar utilizando la asignación implícita de tipos:  
  
 [!code-cs[csrefQueryExpBasics#52](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_8.cs)]  
  
 Para obtener más información, vea [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) y [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
### Iniciar una expresión de consulta  
 Una expresión de consulta debe comenzar con una cláusula `from`.  Ésta especifica un origen de datos junto con una variable de rango.  La variable de rango representa cada elemento sucesivo de la secuencia del origen mientras ésta se recorre.  La variable de rango está fuertemente tipada basada en el tipo de los elementos del origen de datos.  En el ejemplo siguiente, puesto que `countries` es una matriz de objetos `Country`, la variable de rango también presentará el mismo tipo que `Country`.  Dado que la variable de rango está fuertemente tipada, es posible utilizar el operador de punto para obtener acceso a cualquier miembro disponible del tipo.  
  
 [!code-cs[csrefQueryExpBasics#53](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_9.cs)]  
  
 La variable de rango permanece dentro de su ámbito hasta que se sale de la consulta mediante un punto y coma o con una cláusula *continuation*.  
  
 Una expresión de consulta puede contener varias cláusulas `from`.  Utilice cláusulas `from` adicionales cuando cada elemento de la secuencia de origen sea en sí mismo una colección o contenga una colección.  Por ejemplo, suponga que tiene una colección de objetos `Country`, cada uno de los cuales contiene una colección de objetos `City` denominada `Cities`.  Para consultar los objetos `City` de cada `Country`, utilice dos cláusulas `from` como se muestra aquí:  
  
 [!code-cs[csrefQueryExpBasics#54](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_10.cs)]  
  
 Para obtener más información, vea [from \(cláusula\)](../../../csharp/language-reference/keywords/from-clause.md).  
  
### Finalizar una expresión de consulta  
 Una expresión de consulta debe finalizar con una cláusula `select` o una cláusula `group`.  
  
#### Cláusula group  
 Utilice la cláusula `group` para generar una secuencia de grupos organizada por una clave especificada.  La clave puede ser de cualquier tipo de datos.  Por ejemplo, la consulta siguiente crea una secuencia de grupos que contiene uno o más objetos `Country` y cuya clave es un valor `char` de cadena.  
  
 [!code-cs[csrefQueryExpBasics#55](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_11.cs)]  
  
 Para obtener más información sobre agrupación de datos, vea [group \(cláusula\)](../../../csharp/language-reference/keywords/group-clause.md).  
  
#### Cláusula select  
 Utilice la cláusula `select` para generar todos los otros tipos de secuencias.  Una cláusula `select` simplemente genera una secuencia del mismo tipo de objetos que los objetos contenidos en el origen de datos.  En este ejemplo, el origen de datos contiene objetos `Country`.  La cláusula `orderby` simplemente ordena los elementos en un nuevo orden, mientras que la cláusula `select` genera una secuencia de los objetos `Country` reordenados.  
  
 [!code-cs[csrefQueryExpBasics#56](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_12.cs)]  
  
 La cláusula `select` se puede utilizar para transformar datos de origen en secuencias de nuevos tipos.  Esta transformación también se denomina una *proyección*.  En el ejemplo siguiente, la cláusula `select` *proyecta* una secuencia de tipos anónimos que contiene sólo un subconjunto de los campos del elemento original.  Observe que los nuevos objetos se inicializan mediante un inicializador de objeto.  
  
 [!code-cs[csrefQueryExpBasics#57](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_13.cs)]  
  
 Para obtener más información sobre todas las maneras en que una cláusula `select` se puede utilizar para transformar datos de origen, vea [select \(cláusula\)](../../../csharp/language-reference/keywords/select-clause.md).  
  
#### Continuaciones con "into"  
 Puede utilizar la palabra clave `into` en una cláusula `select` o `group` para crear un identificador temporal que almacena una consulta.  Haga esto cuando deba realizar operaciones de consulta adicionales sobre una consulta después de una operación de agrupación o selección.  En el ejemplo siguiente, `countries` están agrupados según su población en intervalos de 10 millones.  Una vez creados estos grupos, las cláusulas adicionales filtran algunos grupos y, a continuación, ordenan los grupos en orden ascendente.  Para realizar esas operaciones adicionales, se requiere la continuación representada por `countryGroup`.  
  
 [!code-cs[csrefQueryExpBasics#58](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_14.cs)]  
  
 Para obtener más información, vea [into](../../../csharp/language-reference/keywords/into.md).  
  
### Filtrado, ordenación y combinación  
 Entre la cláusula de inicio `from`, y de finalización `select` o `group`, todas las demás cláusulas \(`where`, `join`, `orderby`, `from`, `let`\) son opcionales.  Cualquiera de las cláusulas opcionales se pueden utilizar varias veces, o ninguna, en el cuerpo de una consulta.  
  
#### Cláusula where  
 Utilice la cláusula `where` para filtrar los elementos de los datos de origen según una o varias expresiones de predicado.  La cláusula `where` del ejemplo siguiente tiene dos predicados.  
  
 [!code-cs[csrefQueryExpBasics#59](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_15.cs)]  
  
 Para obtener más información, consulte [where \(cláusula\)](../../../csharp/language-reference/keywords/where-clause.md).  
  
#### Cláusula orderby  
 Utilice la cláusula `orderby` para ordenar los resultados en orden ascendente o descendente.  También puede especificar criterios de ordenación secundarios.  El ejemplo siguiente realiza una ordenación principal sobre los objetos `country` mediante la propiedad `Area`.  A continuación, realiza una ordenación secundaria mediante la propiedad `Population`.  
  
 [!code-cs[csrefQueryExpBasics#60](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_16.cs)]  
  
 La palabra clave `ascending` es opcional; constituye el criterio de ordenación predeterminado si no se especifica ningún orden.  Para obtener más información, consulte [orderby \(cláusula\)](../../../csharp/language-reference/keywords/orderby-clause.md).  
  
#### Cláusula join  
 Utilice la cláusula `join` para asociar y\/o combinar elementos de un origen de datos con elementos de otro origen de datos según una comparación de igualdad entre claves especificadas en cada elemento.  En [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], las operaciones de combinación se realizan sobre secuencias de objetos cuyos elementos son de tipos diferentes.  Después de haber unido dos secuencias, deberá utilizar una instrucción `select` o `group` para especificar qué elemento va a almacenar en la secuencia de salida.  También puede utilizar un tipo anónimo para combinar propiedades de cada conjunto de elementos asociados en un nuevo tipo para la secuencia de salida.  El ejemplo siguiente asocia objetos `prod` cuya propiedad `Category` coincide con una de las categorías de la matriz de cadenas `categories`.  Los productos cuya propiedad `Category` no coincide con alguna cadena de `categories` no pasan el filtro.  La instrucción `select` proyecta un nuevo tipo cuyas propiedades se toman de `cat` y `prod`.  
  
 [!code-cs[csrefQueryExpBasics#61](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_17.cs)]  
  
 También puede realizar una unión de grupos almacenando los resultados de la operación `join` en una variable temporal mediante la palabra clave [into](../../../csharp/language-reference/keywords/into.md).  Para obtener más información, consulte [join \(cláusula\)](../../../csharp/language-reference/keywords/join-clause.md).  
  
#### Cláusula let  
 Utilice la cláusula `let` para almacenar el resultado de una expresión, tal como una llamada a un método, en una nueva variable de intervalo.  En el ejemplo siguiente, la variable de intervalo `firstName` almacena el primer elemento de la matriz de cadenas devuelta por `Split`.  
  
 [!code-cs[csrefQueryExpBasics#62](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_18.cs)]  
  
 Para obtener más información, consulte [let \(cláusula\)](../../../csharp/language-reference/keywords/let-clause.md).  
  
### Subconsultas en una expresión de consulta  
 Una cláusula de consulta puede contener en sí misma una expresión de consulta, la cual se denomina a veces *subconsulta*.  Cada subconsulta se inicia con su propia cláusula `from`, que no necesariamente hace referencia al mismo origen de datos de la primera cláusula `from`.  Por ejemplo, la consulta siguiente muestra una expresión de consulta que se utiliza en la instrucción select para recuperar los resultados de una operación de agrupación.  
  
 [!code-cs[csrefQueryExpBasics#63](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_19.cs)]  
  
 Para obtener más información, vea [Cómo: Realizar una subconsulta en una operación de agrupación](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Palabras clave para consultas \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)