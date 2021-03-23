---
title: Consultas basadas en el estado de tiempo de ejecución (Visual Basic)
description: Se describen diversas técnicas que el código puede usar para realizar consultas de forma dinámica según el estado del entorno de ejecución, mediante la modificación de las llamadas a métodos de LINQ o los árboles de expresión pasados a esos métodos.
ms.date: 02/14/2021
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
ms.openlocfilehash: fe59fc8287e67247884cfdcf1bacc6ed2a447e5a
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104875881"
---
# <a name="querying-based-on-runtime-state-visual-basic"></a>Consultas basadas en el estado de tiempo de ejecución (Visual Basic)

Considere el código que define un <xref:System.Linq.IQueryable> o un [IQueryable (of T)](<xref:System.Linq.IQueryable%601>) en un origen de datos:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Initialize":::

Cada vez que ejecute este código, se ejecutará la misma consulta exacta. Esto no suele ser muy útil, ya que es posible que quiera que el código ejecute otras consultas en función de las condiciones en el momento de la ejecución. En este artículo se describe cómo puede ejecutar otra consulta en función del estado del entorno de ejecución.

## <a name="iqueryable--iqueryableof-t-and-expression-trees"></a>IQueryable/IQueryable (of T) y árboles de expresión

Fundamentalmente, una interfaz <xref:System.Linq.IQueryable> tiene dos componentes:

* <xref:System.Linq.IQueryable.Expression>&mdash;representación independiente del lenguaje y del origen de datos de los componentes de la consulta actual, en forma de un árbol de expresión.
* <xref:System.Linq.IQueryable.Provider>&mdash;instancia de un proveedor LINQ, que sabe cómo materializar la consulta actual en un valor o un conjunto de valores.

En el contexto de las consultas dinámicas, el proveedor normalmente seguirá siendo el mismo; el árbol de expresión de la consulta variará entre consultas.

Los árboles de expresión son inmutables; si quiere otro árbol de expresión (y, por tanto, otra consulta), tendrá que convertir el existente en uno nuevo y, de este modo, en una nueva interfaz <xref:System.Linq.IQueryable>.

En las secciones siguientes se describen técnicas específicas para realizar consultas de forma diferente en respuesta al estado del entorno de ejecución:

- Uso del estado del entorno de ejecución desde el árbol de expresión
- Llamada a métodos de LINQ adicionales
- Variación del árbol de expresión que se pasa a los métodos de LINQ
- Construya un árbol [de expresión de expresión (of TDelegate)](xref:System.Linq.Expressions.Expression%601) mediante los métodos de generador en <xref:System.Linq.Expressions.Expression>
- Adición de nodos de llamada de método al árbol de expresión de <xref:System.Linq.IQueryable>
- Construcción de cadenas y uso de la [biblioteca dinámica de LINQ](https://dynamic-linq.net/)

## <a name="use-runtime-state-from-within-the-expression-tree"></a>Uso del estado del entorno de ejecución desde el árbol de expresión

Siempre que el proveedor LINQ lo admita, la manera más sencilla de realizar consultas dinámicas consiste en hacer referencia al estado del entorno de ejecución de forma directa en la consulta mediante una variable cerrada, como `length` en el ejemplo de código siguiente:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Runtime_state_from_within_expression_tree":::

El árbol de expresión interno (y, por tanto, la consulta) no se ha modificado; la consulta devuelve otros valores solo porque se ha cambiado el valor de `length`.

## <a name="call-additional-linq-methods"></a>Llamada a métodos de LINQ adicionales

Por lo general, los [métodos de LINQ integrados](https://github.com/dotnet/runtime/blob/main/src/libraries/System.Linq.Queryable/src/System/Linq/Queryable.cs) en <xref:System.Linq.Queryable> realizan dos pasos:

* Encapsulan el árbol de expresión actual en un elemento <xref:System.Linq.Expressions.MethodCallExpression> que representa la llamada de método.
* Vuelven a pasar el árbol de expresión encapsulado al proveedor, ya sea para devolver un valor mediante el método <xref:System.Linq.IQueryProvider.Execute%2A?displayProperty=nameWithType> del proveedor, o bien para devolver un objeto de consulta traducido mediante el método <xref:System.Linq.IQueryProvider.CreateQuery%2A?displayProperty=nameWithType>.

Puede reemplazar la consulta original con el resultado de un método [IQueryable (of T)](xref:System.Linq.IQueryable%601)que devuelve para obtener una nueva consulta. Puede hacerlo condicionalmente en función del estado del entorno de ejecución, como en el ejemplo siguiente:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Added_method_calls":::

## <a name="vary-the-expression-tree-passed-into-the-linq-methods"></a>Variación del árbol de expresión que se pasa a los métodos de LINQ

Puede pasar otras expresiones a los métodos de LINQ, en función del estado del entorno de ejecución:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Varying_expressions":::

También es posible que quiera crear las distintas subexpresiones mediante una biblioteca de terceros, como [PredicateBuilder](http://www.albahari.com/nutshell/predicatebuilder.aspx) de [LinqKit](http://www.albahari.com/nutshell/linqkit.aspx):

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compose_expression":::

## <a name="construct-expression-trees-and-queries-using-factory-methods"></a>Creación de árboles de expresión y consultas mediante métodos de generador

En todos los ejemplos vistos hasta ahora, se ha conocido el tipo de elemento en tiempo de compilación `String` y, por tanto, el tipo de la consulta `IQueryable(Of String)`. Es posible que necesite agregar componentes a una consulta de cualquier tipo de elemento o agregar componentes diferentes en función del tipo de elemento. Puede crear árboles de expresión desde cero, con los métodos de generador de <xref:System.Linq.Expressions.Expression?displayProperty=fullName> y, por tanto, adaptar la expresión del entorno de ejecución a un tipo de elemento específico.

### <a name="constructing-an-expressionof-tdelegate"></a>Construir una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601)

Cuando se construye una expresión para pasar a uno de los métodos LINQ, en realidad se construye una instancia de [Expression (of TDelegate)](xref:System.Linq.Expressions.Expression%601), donde `TDelegate` es un tipo de delegado como `Func(Of String, Boolean)` , `Action` o un tipo de delegado personalizado.

[Expresión (de TDelegate))](xref:System.Linq.Expressions.Expression%601) hereda de <xref:System.Linq.Expressions.LambdaExpression> , que representa una expresión lambda completa como la siguiente:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compiler_generated":::

<xref:System.Linq.Expressions.LambdaExpression> tiene dos componentes:

* una lista de parámetros `(x As String)` representada por la propiedad <xref:System.Linq.Expressions.LambdaExpression.Parameters>.
* un cuerpo `x.StartsWith("a")` representado por la propiedad <xref:System.Linq.Expressions.LambdaExpression.Body>.

Los pasos básicos para construir una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601) son los siguientes:

* Defina objetos <xref:System.Linq.Expressions.ParameterExpression> para cada uno de los parámetros (si existen) de la expresión lambda, mediante el método generador <xref:System.Linq.Expressions.Expression.Parameter%2A>.

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_parameter":::

* Construya el cuerpo de <xref:System.Linq.Expressions.LambdaExpression> utilizando los valores <xref:System.Linq.Expressions.ParameterExpression> definidos por el usuario y los métodos de generador en <xref:System.Linq.Expressions.Expression>. Por ejemplo, una expresión que represente `x.StartsWith("a")` se podría crear de la siguiente manera:

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_body":::

* Ajuste los parámetros y el cuerpo en una expresión de tipo en tiempo de compilación [(de TDelegate)](xref:System.Linq.Expressions.Expression%601), con la <xref:System.Linq.Expressions.Expression.Lambda%2A> sobrecarga de Factory Method adecuada:

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_lambda":::

En las secciones siguientes se describe un escenario en el que es posible que desee crear una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601) para pasarla a un método LINQ y proporcionar un ejemplo completo de cómo hacerlo mediante los métodos de generador.

