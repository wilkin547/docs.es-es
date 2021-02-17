---
title: Consultas basadas en el estado de tiempo de ejecución (Visual Basic)
description: Describe diversas técnicas que el código puede utilizar para consultar dinámicamente según el estado de tiempo de ejecución, mediante la modificación de las llamadas a métodos LINQ o los árboles de expresión pasados a esos métodos.
ms.date: 02/14/2021
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
ms.openlocfilehash: c9f57950b2c26c0cca798ab632da90bf9f6c519a
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100584858"
---
# <a name="querying-based-on-runtime-state-visual-basic"></a>Consultas basadas en el estado de tiempo de ejecución (Visual Basic)

Considere el código que define un <xref:System.Linq.IQueryable> o un [IQueryable (of T)](<xref:System.Linq.IQueryable%601>) en un origen de datos:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Initialize":::

Cada vez que ejecute este código, se ejecutará la misma consulta exacta. Esto no suele ser muy útil, ya que puede que desee que el código ejecute consultas diferentes en función de las condiciones en tiempo de ejecución. En este artículo se describe cómo puede ejecutar una consulta diferente en función del estado de tiempo de ejecución.

## <a name="iqueryable--iqueryableof-t-and-expression-trees"></a>IQueryable/IQueryable (of T) y árboles de expresión

Fundamentalmente, un <xref:System.Linq.IQueryable> tiene dos componentes:

* <xref:System.Linq.IQueryable.Expression>&mdash;una representación independiente del lenguaje y del origen de orígenes de los componentes de la consulta actual, en forma de un árbol de expresión.
* <xref:System.Linq.IQueryable.Provider>&mdash;instancia de un proveedor LINQ, que sabe cómo materializar la consulta actual en un valor o un conjunto de valores.

En el contexto de las consultas dinámicas, el proveedor normalmente seguirá siendo el mismo. el árbol de expresión de la consulta variará de una consulta a una consulta.

Los árboles de expresión son inmutables; Si desea un árbol de expresión diferente &mdash; y, por tanto, una consulta diferente deberá &mdash; traducir el árbol de expresión existente a uno nuevo y, por tanto, a un nuevo <xref:System.Linq.IQueryable> .

En las secciones siguientes se describen técnicas específicas para realizar consultas de forma diferente en respuesta al estado en tiempo de ejecución:

- Usar el estado de tiempo de ejecución desde el árbol de expresión
- Llamar a métodos LINQ adicionales
- Variar el árbol de expresión que se pasa a los métodos LINQ
- Construya un árbol [de expresión de expresión (of TDelegate)](xref:System.Linq.Expressions.Expression%601) mediante los métodos de generador en <xref:System.Linq.Expressions.Expression>
- Agregar nodos de llamada de método a un <xref:System.Linq.IQueryable> árbol de expresión de
- Construir cadenas y usar la [biblioteca dinámica de LINQ](https://dynamic-linq.net/)

## <a name="use-runtime-state-from-within-the-expression-tree"></a>Usar el estado de tiempo de ejecución desde el árbol de expresión

Suponiendo que el proveedor LINQ lo admita, la manera más sencilla de consultar dinámicamente es hacer referencia al estado de tiempo de ejecución directamente en la consulta a través de una variable cerrada, como `length` en el ejemplo de código siguiente:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Runtime_state_from_within_expression_tree":::

El árbol de expresión interno &mdash; y, por tanto, &mdash; no se ha modificado la consulta; la consulta devuelve valores diferentes solo porque se ha cambiado el valor de `length` .

## <a name="call-additional-linq-methods"></a>Llamar a métodos LINQ adicionales

Por lo general, los [métodos integrados de LINQ](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Linq.Queryable/src/System/Linq/Queryable.cs) en <xref:System.Linq.Queryable> realizan dos pasos:

* Ajusta el árbol de expresión actual en un objeto <xref:System.Linq.Expressions.MethodCallExpression> que representa la llamada al método.
* Vuelva a pasar el árbol de la expresión ajustada al proveedor, ya sea para devolver un valor a través del método del proveedor <xref:System.Linq.IQueryProvider.Execute%2A?displayProperty=nameWithType> ; o para devolver un objeto de consulta traducido a través del <xref:System.Linq.IQueryProvider.CreateQuery%2A?displayProperty=nameWithType> método.

Puede reemplazar la consulta original con el resultado de un método [IQueryable (of T)](xref:System.Linq.IQueryable%601)que devuelve para obtener una nueva consulta. Puede hacerlo condicionalmente en función del estado de tiempo de ejecución, como en el ejemplo siguiente:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Added_method_calls":::

## <a name="vary-the-expression-tree-passed-into-the-linq-methods"></a>Variar el árbol de expresión que se pasa a los métodos LINQ

Puede pasar expresiones diferentes a los métodos LINQ, dependiendo del estado del tiempo de ejecución:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Varying_expressions":::

También puede que desee crear las distintas subexpresiones mediante una biblioteca de terceros como [PredicateBuilder](http://www.albahari.com/nutshell/predicatebuilder.aspx)de [LinqKit](http://www.albahari.com/nutshell/linqkit.aspx):

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compose_expression":::

## <a name="construct-expression-trees-and-queries-using-factory-methods"></a>Crear árboles de expresión y consultas mediante métodos de generador

En todos los ejemplos hasta este punto, hemos conocido el tipo de elemento en tiempo de compilación &mdash; `String` &mdash; y, por tanto, el tipo de la consulta &mdash; `IQueryable(Of String)` . Es posible que necesite agregar componentes a una consulta de cualquier tipo de elemento o agregar componentes diferentes en función del tipo de elemento. Puede crear árboles de expresión desde el principio, utilizando los métodos de generador en <xref:System.Linq.Expressions.Expression?displayProperty=fullName> y, por tanto, adaptar la expresión en tiempo de ejecución a un tipo de elemento específico.

### <a name="constructing-an-expressionof-tdelegate"></a>Construir una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601)

Cuando se construye una expresión para pasar a uno de los métodos LINQ, en realidad se construye una instancia de [Expression (of TDelegate)](xref:System.Linq.Expressions.Expression%601), donde `TDelegate` es un tipo de delegado como `Func(Of String, Boolean)` , `Action` o un tipo de delegado personalizado.

[Expresión (de TDelegate))](xref:System.Linq.Expressions.Expression%601) hereda de <xref:System.Linq.Expressions.LambdaExpression> , que representa una expresión lambda completa como la siguiente:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compiler_generated":::

Un <xref:System.Linq.Expressions.LambdaExpression> tiene dos componentes:

* una lista de parámetros &mdash; `(x As String)` &mdash; representada por la <xref:System.Linq.Expressions.LambdaExpression.Parameters> propiedad
* cuerpo &mdash; `x.StartsWith("a")` &mdash; representado por la <xref:System.Linq.Expressions.LambdaExpression.Body> propiedad.

Los pasos básicos para construir una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601) son los siguientes:

