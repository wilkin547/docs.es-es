---
description: 'Más información acerca de: sub Statement (Visual Basic)'
title: Instrucción Sub
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
ms.openlocfilehash: 9be40c8284c677a151e4b1665f0b49e5f852bf00
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740995"
---
# <a name="sub-statement-visual-basic"></a>Sub (Instrucción, Visual Basic)

Declara el nombre, los parámetros y el código que definen un `Sub` procedimiento.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a>Partes

- `attributelist`

  Opcional. Vea [lista de atributos](attribute-list.md).

- `Partial`

  Opcional. Indica la definición de un método parcial. Vea [métodos parciales](../../programming-guide/language-features/procedures/partial-methods.md).

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

- `name`

  Necesario. Nombre del procedimiento. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md). Para crear un procedimiento de constructor para una clase, establezca el nombre de un `Sub` procedimiento en la `New` palabra clave. Para obtener más información, vea [duración del objeto: cómo se crean y destruyen los objetos](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

- `typeparamlist`

  Opcional. Lista de parámetros de tipo para un procedimiento genérico. Consulte [lista de tipos](type-list.md).

- `parameterlist`

  Opcional. Lista de nombres de variables locales que representan los parámetros de este procedimiento. Vea [lista de parámetros](parameter-list.md).

- `Implements`

  Opcional. Indica que este procedimiento implementa uno o más `Sub` procedimientos, cada uno de ellos definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento. Vea [Implements (instrucción](implements-statement.md)).

- `implementslist`

  Es necesario si se proporciona `Implements`. Lista de procedimientos `Sub` que se implementan.

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

  Opcional. Bloque de instrucciones que se ejecutarán dentro de este procedimiento.

- `End Sub`

  Finaliza la definición de este procedimiento.

## <a name="remarks"></a>Observaciones

Todo el código ejecutable debe estar dentro de un procedimiento. Use un `Sub` procedimiento cuando no desee devolver un valor al código de llamada. Use un `Function` procedimiento cuando desee devolver un valor.

## <a name="defining-a-sub-procedure"></a>Definir un procedimiento Sub

Solo puede definir un `Sub` procedimiento en el nivel de módulo. El contexto de la declaración para un procedimiento Sub debe, por tanto, ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

`Sub` los procedimientos tienen como valor predeterminado el acceso público. Puede ajustar sus niveles de acceso mediante los modificadores de acceso.

Si el procedimiento usa la `Implements` palabra clave, la clase contenedora o la estructura deben tener una `Implements` instrucción que siga inmediatamente a su `Class` `Structure` instrucción o. La `Implements` instrucción debe incluir cada interfaz especificada en `implementslist` . Sin embargo, el nombre por el que una interfaz define `Sub` (en `definedname` ) no tiene que coincidir con el nombre de este procedimiento (en `name` ).

## <a name="returning-from-a-sub-procedure"></a>Devolver desde un procedimiento Sub

Cuando un `Sub` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción después de la instrucción que lo llamó.

En el ejemplo siguiente se muestra un valor devuelto de un `Sub` procedimiento.

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

Las `Exit Sub` `Return` instrucciones y producen una salida inmediata de un `Sub` procedimiento. Cualquier número de `Exit Sub` `Return` instrucciones y puede aparecer en cualquier parte del procedimiento y se pueden mezclar `Exit Sub` e `Return` instrucciones.

## <a name="calling-a-sub-procedure"></a>Llamar a un procedimiento Sub

Llame a un `Sub` procedimiento mediante el nombre del procedimiento en una instrucción y, a continuación, siga ese nombre con su lista de argumentos entre paréntesis. Solo se pueden omitir los paréntesis si no se proporcionan argumentos. Sin embargo, el código es más legible si siempre incluye los paréntesis.

Un `Sub` procedimiento y un `Function` procedimiento pueden tener parámetros y realizar una serie de instrucciones. Sin embargo, un `Function` procedimiento devuelve un valor y un `Sub` procedimiento no. Por lo tanto, no se puede usar un `Sub` procedimiento en una expresión.

Puede usar la `Call` palabra clave al llamar a un `Sub` procedimiento, pero esa palabra clave no se recomienda para la mayoría de los usos. Para obtener más información, consulte [instrucción call](call-statement.md).

A veces Visual Basic reorganiza las expresiones aritméticas para aumentar la eficacia interna. Por ese motivo, si la lista de argumentos incluye expresiones que llaman a otros procedimientos, no debe asumir que se llamará a esas expresiones en un orden determinado.

## <a name="async-sub-procedures"></a>Procedimientos sub asincrónicos

Mediante el uso de la característica Async, puede invocar funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.

Si marca un procedimiento con el modificador [Async](../modifiers/async.md) , puede usar el operador [Await](../operators/await-operator.md) en el procedimiento. Cuando el control alcanza una `Await` expresión en el `Async` procedimiento, el control vuelve al autor de la llamada y el progreso en el procedimiento se suspende hasta que se completa la tarea esperada. Una vez completada la tarea, la ejecución puede reanudarse en el procedimiento.

> [!NOTE]
> Un `Async` procedimiento vuelve al llamador cuando se encuentra el primer objeto esperado que aún no se ha completado o hasta que se alcanza el final del `Async` procedimiento, lo que suceda primero.

También puede marcar una [instrucción function](function-statement.md) con el `Async` modificador. Una `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task> . Un ejemplo más adelante en este tema muestra una `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> .

`Async``Sub`los procedimientos se utilizan principalmente para los controladores de eventos, donde no se puede devolver un valor. `Async` `Sub` No se puede esperar a un procedimiento y el autor de la llamada de un `Async` `Sub` procedimiento no puede detectar las excepciones que `Sub` inicia el procedimiento.

Un `Async` procedimiento no puede declarar ningún parámetro [ByRef](../modifiers/byref.md) .

Para obtener más información sobre `Async` los procedimientos, consulte [programación asincrónica con Async y Await](../../programming-guide/concepts/async/index.md), [flujo de control en programas asincrónicos](../../programming-guide/concepts/async/control-flow-in-async-programs.md)y [tipos de valor devueltos asincrónicos](../../programming-guide/concepts/async/async-return-types.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la `Sub` instrucción para definir el nombre, los parámetros y el código que forman el cuerpo de un `Sub` procedimiento.

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, `DelayAsync` es un `Async` `Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> . `DelayAsync` tiene una instrucción `Return` que devuelve un entero. Por consiguiente, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)` . Dado que el tipo de valor devuelto es `Task(Of Integer)` , la evaluación de la `Await` expresión en `DoSomethingAsync` genera un entero, como se muestra en la siguiente instrucción: `Dim result As Integer = Await delayTask` .

El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento. Dado `DoSomethingAsync` que es una `Async` función, se debe esperar a la tarea de la llamada a `DoSomethingAsync` , como se muestra en la siguiente instrucción: `Await DoSomethingAsync()` . El `startButton_Click` `Sub` procedimiento debe definirse con el `Async` modificador porque tiene una `Await` expresión.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>Vea también

- [Implements (Instrucción)](implements-statement.md)
- [Instrucción Function](function-statement.md)
- [Lista de parámetros](parameter-list.md)
- [Instrucción Dim](dim-statement.md)
- [Instrucción Call](call-statement.md)
- [De](of-clause.md)
- [Matrices de parámetros](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [Procedimiento Uso de clases genéricas](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Solución de problemas de procedimientos](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Métodos Partial](../../programming-guide/language-features/procedures/partial-methods.md)
