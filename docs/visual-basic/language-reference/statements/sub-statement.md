---
title: Sub (Instrucción)
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: da498a5e0a3633eb98882aaed145fcd21ab169fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346442"
---
# <a name="sub-statement-visual-basic"></a>Sub (Instrucción, Visual Basic)

Declara el nombre, los parámetros y el código que definen un procedimiento `Sub`.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a>Elementos

- `attributelist`

  Opcional. Vea [lista de atributos](attribute-list.md).

- `Partial`

  Opcional. Indica la definición de un método parcial. Vea [métodos parciales](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).

- `accessmodifier`

  Opcional. Puede ser uno de los siguientes:

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Private](../modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Opcional. Puede ser uno de los siguientes:

  - [Sobrecargas](../modifiers/overloads.md)

  - [Overrides](../modifiers/overrides.md)

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

- `name`

  Obligatorio. Nombre del procedimiento. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Para crear un procedimiento de constructor para una clase, establezca el nombre de una `Sub` procedimiento en la palabra clave `New`. Para obtener más información, vea [duración del objeto: cómo se crean y destruyen los objetos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

- `typeparamlist`

  Opcional. Lista de parámetros de tipo para un procedimiento genérico. Consulte [lista de tipos](type-list.md).

- `parameterlist`

  Opcional. Lista de nombres de variables locales que representan los parámetros de este procedimiento. Vea [lista de parámetros](parameter-list.md).

- `Implements`

  Opcional. Indica que este procedimiento implementa uno o varios procedimientos de `Sub`, cada uno de los cuales se define en una interfaz implementada por la clase o estructura contenedora de este procedimiento. Vea [Implements (instrucción](implements-statement.md)).

- `implementslist`

  Es necesario si se proporciona `Implements`. Lista de procedimientos `Sub` que se implementan.

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

  Opcional. Bloque de instrucciones que se ejecutarán dentro de este procedimiento.

- `End Sub`

  Finaliza la definición de este procedimiento.

## <a name="remarks"></a>Comentarios

Todo el código ejecutable debe estar dentro de un procedimiento. Use un procedimiento `Sub` cuando no desee devolver un valor al código de llamada. Use una `Function` procedimiento cuando desee devolver un valor.

## <a name="defining-a-sub-procedure"></a>Definir un procedimiento Sub

Solo puede definir un procedimiento `Sub` en el nivel de módulo. El contexto de la declaración para un procedimiento Sub debe, por tanto, ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

`Sub` procedimientos tienen como valor predeterminado el acceso público. Puede ajustar sus niveles de acceso mediante los modificadores de acceso.

Si el procedimiento usa la palabra clave `Implements`, la clase o estructura contenedora debe tener una instrucción `Implements` que siga inmediatamente a su instrucción `Class` o `Structure`. La instrucción `Implements` debe incluir cada interfaz que se especifica en `implementslist`. Sin embargo, el nombre por el que una interfaz define el `Sub` (en `definedname`) no tiene que coincidir con el nombre de este procedimiento (en `name`).

## <a name="returning-from-a-sub-procedure"></a>Devolver desde un procedimiento Sub

Cuando un procedimiento `Sub` devuelve al código de llamada, la ejecución continúa con la instrucción después de la instrucción que lo llamó.

En el ejemplo siguiente se muestra un valor devuelto de un procedimiento `Sub`.

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

Las instrucciones `Exit Sub` y `Return` producen una salida inmediata de un procedimiento de `Sub`. Cualquier número de instrucciones `Exit Sub` y `Return` puede aparecer en cualquier parte del procedimiento y se pueden mezclar instrucciones `Exit Sub` y `Return`.

## <a name="calling-a-sub-procedure"></a>Llamar a un procedimiento Sub

Llame a un procedimiento de `Sub` mediante el nombre del procedimiento en una instrucción y, a continuación, siga ese nombre con su lista de argumentos entre paréntesis. Solo se pueden omitir los paréntesis si no se proporcionan argumentos. Sin embargo, el código es más legible si siempre incluye los paréntesis.

Un procedimiento de `Sub` y un procedimiento `Function` pueden tener parámetros y realizar una serie de instrucciones. Sin embargo, un procedimiento `Function` devuelve un valor y un procedimiento `Sub` no. Por lo tanto, no se puede usar un procedimiento `Sub` en una expresión.

Puede usar la palabra clave `Call` al llamar a un procedimiento de `Sub`, pero esa palabra clave no se recomienda para la mayoría de los usos. Para obtener más información, consulte [instrucción call](call-statement.md).

A veces Visual Basic reorganiza las expresiones aritméticas para aumentar la eficacia interna. Por ese motivo, si la lista de argumentos incluye expresiones que llaman a otros procedimientos, no debe asumir que se llamará a esas expresiones en un orden determinado.

## <a name="async-sub-procedures"></a>Procedimientos sub asincrónicos

Mediante el uso de la característica Async, puede invocar funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.

Si marca un procedimiento con el modificador [Async](../modifiers/async.md) , puede usar el operador [Await](../../../visual-basic/language-reference/operators/await-operator.md) en el procedimiento. Cuando el control alcanza una expresión de `Await` en el procedimiento de `Async`, el control vuelve al llamador y el progreso en el procedimiento se suspende hasta que se completa la tarea esperada. Una vez completada la tarea, la ejecución puede reanudarse en el procedimiento.

> [!NOTE]
> Un procedimiento `Async` vuelve al llamador cuando se encuentra el primer objeto esperado que aún no se ha completado o hasta que se alcanza el final del procedimiento `Async`, lo que ocurra primero.

También puede marcar una [instrucción de función](function-statement.md) con el modificador `Async`. Una función `Async` puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>. Un ejemplo más adelante en este tema muestra una función `Async` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.

`Async` `Sub` procedimientos se utilizan principalmente para los controladores de eventos, donde no se puede devolver un valor. No se puede esperar a un procedimiento de `Sub` de `Async`, y el llamador de un procedimiento de `Sub` de `Async` no puede detectar las excepciones que produce el procedimiento `Sub`.

Un procedimiento `Async` no puede declarar ningún parámetro [ByRef](../modifiers/byref.md) .

Para obtener más información sobre los procedimientos de `Async`, vea [programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flujo de control en programas asincrónicos](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)y [tipos de valor devueltos asincrónicos](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la instrucción `Sub` para definir el nombre, los parámetros y el código que forman el cuerpo de un procedimiento `Sub`.

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, `DelayAsync` es un `Function` de `Async` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>. `DelayAsync` tiene una instrucción `Return` que devuelve un entero. Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)`. Dado que el tipo de valor devuelto es `Task(Of Integer)`, la evaluación de la expresión de `Await` en `DoSomethingAsync` genera un entero, como se muestra en la siguiente instrucción: `Dim result As Integer = Await delayTask`.

El procedimiento `startButton_Click` es un ejemplo de un procedimiento `Async Sub`. Dado que `DoSomethingAsync` es una función `Async`, se debe esperar la tarea para la llamada a `DoSomethingAsync`, como se muestra en la siguiente instrucción: `Await DoSomethingAsync()`. El procedimiento de `Sub` de `startButton_Click` debe definirse con el modificador `Async` porque tiene una expresión de `Await`.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>Vea también

- [Implements (instrucción)](implements-statement.md)
- [Function (instrucción)](function-statement.md)
- [Lista de parámetros](parameter-list.md)
- [Dim (instrucción)](dim-statement.md)
- [Call (instrucción)](call-statement.md)
- [Of](of-clause.md)
- [Matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Solución de problemas de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Métodos Partial](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