### <a name="scenario"></a>Escenario

Imagine que tiene varios tipos de entidad:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Entities.vb":::

En cualquiera de estos tipos de entidad, quiere filtrar y devolver solo las entidades que contengan un texto concreto dentro de uno de sus campos `string`. Para `Person`, le interesa buscar las propiedades `FirstName` y `LastName`:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="PersonsQry":::

Pero para `Car`, solo quiere buscar la propiedad `Model`:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="CarsQry":::

Aunque podría escribir una función personalizada para `IQueryable(Of Person)` y otra para `IQueryable(Of Car)`, la siguiente función agrega este filtrado a cualquier consulta existente, con independencia del tipo de elemento específico.

### <a name="example"></a>Ejemplo

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate":::

Dado `TextFilter` que la función toma y devuelve un [IQueryable (of T)](xref:System.Linq.IQueryable%601) (y no solo un <xref:System.Linq.IQueryable> ), puede agregar más elementos de consulta con tipo en tiempo de compilación después del filtro de texto.

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate_usage":::

## <a name="add-method-call-nodes-to-the-xrefsystemlinqiqueryables-expression-tree"></a>Adición de nodos de llamada de método al árbol de expresión de <xref:System.Linq.IQueryable>

Si tiene <xref:System.Linq.IQueryable> en lugar de [IQueryable (of T)](xref:System.Linq.IQueryable%601), no puede llamar directamente a los métodos LINQ genéricos. Una alternativa consiste en crear el árbol de expresión interno como se ha indicado antes y usar la reflexión para invocar el método de LINQ adecuado mientras se pasa el árbol de expresión.

También puede duplicar la funcionalidad del método de LINQ y encapsular todo el árbol en un objeto <xref:System.Linq.Expressions.MethodCallExpression> que represente una llamada al método de LINQ:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_lambdaexpression":::

Tenga en cuenta que en este caso no tiene un marcador de posición genérico en tiempo de compilación `T` , por lo que usará la <xref:System.Linq.Expressions.Expression.Lambda%2A> sobrecarga, que no requiere información de tipo en tiempo de compilación, y que genera un <xref:System.Linq.Expressions.LambdaExpression> en lugar de una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601).

## <a name="the-dynamic-linq-library"></a>Biblioteca dinámica de LINQ

La creación de árboles de expresión mediante métodos de generador es relativamente compleja; es más fácil crear cadenas. La [biblioteca dinámica de LINQ](https://dynamic-linq.net/) expone un conjunto de métodos de extensión en <xref:System.Linq.IQueryable> correspondiente a los métodos estándar de LINQ en <xref:System.Linq.Queryable> y que aceptan cadenas en una [sintaxis especial](https://dynamic-linq.net/expression-language) en lugar de árboles de expresión. La biblioteca genera el árbol de expresión adecuado a partir de la cadena y puede devolver la interfaz <xref:System.Linq.IQueryable> traducida resultante.

Por ejemplo, el ejemplo anterior (incluida la construcción del árbol de expresión) se podría volver a escribir de la siguiente manera:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Dynamic_linq":::

## <a name="see-also"></a>Consulte también

- [Árboles de expresión (Visual Basic)](index.md)
- [How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md) (Cómo ejecutar árboles de expresión en Visual Basic)
