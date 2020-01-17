---
title: Sub (procedimientos)
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: 9ca1d302a0bc8e989e0b2dddf8cce68e89211d57
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163818"
---
# <a name="sub-procedures-visual-basic"></a>Procedimientos sub (Visual Basic)

Un procedimiento `Sub` es una serie de instrucciones de Visual Basic incluidas en las instrucciones `Sub` y `End Sub`. El procedimiento `Sub` realiza una tarea y, a continuación, devuelve el control al código de llamada, pero no devuelve un valor al código de llamada.

Cada vez que se llama al procedimiento, se ejecutan sus instrucciones, comenzando por la primera instrucción ejecutable después de la instrucción `Sub` y finalizando con la primera instrucción `End Sub`, `Exit Sub`o `Return` encontrada.

Puede definir una `Sub` procedimiento en módulos, clases y estructuras. De forma predeterminada, es `Public`, lo que significa que se puede llamar desde cualquier parte de la aplicación que tenga acceso al módulo, clase o estructura en la que se definió. El término *método* describe un procedimiento `Sub` o `Function` al que se tiene acceso desde fuera de su módulo de definición, clase o estructura. Para más información, vea [Procedimientos en Visual Basic](./index.md).

Un procedimiento `Sub` puede tomar argumentos, como constantes, variables o expresiones, que se le pasan mediante el código de llamada.

## <a name="declaration-syntax"></a>Sintaxis de declaración

La sintaxis para declarar un procedimiento `Sub` es la siguiente:

```vb
[modifiers] Sub SubName[(parameterList)]
    ' Statements of the Sub procedure.
End Sub
```

El `modifiers` puede especificar el nivel de acceso e información sobre la sobrecarga, el reemplazo, el uso compartido y el sombreado. Para obtener más información, vea [Sub Statement](../../../language-reference/statements/sub-statement.md).

## <a name="parameter-declaration"></a>Declaración de parámetros

Cada parámetro de procedimiento se declara de forma similar a como se declara una variable, especificando el nombre del parámetro y el tipo de datos. También puede especificar el mecanismo de paso y si el parámetro es opcional o una matriz de parámetros.

La sintaxis de cada parámetro de la lista de parámetros es la siguiente:

```vb
[Optional] [ByVal | ByRef] [ParamArray] parameterName As DataType
```

Si el parámetro es opcional, también debe proporcionar un valor predeterminado como parte de su declaración. La sintaxis para especificar un valor predeterminado es la siguiente:

```vb
Optional [ByVal | ByRef]  parameterName As DataType = defaultValue
```

### <a name="parameters-as-local-variables"></a>Parámetros como variables locales

Cuando el control pasa al procedimiento, cada parámetro se trata como una variable local. Esto significa que su duración es la misma que la del procedimiento y su ámbito es todo el procedimiento.

## <a name="calling-syntax"></a>Sintaxis de llamada

Invoca un procedimiento `Sub` explícitamente con una instrucción de llamada independiente. No se puede llamar mediante su nombre en una expresión. Debe proporcionar valores para todos los argumentos que no son opcionales y debe incluir la lista de argumentos entre paréntesis. Si no se proporciona ningún argumento, puede omitir los paréntesis opcionalmente. El uso de la palabra clave `Call` es opcional, pero no se recomienda.

La sintaxis de una llamada a un procedimiento `Sub` es la siguiente:

```vb
[Call] SubName[(argumentlist)]
```

Puede llamar a un método `Sub` desde fuera de la clase que lo define. En primer lugar, debe usar la palabra clave `New` para crear una instancia de la clase o llamar a un método que devuelva una instancia de la clase. Para obtener más información, vea [New (operador](../../../language-reference/operators/new-operator.md)). A continuación, puede usar la siguiente sintaxis para llamar al método `Sub` en el objeto de instancia:

```vb
object.MethodName[(argumentList)]
```

### <a name="illustration-of-declaration-and-call"></a>Ilustración de declaration y Call

En el siguiente procedimiento de `Sub` se indica al operador de equipo qué tarea está a punto de realizar la aplicación y también se muestra una marca de tiempo. En lugar de duplicar este código al inicio de cada tarea, la aplicación simplemente llama a `tellOperator` desde varias ubicaciones. Cada llamada pasa una cadena en el argumento `task` que identifica la tarea que se va a iniciar.

[!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]

En el ejemplo siguiente se muestra una llamada típica a `tellOperator`.

[!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]

## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Sub (instrucción)](../../../language-reference/statements/sub-statement.md)
- [Llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [Cómo: llamar a un controlador de eventos en Visual Basic](./how-to-call-an-event-handler.md)
