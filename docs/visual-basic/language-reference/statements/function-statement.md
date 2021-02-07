---
description: 'Más información sobre: function (instrucción) (Visual Basic)'
title: Instrucción Function
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
ms.openlocfilehash: e8a05b02c3a214f0572e85c1fc973cb9f03118ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769070"
---
# <a name="function-statement-visual-basic"></a>Function (Instrucción, Visual Basic)

Declara el nombre, los parámetros y el código que definen un `Function` procedimiento.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a>Partes

- `attributelist`

  Opcional. Vea [lista de atributos](attribute-list.md).

- `accessmodifier`

  Opcional. Puede ser uno de los siguientes:

  - [Público](../modifiers/public.md)

  - [Protegido](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Privado](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

  Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Opcional. Puede ser uno de los siguientes:

  - [Sobrecargas](../modifiers/overloads.md)

  - [Invalidaciones](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Opcional. Vea [Shared](../modifiers/shared.md).

- `Shadows`

  Opcional. Vea [Shadows](../modifiers/shadows.md).

- `Async`

  Opcional. Vea [Async](../modifiers/async.md).

- `Iterator`

  Opcional. Vea [iterator](../modifiers/iterator.md).

- `name`

  Necesario. Nombre del procedimiento. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `typeparamlist`

  Opcional. Lista de parámetros de tipo para un procedimiento genérico. Consulte [lista de tipos](type-list.md).

- `parameterlist`

  Opcional. Lista de nombres de variables locales que representan los parámetros de este procedimiento. Vea [lista de parámetros](parameter-list.md).

- `returntype`

  Obligatorio si `Option Strict` es `On` . Tipo de datos del valor devuelto por este procedimiento.

- `Implements`

  Opcional. Indica que este procedimiento implementa uno o más `Function` procedimientos, cada uno de ellos definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento. Vea [Implements (instrucción](implements-statement.md)).

- `implementslist`

  Es necesario si se proporciona `Implements`. Lista de procedimientos `Function` que se implementan.

  `implementedprocedure [ , implementedprocedure ... ]`

  Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:

  `interface.definedname`

  |Parte|Descripción|
  |---|---|
  |`interface`|Necesario. Nombre de una interfaz implementada por la clase o estructura contenedora de este procedimiento.|
  |`definedname`|Necesario. Nombre por el que se define el procedimiento en `interface`.|

- `Handles`

  Opcional. Indica que este procedimiento puede controlar uno o más eventos concretos. Vea [identificadores](handles-clause.md).

- `eventlist`

  Es necesario si se proporciona `Handles`. Lista de eventos que controla este procedimiento.

  `eventspecifier [ , eventspecifier ... ]`

  Cada `eventspecifier` tiene la sintaxis y las partes siguientes:

  `eventvariable.event`

  |Parte|Descripción|
  |---|---|
  |`eventvariable`|Necesario. Variable de objeto declarada con el tipo de datos de la clase o estructura que genera el evento.|
  |`event`|Necesario. Nombre del evento que controla este procedimiento.|

- `statements`

  Opcional. Bloque de instrucciones que se ejecutarán en este procedimiento.

- `End Function`

  Finaliza la definición de este procedimiento.

## <a name="remarks"></a>Observaciones

Todo el código ejecutable debe estar dentro de un procedimiento. Cada procedimiento, a su vez, se declara dentro de una clase, una estructura o un módulo al que se hace referencia como la clase, estructura o módulo contenedor.

Para devolver un valor al código de llamada, use un `Function` procedimiento; de lo contrario, use un `Sub` procedimiento.

## <a name="defining-a-function"></a>Definir una función

Solo puede definir un `Function` procedimiento en el nivel de módulo. Por lo tanto, el contexto de la declaración de una función debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

`Function` los procedimientos tienen como valor predeterminado el acceso público. Los niveles de acceso se pueden ajustar con los modificadores de acceso.

Un `Function` procedimiento puede declarar el tipo de datos del valor que devuelve el procedimiento. Puede especificar cualquier tipo de datos o el nombre de una enumeración, una estructura, una clase o una interfaz. Si no especifica el `returntype` parámetro, el procedimiento devuelve `Object` .

Si este procedimiento usa la `Implements` palabra clave, la clase o estructura contenedora también debe tener una `Implements` instrucción que siga inmediatamente a su `Class` `Structure` instrucción o. La `Implements` instrucción debe incluir cada interfaz especificada en `implementslist` . Sin embargo, el nombre por el que una interfaz define `Function` (en `definedname` ) no tiene que coincidir con el nombre de este procedimiento (en `name` ).

> [!NOTE]
> Puede usar expresiones lambda para definir expresiones de función alineadas. Para obtener más información, vea [expresión de función](../operators/function-expression.md) y [expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="returning-from-a-function"></a>Devolver desde una función

Cuando el `Function` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento.

Para devolver un valor de una función, puede asignar el valor al nombre de la función o incluirlo en una `Return` instrucción.

La `Return` instrucción asigna simultáneamente el valor devuelto y sale de la función, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

En el ejemplo siguiente se asigna el valor devuelto al nombre de la función `myFunction` y, a continuación, se usa la `Exit Function` instrucción para devolver.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

Las `Exit Function` `Return` instrucciones y producen una salida inmediata de un `Function` procedimiento. Cualquier número de `Exit Function` `Return` instrucciones y puede aparecer en cualquier parte del procedimiento y se pueden mezclar `Exit Function` e `Return` instrucciones.

Si utiliza `Exit Function` sin asignar un valor a `name` , el procedimiento devuelve el valor predeterminado para el tipo de datos especificado en `returntype` . Si `returntype` no se especifica, el procedimiento devuelve `Nothing` , que es el valor predeterminado de `Object` .

## <a name="calling-a-function"></a>Llamar a una función

Se llama a un `Function` procedimiento mediante el nombre del procedimiento, seguido de la lista de argumentos entre paréntesis, en una expresión. Solo se pueden omitir los paréntesis si no se proporcionan argumentos. Sin embargo, el código es más legible si siempre incluye los paréntesis.

Puede llamar a un `Function` procedimiento de la misma manera que llama a cualquier función de biblioteca como `Sqrt` , `Cos` o `ChrW` .

También puede llamar a una función mediante la `Call` palabra clave. En ese caso, se omite el valor devuelto. No se recomienda el uso de la `Call` palabra clave en la mayoría de los casos. Para obtener más información, consulte [instrucción call](call-statement.md).

A veces Visual Basic reorganiza las expresiones aritméticas para aumentar la eficacia interna. Por ese motivo, no debe utilizar un `Function` procedimiento en una expresión aritmética cuando la función cambia el valor de las variables en la misma expresión.

## <a name="async-functions"></a>Funciones asincrónicas

La característica *Async* le permite invocar funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.

Si marca una función con el modificador [Async](../modifiers/async.md) , puede usar el operador [Await](../operators/await-operator.md) en la función. Cuando el control alcanza una `Await` expresión de la `Async` función, el control vuelve al autor de la llamada y el progreso de la función se suspende hasta que se completa la tarea esperada. Una vez completada la tarea, la ejecución puede reanudarse en la función.

> [!NOTE]
> Un `Async` procedimiento vuelve al autor de la llamada cuando encuentra el primer objeto esperado que aún no se ha completado o se llega al final del `Async` procedimiento, lo que ocurra primero.

Una `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task> . A continuación se proporciona un ejemplo de una `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> .

Una `Async` función no puede declarar ningún parámetro [ByRef](../modifiers/byref.md) .

Una [instrucción Sub](sub-statement.md) también se puede marcar con el `Async` modificador. Se utiliza principalmente para los controladores de eventos, donde no se puede devolver un valor. `Async` `Sub` No se puede esperar un procedimiento y el autor de la llamada de un `Async` `Sub` procedimiento no puede detectar las excepciones producidas por el `Sub` procedimiento.

Para obtener más información sobre `Async` las funciones, vea [programación asincrónica con Async y Await](../../programming-guide/concepts/async/index.md), [flujo de control en programas asincrónicos](../../programming-guide/concepts/async/control-flow-in-async-programs.md)y [tipos de valor devueltos asincrónicos](../../programming-guide/concepts/async/async-return-types.md).

## <a name="iterator-functions"></a>Funciones de iterador

Una función de *iterador* realiza una iteración personalizada en una colección, como una lista o una matriz. Una función de iterador utiliza la instrucción [yield](yield-statement.md) para devolver cada elemento de uno en uno. Cuando se alcanza una instrucción [yield](yield-statement.md) , se recuerda la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.

Se llama a un iterador desde el código de cliente mediante un método [for each... Instrucción siguiente](for-each-next-statement.md) .

El tipo de valor devuelto de una función de iterador puede ser <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> .

Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la `Function` instrucción para declarar el nombre, los parámetros y el código que forman el cuerpo de un `Function` procedimiento. El `ParamArray` modificador permite que la función acepte un número variable de argumentos.

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se invoca la función declarada en el ejemplo anterior.

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, `DelayAsync` es un `Async` `Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> . `DelayAsync` tiene una instrucción `Return` que devuelve un entero. Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)` . Dado que el tipo de valor devuelto es `Task(Of Integer)` , la evaluación de la `Await` expresión en `DoSomethingAsync` genera un entero. Esto se muestra en esta declaración: `Dim result As Integer = Await delayTask` .

El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento. Dado `DoSomethingAsync` que es una `Async` función, se debe esperar a la tarea de la llamada a `DoSomethingAsync` , como se muestra en la siguiente instrucción: `Await DoSomethingAsync()` . El `startButton_Click` `Sub` procedimiento debe definirse con el `Async` modificador porque tiene una `Await` expresión.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>Vea también

- [Instrucción Sub](sub-statement.md)
- [Procedimientos de función](../../programming-guide/language-features/procedures/function-procedures.md)
- [Lista de parámetros](parameter-list.md)
- [Instrucción Dim](dim-statement.md)
- [Instrucción Call](call-statement.md)
- [De](of-clause.md)
- [Matrices de parámetros](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [Procedimiento Uso de clases genéricas](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Solución de problemas de procedimientos](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Expresión Function](../operators/function-expression.md)
