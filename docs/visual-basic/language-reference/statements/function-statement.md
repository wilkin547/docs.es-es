---
title: Function (Instrucción)
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 8140c7e6267e66c69c20d413a11d04372400c581
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345917"
---
# <a name="function-statement-visual-basic"></a>Function (Instrucción, Visual Basic)

Declara el nombre, los parámetros y el código que definen un procedimiento `Function`.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a>Elementos

- `attributelist`

  Opcional. Vea [lista de atributos](attribute-list.md).

- `accessmodifier`

  Opcional. Puede ser uno de los siguientes:

  - [Public](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Private](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Opcional. Puede ser uno de los siguientes:

  - [Sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Opcional. Vea [Shared](../../../visual-basic/language-reference/modifiers/shared.md).

- `Shadows`

  Opcional. Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

- `Async`

  Opcional. Vea [Async](../../../visual-basic/language-reference/modifiers/async.md).

- `Iterator`

  Opcional. Vea [iterator](../../../visual-basic/language-reference/modifiers/iterator.md).

- `name`

  Obligatorio. Nombre del procedimiento. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

- `typeparamlist`

  Opcional. Lista de parámetros de tipo para un procedimiento genérico. Consulte [lista de tipos](type-list.md).

- `parameterlist`

  Opcional. Lista de nombres de variables locales que representan los parámetros de este procedimiento. Vea [lista de parámetros](parameter-list.md).

- `returntype`

  Es obligatorio si se `On``Option Strict`. Tipo de datos del valor devuelto por este procedimiento.

- `Implements`

  Opcional. Indica que este procedimiento implementa uno o varios procedimientos de `Function`, cada uno de los cuales se define en una interfaz implementada por la clase o estructura contenedora de este procedimiento. Vea [Implements (instrucción](implements-statement.md)).

- `implementslist`

  Es necesario si se proporciona `Implements`. Lista de procedimientos `Function` que se implementan.

  `implementedprocedure [ , implementedprocedure ... ]`

  Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:

  `interface.definedname`

  |Parte|Descripción|
  |---|---|
  |`interface`|Obligatorio. Nombre de una interfaz implementada por la clase o estructura contenedora de este procedimiento.|
  |`definedname`|Obligatorio. Nombre por el que se define el procedimiento en `interface`.|

- `Handles`

  Opcional. Indica que este procedimiento puede controlar uno o más eventos concretos. Vea [identificadores](handles-clause.md).

- `eventlist`

  Es necesario si se proporciona `Handles`. Lista de eventos que controla este procedimiento.

  `eventspecifier [ , eventspecifier ... ]`

  Cada `eventspecifier` tiene la sintaxis y las partes siguientes:

  `eventvariable.event`

  |Parte|Descripción|
  |---|---|
  |`eventvariable`|Obligatorio. Variable de objeto declarada con el tipo de datos de la clase o estructura que genera el evento.|
  |`event`|Obligatorio. Nombre del evento que controla este procedimiento.|

- `statements`

  Opcional. Bloque de instrucciones que se ejecutarán en este procedimiento.

- `End Function`

  Finaliza la definición de este procedimiento.

## <a name="remarks"></a>Comentarios

Todo el código ejecutable debe estar dentro de un procedimiento. Cada procedimiento, a su vez, se declara dentro de una clase, una estructura o un módulo al que se hace referencia como la clase, estructura o módulo contenedor.

Para devolver un valor al código de llamada, use un procedimiento `Function`; de lo contrario, use un procedimiento `Sub`.

## <a name="defining-a-function"></a>Definir una función

Solo puede definir un procedimiento `Function` en el nivel de módulo. Por lo tanto, el contexto de la declaración de una función debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

`Function` procedimientos tienen como valor predeterminado el acceso público. Los niveles de acceso se pueden ajustar con los modificadores de acceso.

Un procedimiento `Function` puede declarar el tipo de datos del valor que devuelve el procedimiento. Puede especificar cualquier tipo de datos o el nombre de una enumeración, una estructura, una clase o una interfaz. Si no especifica el parámetro `returntype`, el procedimiento devuelve `Object`.

Si este procedimiento usa la palabra clave `Implements`, la clase o estructura contenedora también debe tener una instrucción `Implements` que siga inmediatamente a su instrucción `Class` o `Structure`. La instrucción `Implements` debe incluir cada interfaz que se especifica en `implementslist`. Sin embargo, el nombre por el que una interfaz define el `Function` (en `definedname`) no tiene que coincidir con el nombre de este procedimiento (en `name`).

> [!NOTE]
> Puede usar expresiones lambda para definir expresiones de función alineadas. Para obtener más información, vea [expresión de función](../../../visual-basic/language-reference/operators/function-expression.md) y [expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="returning-from-a-function"></a>Devolver desde una función

Cuando el procedimiento `Function` devuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento.

Para devolver un valor de una función, puede asignar el valor al nombre de la función o incluirlo en una instrucción `Return`.

La instrucción `Return` asigna simultáneamente el valor devuelto y sale de la función, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

En el ejemplo siguiente se asigna el valor devuelto al nombre de función `myFunction` y, a continuación, se usa la instrucción `Exit Function` para devolver.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

Las instrucciones `Exit Function` y `Return` producen una salida inmediata de un procedimiento de `Function`. Cualquier número de instrucciones `Exit Function` y `Return` puede aparecer en cualquier parte del procedimiento y se pueden mezclar instrucciones `Exit Function` y `Return`.

Si usa `Exit Function` sin asignar un valor a `name`, el procedimiento devuelve el valor predeterminado para el tipo de datos especificado en `returntype`. Si no se especifica `returntype`, el procedimiento devuelve `Nothing`, que es el valor predeterminado para `Object`.

## <a name="calling-a-function"></a>Llamar a una función

Se llama a un procedimiento de `Function` mediante el nombre del procedimiento, seguido de la lista de argumentos entre paréntesis, en una expresión. Solo se pueden omitir los paréntesis si no se proporcionan argumentos. Sin embargo, el código es más legible si siempre incluye los paréntesis.

Se llama a un procedimiento `Function` del mismo modo que se llama a cualquier función de biblioteca como `Sqrt`, `Cos`o `ChrW`.

También puede llamar a una función mediante la palabra clave `Call`. En ese caso, se omite el valor devuelto. No se recomienda el uso de la palabra clave `Call` en la mayoría de los casos. Para obtener más información, consulte [instrucción call](call-statement.md).

A veces Visual Basic reorganiza las expresiones aritméticas para aumentar la eficacia interna. Por ese motivo, no debe utilizar un procedimiento `Function` en una expresión aritmética cuando la función cambia el valor de las variables en la misma expresión.

## <a name="async-functions"></a>Funciones asincrónicas

La característica *Async* le permite invocar funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.

Si marca una función con el modificador [Async](../../../visual-basic/language-reference/modifiers/async.md) , puede usar el operador [Await](../../../visual-basic/language-reference/operators/await-operator.md) en la función. Cuando el control alcanza una expresión `Await` en la función `Async`, el control vuelve al llamador y el progreso de la función se suspende hasta que se completa la tarea esperada. Una vez completada la tarea, la ejecución puede reanudarse en la función.

> [!NOTE]
> Un procedimiento `Async` devuelve al autor de la llamada cuando encuentra el primer objeto esperado que aún no se ha completado o hasta el final de la `Async` procedimiento, lo que ocurra primero.

Una función `Async` puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>. A continuación se proporciona un ejemplo de una función de `Async` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.

Una función `Async` no puede declarar ningún parámetro [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) .

Una [instrucción Sub](sub-statement.md) también se puede marcar con el modificador `Async`. Se utiliza principalmente para los controladores de eventos, donde no se puede devolver un valor. No se puede esperar a un procedimiento de `Sub` de `Async`, y el llamador de un procedimiento de `Sub` de `Async` no puede detectar las excepciones producidas por el procedimiento `Sub`.

Para obtener más información sobre las funciones de `Async`, vea [programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flujo de control en programas asincrónicos](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)y [tipos de valor devueltos asincrónicos](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

## <a name="iterator-functions"></a>Funciones de iterador

Una función de *iterador* realiza una iteración personalizada en una colección, como una lista o una matriz. Una función de iterador utiliza la instrucción [yield](yield-statement.md) para devolver cada elemento de uno en uno. Cuando se alcanza una instrucción [yield](yield-statement.md) , se recuerda la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.

Se llama a un iterador desde el código de cliente mediante un método [for each... Instrucción siguiente](for-each-next-statement.md) .

El tipo de valor devuelto de una función de iterador puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>o <xref:System.Collections.Generic.IEnumerator%601>.

Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la instrucción `Function` para declarar el nombre, los parámetros y el código que forman el cuerpo de un procedimiento `Function`. El modificador `ParamArray` permite que la función acepte un número variable de argumentos.

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se invoca la función declarada en el ejemplo anterior.

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, `DelayAsync` es un `Function` de `Async` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>. `DelayAsync` tiene una instrucción `Return` que devuelve un entero. Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)`. Dado que el tipo de valor devuelto es `Task(Of Integer)`, la evaluación de la expresión de `Await` en `DoSomethingAsync` produce un entero. Esto se muestra en esta instrucción: `Dim result As Integer = Await delayTask`.

El procedimiento `startButton_Click` es un ejemplo de un procedimiento `Async Sub`. Dado que `DoSomethingAsync` es una función `Async`, se debe esperar la tarea para la llamada a `DoSomethingAsync`, como se muestra en la siguiente instrucción: `Await DoSomethingAsync()`. El procedimiento de `Sub` de `startButton_Click` debe definirse con el modificador `Async` porque tiene una expresión de `Await`.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>Vea también

- [Sub (instrucción)](sub-statement.md)
- [Procedimientos de función](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [Lista de parámetros](parameter-list.md)
- [Dim (instrucción)](dim-statement.md)
- [Call (instrucción)](call-statement.md)
- [Of](of-clause.md)
- [Matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Solución de problemas de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Expresión de función](../../../visual-basic/language-reference/operators/function-expression.md)
