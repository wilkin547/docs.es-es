---
description: 'Más información sobre: procedimientos de función (Visual Basic)'
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
ms.openlocfilehash: 4997059fc33fb5d438519356b2c9fdd9e6a27cce
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436154"
---
# <a name="function-procedures-visual-basic"></a>Procedimientos de función (Visual Basic)

Un `Function` procedimiento es una serie de instrucciones Visual Basic incluidas en las `Function` `End Function` instrucciones y. El `Function` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada. Cuando devuelve el control, también devuelve un valor al código de llamada.

Cada vez que se llama al procedimiento, sus instrucciones se ejecutan, empezando por la primera instrucción ejecutable después de la `Function` instrucción y terminando por la primera `End Function` `Exit Function` instrucción, o `Return` encontrada.

Puede definir un `Function` procedimiento en un módulo, clase o estructura. Es de `Public` forma predeterminada, lo que significa que se puede llamar desde cualquier parte de la aplicación que tenga acceso al módulo, clase o estructura en la que se definió.

Un `Function` procedimiento puede aceptar argumentos, como constantes, variables o expresiones, que se le pasan por el código de llamada.

## <a name="declaration-syntax"></a>Sintaxis de declaración

La sintaxis para declarar un `Function` procedimiento es la siguiente:

```vb
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType
    [Statements]
End Function
```

Los *Modificadores* pueden especificar el nivel de acceso y la información relacionada con la sobrecarga, el reemplazo, el uso compartido y el sombreado. Para obtener más información, vea [function (instrucción](../../../language-reference/statements/function-statement.md)).

Los parámetros se declaran de la misma manera que para [los procedimientos sub](./sub-procedures.md).

### <a name="data-type"></a>Tipo de datos

Cada `Function` procedimiento tiene un tipo de datos, al igual que cada variable. Este tipo de datos se especifica mediante la `As` cláusula en la `Function` instrucción y determina el tipo de datos del valor que la función devuelve al código de llamada. En las declaraciones de ejemplo siguientes se muestra esto.

```vb
Function Yesterday() As Date
End Function

Function FindSqrt(radicand As Single) As Single
End Function
```

Para obtener más información, vea "Parts" en la [instrucción function](../../../language-reference/statements/function-statement.md).

### <a name="returning-values"></a>Devolver valores

El valor `Function` que un procedimiento devuelve al código de llamada se denomina su valor devuelto. El procedimiento devuelve este valor de una de estas dos maneras:

- Usa la `Return` instrucción para especificar el valor devuelto y devuelve el control inmediatamente al programa que realiza la llamada. Esto se ilustra en el siguiente ejemplo:

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement immediately transfers control back
      ' to the calling code and returns the value of Expression.
      Return Expression
  End Function
  ```

- Asigna un valor a su propio nombre de función en una o más instrucciones del procedimiento. El control no vuelve al programa que realiza la llamada hasta que `Exit Function` `End Function` se ejecuta una instrucción o. Esto se ilustra en el siguiente ejemplo:

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement does not transfer control back to the calling code.
      FunctionName = Expression
      ' When control returns to the calling code, Expression is the return value.
  End Function
  ```

La ventaja de asignar el valor devuelto al nombre de la función es que el control no vuelve del procedimiento hasta que encuentra una `Exit Function` `End Function` instrucción o. Esto le permite asignar un valor preliminar y ajustarlo más adelante si es necesario.

Para obtener más información sobre cómo devolver valores, vea [function (instrucción](../../../language-reference/statements/function-statement.md)). Para obtener información sobre cómo devolver matrices, vea [matrices](../arrays/index.md).

## <a name="calling-syntax"></a>Sintaxis de llamada

Para invocar un `Function` procedimiento, incluya su nombre y sus argumentos en el lado derecho de una instrucción de asignación o en una expresión. Debe proporcionar valores para todos los argumentos que no son opcionales y debe incluir la lista de argumentos entre paréntesis. Si no se proporciona ningún argumento, puede omitir los paréntesis opcionalmente.

La sintaxis de una llamada a un `Function` procedimiento es la siguiente.

valor *l* `=` *nombrefunción* `[(` *argumentlist*    `)]`

`If ((`*nombrefunción* `[(` *argumentlist* `)] / 3) <=` *expresión* de  `) Then`

Cuando se llama a un `Function` procedimiento, no es necesario usar su valor devuelto. Si no es así, se realizan todas las acciones de la función, pero se omite el valor devuelto. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> a menudo se llama de esta manera.

### <a name="illustration-of-declaration-and-call"></a>Ilustración de declaration y Call

En el `Function` procedimiento siguiente se calcula el lado más largo o la hipotenusa de un triángulo de la derecha, dados los valores de los otros dos lados.

[!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

En el ejemplo siguiente se muestra una llamada típica a `hypotenuse` .

[!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]

## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Procedimientos Sub](./sub-procedures.md)
- [Procedimientos de propiedad](./property-procedures.md)
- [Procedimientos de operador](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Instrucción Function](../../../language-reference/statements/function-statement.md)
- [Procedimiento para crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)
- [Procedimiento para devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)
- [Procedimiento para llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
