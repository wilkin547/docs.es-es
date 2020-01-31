---
title: Function (procedimientos)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: d7a0293e2ec520c2278f67156be56315d1def2b5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76780079"
---
# <a name="function-procedures-visual-basic"></a>Procedimientos de función (Visual Basic)

Un procedimiento `Function` es una serie de instrucciones de Visual Basic incluidas en las instrucciones `Function` y `End Function`. El procedimiento `Function` realiza una tarea y, a continuación, devuelve el control al código de llamada. Cuando devuelve el control, también devuelve un valor al código de llamada.

Cada vez que se llama al procedimiento, sus instrucciones se ejecutan, empezando por la primera instrucción ejecutable después de la instrucción `Function` y terminando por la primera instrucción `End Function`, `Exit Function`o `Return` encontrada.

Puede definir una `Function` procedimiento en un módulo, clase o estructura. Es `Public` de forma predeterminada, lo que significa que se puede llamar desde cualquier parte de la aplicación que tenga acceso al módulo, clase o estructura en la que se definió.

Un procedimiento `Function` puede tomar argumentos, como constantes, variables o expresiones, que se le pasan mediante el código de llamada.

## <a name="declaration-syntax"></a>Sintaxis de declaración

La sintaxis para declarar un procedimiento `Function` es la siguiente:

```vb
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType
    [Statements]
End Function
```

Los *Modificadores* pueden especificar el nivel de acceso y la información relacionada con la sobrecarga, el reemplazo, el uso compartido y el sombreado. Para obtener más información, vea [function (instrucción](../../../language-reference/statements/function-statement.md)).

Los parámetros se declaran de la misma manera que para [los procedimientos sub](./sub-procedures.md).

### <a name="data-type"></a>Tipo de datos

Cada `Function` procedimiento tiene un tipo de datos, al igual que cada variable. Este tipo de datos se especifica mediante la cláusula `As` en la instrucción `Function` y determina el tipo de datos del valor que la función devuelve al código de llamada. En las declaraciones de ejemplo siguientes se muestra esto.

```vb
Function Yesterday() As Date
End Function

Function FindSqrt(radicand As Single) As Single
End Function
```

Para obtener más información, vea "Parts" en la [instrucción function](../../../language-reference/statements/function-statement.md).

### <a name="returning-values"></a>Devolver valores

El valor que un procedimiento `Function` devuelve al código de llamada se denomina su valor devuelto. El procedimiento devuelve este valor de una de estas dos maneras:

- Usa la instrucción `Return` para especificar el valor devuelto y devuelve el control inmediatamente al programa que realiza la llamada. En el ejemplo siguiente se ilustra esto.

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement immediately transfers control back
      ' to the calling code and returns the value of Expression.
      Return Expression
  End Function
  ```

- Asigna un valor a su propio nombre de función en una o más instrucciones del procedimiento. El control no vuelve al programa que realiza la llamada hasta que se ejecuta una instrucción `Exit Function` o `End Function`. En el ejemplo siguiente se ilustra esto.

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement does not transfer control back to the calling code.
      FunctionName = Expression
      ' When control returns to the calling code, Expression is the return value.
  End Function
  ```

La ventaja de asignar el valor devuelto al nombre de la función es que el control no vuelve del procedimiento hasta que encuentra una instrucción `Exit Function` o `End Function`. Esto le permite asignar un valor preliminar y ajustarlo más adelante si es necesario.

Para obtener más información sobre cómo devolver valores, vea [function (instrucción](../../../language-reference/statements/function-statement.md)). Para obtener información sobre cómo devolver matrices, vea [matrices](../arrays/index.md).

## <a name="calling-syntax"></a>Sintaxis de llamada

Para invocar un procedimiento `Function`, incluya su nombre y sus argumentos en el lado derecho de una instrucción de asignación o en una expresión. Debe proporcionar valores para todos los argumentos que no son opcionales y debe incluir la lista de argumentos entre paréntesis. Si no se proporciona ningún argumento, puede omitir los paréntesis opcionalmente.

La sintaxis de una llamada a un procedimiento `Function` es la siguiente.

*lvalue*`=`*functionname* `[(` *argumentlist* `)]`

`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`*expresión* `) Then`

Cuando se llama a un procedimiento de `Function`, no es necesario usar su valor devuelto. Si no es así, se realizan todas las acciones de la función, pero se omite el valor devuelto. a menudo se llama a <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> de esta manera.

### <a name="illustration-of-declaration-and-call"></a>Ilustración de declaration y Call

En el procedimiento `Function` siguiente se calcula el lado más largo o la hipotenusa de un triángulo de la derecha, dados los valores de los otros dos lados.

[!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`.

[!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]

## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Subprocedimientos](./sub-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)
- [Devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)
- [Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
