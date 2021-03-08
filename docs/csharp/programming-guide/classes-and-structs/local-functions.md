---
title: 'Funciones locales: Guía de programación de C#'
description: En C#, las funciones locales son métodos privados que están anidados en otro miembro y se pueden llamar desde su miembro contenedor.
ms.date: 10/16/2020
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: 1c0cd1b8122f9069e5d6385d698f0ff8278912dd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103249"
---
# <a name="local-functions-c-programming-guide"></a>Funciones locales (Guía de programación de C#)

A partir de C# 7.0, C# admite *funciones locales*. Las funciones locales son métodos privados de un tipo que están anidados en otro miembro. Solo se pueden llamar desde su miembro contenedor. Las funciones locales se pueden declarar en y llamar desde:

- Métodos, especialmente los métodos de iterador y asincrónicos
- Constructores
- Descriptores de acceso de propiedad
- Descriptores de acceso de un evento
- Métodos anónimos
- Expresiones lambda
- Finalizadores
- Otras funciones locales

En cambio, las funciones locales no se pueden declarar dentro de un miembro con forma de expresión.

> [!NOTE]
> En algunos casos, puede usar una expresión lambda para implementar funcionalidad compatible también con una función local. Para ver una comparación, consulte [Funciones locales frente a expresiones lambda](#local-functions-vs-lambda-expressions).

Las funciones locales aclaran la intención del código. Cualquiera que lea el código puede ver que solo el método que lo contiene puede llamar al método. Para los proyectos de equipo, también hacen que sea imposible que otro desarrollador llame erróneamente al método de forma directa desde cualquier otro punto de la clase o estructura.

## <a name="local-function-syntax"></a>Sintaxis de función local

Una función local se define como un método anidado dentro de un miembro contenedor. Su definición tiene la siguiente sintaxis:

```csharp
<modifiers> <return-type> <method-name> <parameter-list>
```

Puede usar los siguientes modificadores con una función local:

- [`async`](../../language-reference/keywords/async.md)
- [`unsafe`](../../language-reference/keywords/unsafe.md)
- [`static`](../../language-reference/keywords/static.md) (en C# 8.0 y posterior). Una función local estática no puede capturar variables locales o el estado de la instancia.
- [`extern`](../../language-reference/keywords/extern.md) (en C# 9.0 y posterior). Una función local externa debe ser `static`.

Todas las variables locales que se definen en el miembro contenedor, incluidos sus parámetros de método, son accesibles en la función local no estática.

A diferencia de una definición de método, una definición de función local no puede incluir el modificador de acceso de los miembros. Dado que todas las funciones locales son privadas, incluido un modificador de acceso, como la palabra clave `private`, se genera el error del compilador CS0106, "El modificador 'private' no es válido para este elemento".

En el ejemplo siguiente, se define una función local denominada `AppendPathSeparator` que es privada a un método denominado `GetText`:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="Basic" :::

A partir de C# 9.0, puede aplicar atributos a una función local, sus parámetros y parámetros de tipo, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="WithAttributes" :::

En el ejemplo anterior se usa un [atributo especial](../../language-reference/attributes/nullable-analysis.md) para ayudar al compilador en el análisis estático en un contexto que acepta valores NULL.

## <a name="local-functions-and-exceptions"></a>Excepciones y funciones locales

Una de las características útiles de las funciones locales es que pueden permitir que las excepciones aparezcan inmediatamente. Para los iteradores de método, las excepciones aparecen solo cuando la secuencia devuelta se enumera y no cuando se recupera el iterador. Para los métodos asincrónicos, las excepciones producidas en un método asincrónico se observan cuando se espera la tarea devuelta.

En el ejemplo siguiente se define un método `OddSequence` que enumera los números impares de un intervalo especificado. Dado que pasa un número mayor de 100 al método de enumerador `OddSequence`, el método produce una excepción <xref:System.ArgumentOutOfRangeException>. Como se muestra en el resultado del ejemplo, la excepción aparece solo cuando itera los números, y no al recuperar el enumerador.

:::code language="csharp" source="snippets/local-functions/IteratorWithoutLocal.cs" :::

Si coloca la lógica de iterador en una función local, se iniciarán excepciones de validación de argumentos al recuperar el enumerador, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/local-functions/IteratorWithLocal.cs" :::

## <a name="local-functions-vs-lambda-expressions"></a>Funciones locales frente a expresiones lambda

A primera vista, las funciones locales y las [expresiones lambda](../../language-reference/operators/lambda-expressions.md) son muy similares. En muchos casos, la elección entre usar expresiones lambda y funciones locales es una cuestión de estilo y de preferencia personal, aunque hay diferencias que debe tener en cuenta acerca de dónde puede usar una u otra.

Vamos a examinar las diferencias entre las implementaciones de la función local y la expresión lambda del algoritmo factorial. Esta es la versión que usa una función local:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="FactorialWithLocal" :::

Esta versión usa expresiones lambda:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="FactorialWithLambda" :::

### <a name="naming"></a>Nomenclatura

Las funciones locales se nombran explícitamente como métodos. Las expresiones lambda son métodos anónimos y deben asignarse a variables de un tipo `delegate`, normalmente los tipos `Action` o `Func`. Cuando se declara una función local, el proceso es como escribir un método normal: se declaran un tipo de valor devuelto y una signatura de función.

### <a name="function-signatures-and-lambda-expression-types"></a>Signaturas de función y tipos de expresiones lambda

Las expresiones lambda se basan en el tipo de la variable `Action`/`Func` al que están asignadas para determinar los tipos de argumento y de valor devuelto. En las funciones locales, dado que la sintaxis se parece mucho a escribir un método normal, los tipos de argumento y el tipo de valor devuelto ya forman parte de la declaración de función.

### <a name="definite-assignment"></a>Asignación definitiva

Las expresiones lambda son objetos que se declaran y se asignan en tiempo de ejecución. Para poder usar una expresión lambda, debe asignarse definitivamente: se debe declarar la variable `Action`/`Func` a la que se va a asignar y luego asignar a esta la expresión lambda. Observe que `LambdaFactorial` debe declarar e inicializar la expresión lambda `nthFactorial` antes de definirla. De no hacerlo, se produce un error en tiempo de compilación por hacer referencia a `nthFactorial` antes de asignarlo.

Las funciones locales se definen en tiempo de compilación. Dado que no están asignadas a variables, se puede hacer referencia a ellas desde cualquier ubicación del código **que esté en ámbito**; en el primer ejemplo `LocalFunctionFactorial`, se podría declarar la función local por encima o por debajo de la instrucción `return` y no desencadenar ningún error del compilador.

Estas diferencias implican que los algoritmos recursivos son más fáciles de crear usando funciones locales. Puede declarar y definir una función local que se llama a sí misma. Las expresiones lambda se deben declarar y se les debe asignar un valor predeterminado para que se les pueda volver a asignar un cuerpo que haga referencia a la misma expresión lambda.

### <a name="implementation-as-a-delegate"></a>Implementación como delegado

Las expresiones lambda se convierten en delegados en el momento en que se declaran. Las funciones locales son más flexibles, ya que se pueden escribir como un método tradicional *o* como un delegado. Las funciones locales solo se convierten en delegados cuando ***se usan*** como delegados.

Si se declara una función local y solo se hace referencia a ella llamándola como un método, no se convertirá en un delegado.

### <a name="variable-capture"></a>Captura de variables

Las reglas de [asignación definitiva](../../../../_csharplang/spec/variables.md#definite-assignment) también afectan a las variables capturadas por la función local o la expresión lambda. El compilador puede efectuar un análisis estático que permite a las funciones locales asignar definitivamente variables capturadas en el ámbito de inclusión. Considere este ejemplo:

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

El compilador puede determinar que `LocalFunction` asigna `y` definitivamente cuando se le llama. Como se llama a `LocalFunction` antes de la instrucción `return`, `y` se asigna definitivamente en la instrucción `return`.

Observe que cuando una función local captura variables en el ámbito de inclusión, la función local se implementa como un tipo delegado.

### <a name="heap-allocations"></a>Asignaciones de montón

Dependiendo de su uso, las funciones locales pueden evitar las asignaciones de montón que siempre son necesarias para las expresiones lambda. Si una función local no se convierte nunca en un delegado y ninguna de las variables capturadas por la función local se captura con otras expresiones lambda o funciones locales que se han convertido en delegados, el compilador puede evitar las asignaciones de montón.

Considere este ejemplo asincrónico:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="AsyncWithLambda" :::

La clausura de esta expresión lambda contiene las variables `address`, `index` y `name`. En el caso de las funciones locales, el objeto que implementa el cierre puede ser un tipo `struct`. Luego, ese tipo de estructura se pasaría por referencia a la función local. Esta diferencia de implementación supondría un ahorro en una asignación.

La creación de instancias necesaria para las expresiones lambda significa asignaciones de memoria adicionales, lo que puede ser un factor de rendimiento en rutas de acceso de código crítico en el tiempo. Las funciones locales no suponen esta sobrecarga. En el ejemplo anterior, la versión de las funciones locales tiene dos asignaciones menos que la versión de la expresión lambda.

Si sabe que la función local no se va a convertir en delegado y ninguna de las variables capturadas por ella han sido capturadas por otras expresiones lambda o funciones locales que se han convertido en delegados, puede garantizar la no asignación de la función local al montón al declararla como función local `static`. Observe que esta característica está disponible en C# 8.0 y versiones más recientes.

> [!NOTE]
> La función local equivalente de este método también usa una clase para el cierre. Si el cierre de una función local se implementa como `class` o `struct` es un detalle de implementación. Una función local puede usar `struct` mientras una expresión lambda siempre usará `class`.

:::code language="csharp" source="snippets/local-functions/Program.cs" id="AsyncWithLocal" :::

### <a name="usage-of-the-yield-keyword"></a>Uso de la palabra clave `yield`

Una ventaja final que no se muestra en este ejemplo es que las funciones locales pueden implementarse como iteradores, con la sintaxis `yield return` para producir una secuencia de valores.

:::code language="csharp" source="snippets/local-functions/Program.cs" id="YieldReturn" :::

La instrucción `yield return` no se permite en las expresiones lambda; vea el [Error del compilador CS1621](../../misc/cs1621.md).

Aunque las funciones locales pueden parecer redundantes con respecto a las expresiones lambda, en realidad tienen finalidades y usos diferentes. Las funciones locales son más eficaces si se quiere escribir una función a la que solo se llame desde el contexto de otro método.

## <a name="see-also"></a>Vea también

- [Métodos](methods.md)
