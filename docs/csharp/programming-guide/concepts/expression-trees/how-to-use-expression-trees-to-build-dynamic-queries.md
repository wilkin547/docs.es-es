---
title: Consultas basadas en el estado del entorno de ejecución (C#)
description: Se describen diversas técnicas que el código puede usar para realizar consultas de forma dinámica según el estado del entorno de ejecución, mediante la modificación de las llamadas a métodos de LINQ o los árboles de expresión pasados a esos métodos.
ms.date: 02/11/2021
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
ms.openlocfilehash: 0dcf1696ca323ac4823c80c7993fef7873fd8ed5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433788"
---
# <a name="querying-based-on-runtime-state-c"></a>Consultas basadas en el estado del entorno de ejecución (C#)

Tenga en cuenta el código que define una interfaz <xref:System.Linq.IQueryable> o [IQueryable\<T>](<xref:System.Linq.IQueryable%601>) con respecto a un origen de datos:

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Initialize":::

Cada vez que ejecute este código, se ejecutará la misma consulta exacta. Esto no suele ser muy útil, ya que es posible que quiera que el código ejecute otras consultas en función de las condiciones en el momento de la ejecución. En este artículo se describe cómo puede ejecutar otra consulta en función del estado del entorno de ejecución.

## <a name="iqueryable--iqueryablet-and-expression-trees"></a>IQueryable/IQueryable\<T> y árboles de expresión

Fundamentalmente, una interfaz <xref:System.Linq.IQueryable> tiene dos componentes:

* <xref:System.Linq.IQueryable.Expression>&mdash;representación independiente del lenguaje y del origen de datos de los componentes de la consulta actual, en forma de un árbol de expresión.
* <xref:System.Linq.IQueryable.Provider>&mdash;instancia de un proveedor LINQ, que sabe cómo materializar la consulta actual en un valor o un conjunto de valores.

En el contexto de las consultas dinámicas, el proveedor normalmente seguirá siendo el mismo; el árbol de expresión de la consulta variará entre consultas.

Los árboles de expresión son inmutables; si quiere otro árbol de expresión (y, por tanto, otra consulta), tendrá que convertir el existente en uno nuevo y, de este modo, en una nueva interfaz <xref:System.Linq.IQueryable>.

En las secciones siguientes se describen técnicas específicas para realizar consultas de forma diferente en respuesta al estado del entorno de ejecución:

- Uso del estado del entorno de ejecución desde el árbol de expresión
- Llamada a métodos de LINQ adicionales
- Variación del árbol de expresión que se pasa a los métodos de LINQ
- Creación de un árbol de expresión [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) con los métodos de generador de <xref:System.Linq.Expressions.Expression>
- Adición de nodos de llamada de método a la interfaz <xref:System.Linq.IQueryable> de un árbol de expresión
- Construcción de cadenas y uso de la [biblioteca dinámica de LINQ](https://dynamic-linq.net/)

## <a name="use-runtime-state-from-within-the-expression-tree"></a>Uso del estado del entorno de ejecución desde el árbol de expresión

Siempre que el proveedor LINQ lo admita, la manera más sencilla de realizar consultas dinámicas consiste en hacer referencia al estado del entorno de ejecución de forma directa en la consulta mediante una variable cerrada, como `length` en el ejemplo de código siguiente:

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Runtime_state_from_within_expression_tree":::

El árbol de expresión interno (y, por tanto, la consulta) no se ha modificado; la consulta devuelve otros valores solo porque se ha cambiado el valor de `length`.

## <a name="call-additional-linq-methods"></a>Llamada a métodos de LINQ adicionales

Por lo general, los [métodos de LINQ integrados](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Linq.Queryable/src/System/Linq/Queryable.cs) en <xref:System.Linq.Queryable> realizan dos pasos:

* Encapsulan el árbol de expresión actual en un elemento <xref:System.Linq.Expressions.MethodCallExpression> que representa la llamada de método.
* Vuelven a pasar el árbol de expresión encapsulado al proveedor, ya sea para devolver un valor mediante el método <xref:System.Linq.IQueryProvider.Execute%2A?displayProperty=nameWithType> del proveedor, o bien para devolver un objeto de consulta traducido mediante el método <xref:System.Linq.IQueryProvider.CreateQuery%2A?displayProperty=nameWithType>.

Puede reemplazar la consulta original con el resultado de un método que devuelva [IQueryable\<T>](xref:System.Linq.IQueryable%601) para obtener una nueva consulta. Puede hacerlo en función del estado del entorno de ejecución, como en el ejemplo siguiente:

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Added_method_calls":::

## <a name="vary-the-expression-tree-passed-into-the-linq-methods"></a>Variación del árbol de expresión que se pasa a los métodos de LINQ

Puede pasar otras expresiones a los métodos de LINQ, en función del estado del entorno de ejecución:

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Varying_expressions":::

También es posible que quiera crear las distintas subexpresiones mediante una biblioteca de terceros, como [PredicateBuilder](http://www.albahari.com/nutshell/predicatebuilder.aspx) de [LinqKit](http://www.albahari.com/nutshell/linqkit.aspx):

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Compose_expressions":::

## <a name="construct-expression-trees-and-queries-using-factory-methods"></a>Creación de árboles de expresión y consultas mediante métodos de generador

En todos los ejemplos vistos hasta ahora, se ha conocido el tipo de elemento en tiempo de compilación `string` y, por tanto, el tipo de la consulta `IQueryable<string>`. Es posible que tenga que agregar componentes a una consulta de cualquier tipo de elemento. Es posible que tenga que agregar otros componentes, en función del tipo de elemento. Puede crear árboles de expresión desde cero, con los métodos de generador de <xref:System.Linq.Expressions.Expression?displayProperty=fullName> y, por tanto, adaptar la expresión a un tipo de elemento específico.

### <a name="constructing-an-expressiontdelegate"></a>Creación de una instancia de [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601)

Cuando se crea una expresión para pasarla a uno de los métodos de LINQ, en realidad se crea una instancia de [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601), donde `TDelegate` es un tipo de delegado como `Func<string, bool>`, `Action` o un tipo de delegado personalizado.

[Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) hereda de <xref:System.Linq.Expressions.LambdaExpression>, que representa una expresión lambda completa como la siguiente:

```csharp
Expression<Func<string, bool>> expr = x => x.StartsWith("a");
```

<xref:System.Linq.Expressions.LambdaExpression> tiene dos componentes:

* una lista de parámetros `(string x)` representada por la propiedad <xref:System.Linq.Expressions.LambdaExpression.Parameters>.
* un cuerpo `x.StartsWith("a")` representado por la propiedad <xref:System.Linq.Expressions.LambdaExpression.Body>.

Los pasos básicos para crear una instancia de [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) son los siguientes:

* Defina objetos <xref:System.Linq.Expressions.ParameterExpression> para cada uno de los parámetros (si existen) de la expresión lambda, mediante el método generador <xref:System.Linq.Expressions.Expression.Parameter%2A>.

    ```csharp
    ParameterExpression x = Parameter(typeof(string), "x");
    ```

* Cree el cuerpo de <xref:System.Linq.Expressions.LambdaExpression>, mediante el objeto <xref:System.Linq.Expressions.ParameterExpression> que haya definido. Por ejemplo, una expresión que represente `x.StartsWith("a")` se podría crear de la siguiente manera:

    ```csharp
    Expression body = Call(
        x,
        typeof(string).GetMethod("StartsWith", new [] {typeof(string)}),
        Constant("a")
    );
    ```

* Encapsule los parámetros y el cuerpo en una instancia de [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) con tipo de tiempo de compilación, mediante la sobrecarga correspondiente del método de generador <xref:System.Linq.Expressions.Expression.Lambda%2A>:

    ```csharp
    Expression<Func<string, bool>> expr = Lambda<Func<string, bool>>(body, prm);
    ```

En las secciones siguientes se describe un escenario en el que es posible que quiera crear una instancia de [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) para pasarla a un método de LINQ, y se proporciona un ejemplo completo de cómo hacerlo mediante los métodos de generador.

### <a name="scenario"></a>Escenario

Imagine que tiene varios tipos de entidad:

```csharp
record Person(string LastName, string FirstName, DateTime DateOfBirth);
record Car(string Model, int Year);
```

En cualquiera de estos tipos de entidad, quiere filtrar y devolver solo las entidades que contengan un texto concreto dentro de uno de sus campos `string`. Para `Person`, le interesa buscar las propiedades `FirstName` y `LastName`:

```csharp
string term = /* ... */;
var personsQry = new List<Person>()
    .AsQueryable()
    .Where(x => x.FirstName.Contains(term) || x.LastName.Contains(term));
```

Pero para `Car`, solo quiere buscar la propiedad `Model`:

```csharp
string term = /* ... */;
var carsQry = new List<Car>()
    .AsQueryable()
    .Where(x => x.Model.Contains(term));
```

Aunque podría escribir una función personalizada para `IQueryable<Person>` y otra para `IQueryable<Car>`, la siguiente función agrega este filtrado a cualquier consulta existente, con independencia del tipo de elemento específico.

### <a name="example"></a>Ejemplo

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Factory_methods_expression_of_tdelegate":::

Como la función `TextFilter` toma y devuelve una interfaz [IQueryable\<T>](xref:System.Linq.IQueryable%601) (y no solo una interfaz <xref:System.Linq.IQueryable>), puede agregar más elementos de consulta con tipo de tiempo de compilación después del filtro de texto.

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Factory_methods_expression_of_tdelegate_usage":::

## <a name="adding-method-call-nodes-to-the-xrefsystemlinqiqueryables-expression-tree"></a>Adición de nodos de llamada de método a la interfaz <xref:System.Linq.IQueryable> del árbol de expresión

Si tiene una interfaz <xref:System.Linq.IQueryable> en lugar de [IQueryable\<T>](xref:System.Linq.IQueryable%601), no puede llamar directamente a los métodos de LINQ genéricos. Una alternativa consiste en crear el árbol de expresión interno como se ha indicado antes y usar la reflexión para invocar el método de LINQ adecuado mientras se pasa el árbol de expresión.

También puede duplicar la funcionalidad del método de LINQ y encapsular todo el árbol en un objeto <xref:System.Linq.Expressions.MethodCallExpression> que represente una llamada al método de LINQ:

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Factory_methods_lambdaexpression":::

Tenga en cuenta que en este caso no tiene un marcador de posición genérico `T` en tiempo de compilación, por lo que usará la sobrecarga de <xref:System.Linq.Expressions.Expression.Lambda%2A> que no necesita información de tipos de tiempo de compilación y que genera un elemento <xref:System.Linq.Expressions.LambdaExpression> en lugar de una instancia de [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601).

## <a name="the-dynamic-linq-library"></a>Biblioteca dinámica de LINQ

La creación de árboles de expresión mediante métodos de generador es relativamente compleja; es más fácil crear cadenas. La [biblioteca dinámica de LINQ](https://dynamic-linq.net/) expone un conjunto de métodos de extensión en <xref:System.Linq.IQueryable> correspondiente a los métodos estándar de LINQ en <xref:System.Linq.Queryable> y que aceptan cadenas en una [sintaxis especial](https://dynamic-linq.net/expression-language) en lugar de árboles de expresión. La biblioteca genera el árbol de expresión adecuado a partir de la cadena y puede devolver la interfaz <xref:System.Linq.IQueryable> traducida resultante.

El ejemplo anterior se podría volver a escribir de esta manera:

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Dynamic_linq":::

## <a name="see-also"></a>Vea también

- [Árboles de expresión (C#)](./index.md)
- [Procedimiento para ejecutar árboles de expresión (C#)](./how-to-execute-expression-trees.md)
- [Especificar dinámicamente filtros con predicado en tiempo de ejecución](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