* Defina los <xref:System.Linq.Expressions.ParameterExpression> objetos para cada uno de los parámetros (si existen) en la expresión lambda, mediante el <xref:System.Linq.Expressions.Expression.Parameter%2A> Factory Method.

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_parameter":::

* Construya el cuerpo de la <xref:System.Linq.Expressions.LambdaExpression> , utilizando las <xref:System.Linq.Expressions.ParameterExpression> (s) definidas por el usuario y los métodos de generador en <xref:System.Linq.Expressions.Expression> . Por ejemplo, una expresión que representa `x.StartsWith("a")` se podría construir de la siguiente manera:

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_body":::

* Ajuste los parámetros y el cuerpo en una expresión de tipo en tiempo de compilación [(de TDelegate)](xref:System.Linq.Expressions.Expression%601), con la <xref:System.Linq.Expressions.Expression.Lambda%2A> sobrecarga de Factory Method adecuada:

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_lambda":::

En las secciones siguientes se describe un escenario en el que es posible que desee crear una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601) para pasarla a un método LINQ y proporcionar un ejemplo completo de cómo hacerlo mediante los métodos de generador.

### <a name="scenario"></a>Escenario

Supongamos que tiene varios tipos de entidad:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Entities.vb":::

Para cualquiera de estos tipos de entidad, desea filtrar y devolver solo las entidades que tienen un texto determinado dentro de uno de sus `string` campos. Para `Person` , desea buscar en las `FirstName` `LastName` propiedades y:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="PersonsQry":::

pero para `Car` , querrá buscar solo la `Model` propiedad:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="CarsQry":::

Aunque podría escribir una función personalizada para `IQueryable(Of Person)` y otra para `IQueryable(Of Car)` , la función siguiente agrega este filtrado a cualquier consulta existente, con independencia del tipo de elemento específico.

### <a name="example"></a>Ejemplo

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate":::

Dado `TextFilter` que la función toma y devuelve un [IQueryable (of T)](xref:System.Linq.IQueryable%601) (y no solo un <xref:System.Linq.IQueryable> ), puede agregar más elementos de consulta con tipo en tiempo de compilación después del filtro de texto.

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate_usage":::

## <a name="add-method-call-nodes-to-the-xrefsystemlinqiqueryables-expression-tree"></a>Agregar nodos de llamada de método al <xref:System.Linq.IQueryable> árbol de expresión de

Si tiene <xref:System.Linq.IQueryable> en lugar de [IQueryable (of T)](xref:System.Linq.IQueryable%601), no puede llamar directamente a los métodos LINQ genéricos. Una alternativa consiste en crear el árbol de expresión interno como se indicó anteriormente y usar la reflexión para invocar el método LINQ adecuado mientras se pasa el árbol de expresión.

También puede duplicar la funcionalidad del método de LINQ, ajustando todo el árbol en un <xref:System.Linq.Expressions.MethodCallExpression> que representa una llamada al método LINQ:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_lambdaexpression":::

Tenga en cuenta que en este caso no tiene un marcador de posición genérico en tiempo de compilación `T` , por lo que usará la <xref:System.Linq.Expressions.Expression.Lambda%2A> sobrecarga, que no requiere información de tipo en tiempo de compilación, y que genera un <xref:System.Linq.Expressions.LambdaExpression> en lugar de una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601).

## <a name="the-dynamic-linq-library"></a>Biblioteca dinámica de LINQ

La construcción de árboles de expresión mediante métodos de generador es relativamente compleja; es más fácil crear cadenas. La [biblioteca dinámica de LINQ](https://dynamic-linq.net/) expone un conjunto de métodos de extensión en que <xref:System.Linq.IQueryable> corresponden a los métodos estándar de LINQ en <xref:System.Linq.Queryable> y que aceptan cadenas en una [Sintaxis especial](https://dynamic-linq.net/expression-language) en lugar de árboles de expresión. La biblioteca genera el árbol de expresión adecuado a partir de la cadena y puede devolver el resultado traducido <xref:System.Linq.IQueryable> .

Por ejemplo, el ejemplo anterior (incluida la construcción del árbol de expresión) se podría volver a escribir de la siguiente manera:

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Dynamic_linq":::

## <a name="see-also"></a>Consulte también

- [Árboles de expresión (Visual Basic)](index.md)
- [How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md) (Cómo ejecutar árboles de expresión en Visual Basic)
