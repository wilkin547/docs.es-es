---
title: Conceptos básicos de las expresiones de consulta (LINQ en C#)
description: En este tema se presentan los conceptos relacionados con las expresiones de consulta.
ms.date: 11/30/2016
ms.assetid: 027db1f8-346f-44d2-a16e-043fcea3a4e0
ms.openlocfilehash: 83beaa82d4b4b42ff9da5230edddd391b33a0717
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173359"
---
# <a name="query-expression-basics"></a>Conceptos básicos de las expresiones de consultas

En este artículo se presentan los conceptos básicos relacionados con las expresiones de consulta en C#.

## <a name="what-is-a-query-and-what-does-it-do"></a>¿Qué es una consulta y qué hace?

Una *consulta* es un conjunto de instrucciones que describen qué datos se recuperan de uno o varios orígenes de datos determinados y qué forma y qué organización deben tener los datos devueltos. Una consulta es distinta de los resultados que genera.

Por lo general, los datos de origen se organizan lógicamente como una secuencia de elementos del mismo tipo. Por ejemplo, una tabla de base de datos SQL contiene una secuencia de filas. En un archivo XML, hay una "secuencia" de elementos XML (aunque estos se organizan jerárquicamente en una estructura de árbol). Una colección en memoria contiene una secuencia de objetos.

Desde el punto de vista de la aplicación, el tipo y la estructura específicos de los datos de origen originales no es importante. La aplicación siempre ve los datos de origen como una colección <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>. Por ejemplo, en LINQ to XML, los datos de origen se hacen visibles como `IEnumerable`\<<xref:System.Xml.Linq.XElement>>.

Dada esta secuencia de origen, una consulta puede hacer una de estas tres cosas:

- Recuperar un subconjunto de los elementos para generar una nueva secuencia sin modificar los elementos individuales. Después, la consulta puede ordenar o agrupar la secuencia devuelta de varias maneras, como se muestra en el ejemplo siguiente (supongamos que `scores` es `int[]`):

    [!code-csharp[csrefQueryExpBasics#45](~/samples/snippets/csharp/concepts/linq/query-expression-basics_1.cs)]

- Recuperar una secuencia de elementos como en el ejemplo anterior, pero transformándolos en un nuevo tipo de objeto. Por ejemplo, una consulta puede recuperar solo los apellidos de ciertos registros de clientes de un origen de datos. También puede recuperar el registro completo y, luego, usarlo para construir otro tipo de objeto en memoria, o incluso datos XML, antes de generar la secuencia de resultado final. En el ejemplo siguiente muestra una proyección de `int` a `string`. Observe el nuevo tipo de `highScoresQuery`.

    [!code-csharp[csrefQueryExpBasics#46](~/samples/snippets/csharp/concepts/linq/query-expression-basics_2.cs)]

- Recuperar un valor singleton sobre los datos de origen, por ejemplo:

  - El número de elementos que coinciden con una condición determinada.

  - El elemento que tiene el mayor o el menor valor.

  - El primer elemento que coincide con una condición, o bien la suma de determinados valores de un conjunto de elementos especificado. Por ejemplo, la consulta siguiente devuelve el número de resultados mayor que 80 de la matriz de enteros `scores`:

    [!code-csharp[csrefQueryExpBasics#47](~/samples/snippets/csharp/concepts/linq/query-expression-basics_3.cs)]

    En el ejemplo anterior, observe el uso de los paréntesis alrededor de la expresión de consulta antes de llamar al método `Count`. Esto también se puede expresar mediante una nueva variable para almacenar el resultado concreto. Esta técnica es más legible porque hace que la variable que almacena la consulta se mantenga separada de la consulta que almacena un resultado.

    [!code-csharp[csrefQueryExpBasics#48](~/samples/snippets/csharp/concepts/linq/query-expression-basics_4.cs)]

En el ejemplo anterior, la consulta se ejecuta en la llamada a `Count`, ya que `Count` debe iterar los resultados para determinar el número de elementos devueltos por `highScoresQuery`.

## <a name="what-is-a-query-expression"></a>¿Qué es una expresión de consulta?

Una *expresión de consulta* es una consulta que se expresa en sintaxis de consulta. Una expresión de consulta es una construcción de lenguaje de primera clase. Es igual que cualquier otra expresión y puede usarse en cualquier contexto en el que una expresión de C# sea válida. Una expresión de consulta consta de un conjunto de cláusulas escritas en una sintaxis declarativa similar a SQL o XQuery. Cada cláusula contiene una o más expresiones de C#, y estas expresiones pueden ser una expresión de consulta en sí mismas o bien contener una expresión de consulta.

Una expresión de consulta debe comenzar con una cláusula [from](../language-reference/keywords/from-clause.md) y debe terminar con una cláusula [select](../language-reference/keywords/select-clause.md) o [group](../language-reference/keywords/group-clause.md). Entre la primera cláusula `from` y la última cláusula `select` o `group`, puede contener una o varias de estas cláusulas opcionales: [where](../language-reference/keywords/where-clause.md), [orderby](../language-reference/keywords/orderby-clause.md), [join](../language-reference/keywords/join-clause.md), [let](../language-reference/keywords/let-clause.md) e incluso cláusulas [from](../language-reference/keywords/from-clause.md) adicionales. También puede usar la palabra clave [into](../language-reference/keywords/into.md) para que el resultado de una cláusula `join` o `group` actúe como el origen de las cláusulas de consulta adicionales en la misma expresión de consulta.

### <a name="query-variable"></a>Variable de consulta

En LINQ, una variable de consulta es cualquier variable que almacene una *consulta* en lugar de los *resultados* de una consulta. Más concretamente, una variable de consulta es siempre un tipo enumerable que generará una secuencia de elementos cuando se itere en una instrucción `foreach` o en una llamada directa a su método `IEnumerator.MoveNext`.

En el ejemplo de código siguiente se muestra una expresión de consulta simple con un origen de datos, una cláusula de filtrado, una cláusula de clasificación y ninguna transformación en los elementos de origen. La cláusula `select` finaliza la consulta.

[!code-csharp[csrefQueryExpBasics#49](~/samples/snippets/csharp/concepts/linq/query-expression-basics_5.cs)]

En el ejemplo anterior, `scoreQuery` es una *variable de consulta*, que a veces se conoce simplemente como una *consulta*. La variable de consulta no almacena datos de resultado reales, que se producen en el bucle `foreach`. Cuando se ejecuta la instrucción `foreach`, los resultados de la consulta no se devuelven a través de la variable de consulta `scoreQuery`, sino a través de la variable de iteración `testScore`. La variable `scoreQuery` se puede iterar en un segundo bucle `foreach`. Siempre y cuando ni esta ni el origen de datos se hayan modificado, producirá los mismos resultados.

Una variable de consulta puede almacenar una consulta expresada en sintaxis de consulta, en sintaxis de método o en una combinación de ambas. En los ejemplos siguientes, `queryMajorCities` y `queryMajorCities2` son variables de consulta:

[!code-csharp[csrefQueryExpBasics#50](~/samples/snippets/csharp/concepts/linq/query-expression-basics_6.cs)]

Por otro lado, en los dos ejemplos siguientes se muestran variables que no son de consulta, a pesar de que se inicialicen con una consulta. No son variables de consulta porque almacenan resultados:

[!code-csharp[csrefQueryExpBasics#51](~/samples/snippets/csharp/concepts/linq/query-expression-basics_7.cs)]

Para obtener más información sobre las distintas formas de expresar consultas, vea [Query syntax and method syntax in LINQ](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) (Sintaxis de consulta y sintaxis de método en LINQ).

#### <a name="explicit-and-implicit-typing-of-query-variables"></a>Asignación implícita y explícita de tipos de variables de consulta

En esta documentación se suele proporcionar el tipo explícito de la variable de consulta para mostrar las relaciones de tipo entre la variable de consulta y la [cláusula select](../language-reference/keywords/select-clause.md). Pero también se puede usar la palabra clave [var](../language-reference/keywords/var.md) para indicarle al compilador que infiera el tipo de una variable de consulta (u otra variable local) en tiempo de compilación. Por ejemplo, la consulta de ejemplo que se mostró anteriormente en este tema también se puede expresar mediante la asignación implícita de tipos:

[!code-csharp[csrefQueryExpBasics#52](~/samples/snippets/csharp/concepts/linq/query-expression-basics_8.cs)]

Para obtener más información, vea [Implicitly typed local variables](../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) (Variables locales con asignación implícita de tipos) y [Type relationships in LINQ query operations](../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md) (Relaciones entre tipos en las operaciones de consulta de LINQ).

### <a name="starting-a-query-expression"></a>Iniciar una expresión de consulta

Una expresión de consulta debe comenzar con una cláusula `from`, que especifica un origen de datos junto con una variable de rango. La variable de rango representa cada elemento sucesivo de la secuencia de origen a medida que esta se recorre. La variable de rango está fuertemente tipada en función del tipo de elementos del origen de datos. En el ejemplo siguiente, como `countries` es una matriz de objetos `Country`, la variable de rango también está tipada como `Country`. Dado que la variable de rango está fuertemente tipada, se puede usar el operador punto para tener acceso a cualquier miembro disponible del tipo.

[!code-csharp[csrefQueryExpBasics#53](~/samples/snippets/csharp/concepts/linq/query-expression-basics_9.cs)]

La variable de rango está en el ámbito hasta que se cierra la consulta con un punto y coma o con una cláusula de *continuación*.

Una expresión de consulta puede contener varias cláusulas `from`. Use más cláusulas `from` cuando cada elemento de la secuencia de origen sea una colección en sí mismo o contenga una colección. Por ejemplo, supongamos que tiene una colección de objetos `Country`, cada uno de los cuales contiene una colección de objetos `City` denominados `Cities`. Para consultar los objetos `City` de cada `Country`, use dos cláusulas `from`, como se muestra aquí:

[!code-csharp[csrefQueryExpBasics#54](~/samples/snippets/csharp/concepts/linq/query-expression-basics_10.cs)]

Para obtener más información, vea [from clause](../language-reference/keywords/from-clause.md) (Cláusula from).

### <a name="ending-a-query-expression"></a>Finalizar una expresión de consulta

Una expresión de consulta debe finalizar con una cláusula `group` o `select`.

#### <a name="group-clause"></a>group (cláusula)

Use la cláusula `group` para generar una secuencia de grupos organizados por la clave que especifique. La clave puede ser cualquier tipo de datos. Por ejemplo, la siguiente consulta crea una secuencia de grupos que contienen uno o más objetos `Country` y cuya clave es un valor `char`.

[!code-csharp[csrefQueryExpBasics#55](~/samples/snippets/csharp/concepts/linq/query-expression-basics_11.cs)]

Para obtener más información sobre la agrupación, vea [group clause](../language-reference/keywords/group-clause.md) (Cláusula group).

#### <a name="select-clause"></a>select (cláusula)

Use la cláusula `select` para generar todos los demás tipos de secuencias. Una cláusula `select` simple solo genera una secuencia del mismo tipo de objetos que los objetos contenidos en el origen de datos. En este ejemplo, el origen de datos contiene objetos `Country`. La cláusula `orderby` simplemente ordena los elementos con un orden nuevo y la cláusula `select` genera una secuencia con los objetos `Country` reordenados.

[!code-csharp[csrefQueryExpBasics#56](~/samples/snippets/csharp/concepts/linq/query-expression-basics_12.cs)]

La cláusula `select` puede usarse para transformar los datos de origen en secuencias de nuevos tipos. Esta transformación también se denomina *proyección*. En el ejemplo siguiente, la cláusula `select`*proyecta* una secuencia de tipos anónimos que solo contiene un subconjunto de los campos del elemento original. Tenga en cuenta que los nuevos objetos se inicializan mediante un inicializador de objeto.

[!code-csharp[csrefQueryExpBasics#57](~/samples/snippets/csharp/concepts/linq/query-expression-basics_13.cs)]

Para obtener más información sobre todas las formas en que se puede usar una cláusula `select` para transformar datos de origen, vea [select clause](../language-reference/keywords/select-clause.md) (Cláusula select).

#### <a name="continuations-with-into"></a>Continuaciones con "into"

Puede usar la palabra clave `into` en una cláusula `select` o `group` para crear un identificador temporal que almacene una consulta. Hágalo cuando deba realizar operaciones de consulta adicionales en una consulta después de una operación de agrupación o selección. En el siguiente ejemplo se agrupan los objetos `countries` según su población en intervalos de 10 millones. Una vez que se han creado estos grupos, las cláusulas adicionales filtran algunos grupos y, después, ordenan los grupos en orden ascendente. Para realizar esas operaciones adicionales, es necesaria la continuación representada por `countryGroup`.

[!code-csharp[csrefQueryExpBasics#58](~/samples/snippets/csharp/concepts/linq/query-expression-basics_14.cs)]

Para obtener más información, vea [into](../language-reference/keywords/into.md).

### <a name="filtering-ordering-and-joining"></a>Filtrar, ordenar y combinar

Entre la cláusula de inicio `from` y la cláusula de finalización `select` o `group`, todas las demás cláusulas (`where`, `join`, `orderby`, `from`, `let`) son opcionales. Cualquiera de las cláusulas opcionales puede usarse cero o varias veces en el cuerpo de una consulta.

#### <a name="where-clause"></a>where (cláusula)

Use la cláusula `where` para filtrar los elementos de los datos de origen en función de una o varias expresiones de predicado. La cláusula `where` del ejemplo siguiente tiene un predicado con dos condiciones.

[!code-csharp[csrefQueryExpBasics#59](~/samples/snippets/csharp/concepts/linq/query-expression-basics_15.cs)]

Para obtener más información, vea [where (Cláusula)](../language-reference/keywords/where-clause.md).

#### <a name="orderby-clause"></a>orderby (cláusula)

Use la cláusula `orderby` para ordenar los resultados en orden ascendente o descendente. También puede especificar criterios de ordenación secundaria. En el ejemplo siguiente se realiza una ordenación primaria de los objetos `country` mediante la propiedad `Area`. Después, se realiza una ordenación secundaria mediante la propiedad `Population`.

[!code-csharp[csrefQueryExpBasics#60](~/samples/snippets/csharp/concepts/linq/query-expression-basics_16.cs)]

La palabra clave `ascending` es opcional; es el criterio de ordenación predeterminado si no se especifica ningún orden. Para obtener más información, vea [orderby (Cláusula)](../language-reference/keywords/orderby-clause.md).

#### <a name="join-clause"></a>join (cláusula)

Use la cláusula `join` para asociar o combinar elementos de un origen de datos con elementos de otro origen de datos en función de una comparación de igualdad entre las claves especificadas en cada elemento. En LINQ, las operaciones de combinación se realizan en secuencias de objetos cuyos elementos son de tipos diferentes. Después de combinar dos secuencias, debe usar una instrucción `select` o `group` para especificar qué elemento se va a almacenar en la secuencia de salida. También puede usar un tipo anónimo para combinar propiedades de cada conjunto de elementos asociados en un nuevo tipo para la secuencia de salida. En el ejemplo siguiente se asocian objetos `prod` cuya propiedad `Category` coincide con una de las categorías de la matriz de cadenas `categories`. Los productos cuya propiedad `Category` no coincide con ninguna cadena de `categories` se filtran. La instrucción `select` proyecta un nuevo tipo cuyas propiedades se toman de `cat` y `prod`.

[!code-csharp[csrefQueryExpBasics#61](~/samples/snippets/csharp/concepts/linq/query-expression-basics_17.cs)]

También puede realizar una combinación agrupada. Para ello, almacene los resultados de la operación `join` en una variable temporal mediante el uso de la palabra clave [into](../language-reference/keywords/into.md). Para obtener más información, vea [join (Cláusula, Referencia de C#)](../language-reference/keywords/join-clause.md).

#### <a name="let-clause"></a>let (cláusula)

Use la cláusula `let` para almacenar el resultado de una expresión, como una llamada de método, en una nueva variable de rango. En el ejemplo siguiente, la variable de rango `firstName` almacena el primer elemento de la matriz de cadenas devuelta por `Split`.

[!code-csharp[csrefQueryExpBasics#62](~/samples/snippets/csharp/concepts/linq/query-expression-basics_18.cs)]

Para obtener más información, vea [let (Cláusula)](../language-reference/keywords/let-clause.md).

### <a name="subqueries-in-a-query-expression"></a>Subconsultas en una expresión de consulta

Una cláusula de consulta puede contener una expresión de consulta, en ocasiones denominada *subconsulta*. Cada subconsulta comienza con su propia cláusula `from` que no necesariamente hace referencia al mismo origen de datos de la primera cláusula `from`. Por ejemplo, la consulta siguiente muestra una expresión de consulta que se usa en la instrucción select para recuperar los resultados de una operación de agrupación.

[!code-csharp[csrefQueryExpBasics#63](~/samples/snippets/csharp/concepts/linq/query-expression-basics_19.cs)]

Para más información, consulte [Realizar una subconsulta en una operación de agrupación](perform-a-subquery-on-a-grouping-operation.md).

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../programming-guide/index.md)
- [Language-Integrated Query (LINQ)](index.md)
- [Palabras clave de consultas (LINQ)](../language-reference/keywords/query-keywords.md)
- [Información general sobre operadores de consulta estándar](../programming-guide/concepts/linq/standard-query-operators-overview.md)
