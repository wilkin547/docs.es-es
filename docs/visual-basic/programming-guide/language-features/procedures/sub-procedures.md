---
description: 'Más información sobre: procedimientos sub (Visual Basic)'
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
ms.openlocfilehash: fe9d26fb2d18fbd29820af7aca96b826d7b45d0b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466515"
---
# <a name="sub-procedures-visual-basic"></a>Procedimientos sub (Visual Basic)

Un `Sub` procedimiento es una serie de instrucciones Visual Basic incluidas en las `Sub` `End Sub` instrucciones y. El `Sub` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada, pero no devuelve un valor al código de llamada.

Cada vez que se llama al procedimiento, se ejecutan sus instrucciones, comenzando por la primera instrucción ejecutable después de la `Sub` instrucción y terminando por la primera `End Sub` `Exit Sub` instrucción, o `Return` encontrada.

Puede definir un `Sub` procedimiento en módulos, clases y estructuras. De forma predeterminada, es `Public` , lo que significa que se puede llamar desde cualquier parte de la aplicación que tenga acceso al módulo, la clase o la estructura en la que se definió. El término *método* describe un `Sub` `Function` procedimiento o al que se tiene acceso desde fuera de su módulo de definición, clase o estructura. Para más información, vea [Procedimientos en Visual Basic](./index.md).

Un `Sub` procedimiento puede aceptar argumentos, como constantes, variables o expresiones, que se le pasan por el código de llamada.

## <a name="declaration-syntax"></a>Sintaxis de declaración

La sintaxis para declarar un `Sub` procedimiento es la siguiente:

```vb
[modifiers] Sub SubName[(parameterList)]
    ' Statements of the Sub procedure.
End Sub
```

`modifiers`Puede especificar el nivel de acceso e información sobre la sobrecarga, el reemplazo, el uso compartido y el sombreado. Para obtener más información, vea [Sub Statement](../../../language-reference/statements/sub-statement.md).

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

Un procedimiento se invoca `Sub` explícitamente con una instrucción de llamada independiente. No se puede llamar mediante su nombre en una expresión. Debe proporcionar valores para todos los argumentos que no son opcionales y debe incluir la lista de argumentos entre paréntesis. Si no se proporciona ningún argumento, puede omitir los paréntesis opcionalmente. El uso de la `Call` palabra clave es opcional, pero no se recomienda.

La sintaxis de una llamada a un `Sub` procedimiento es la siguiente:

```vb
[Call] SubName[(argumentlist)]
```

Puede llamar a un `Sub` método desde fuera de la clase que lo define. En primer lugar, debe usar la `New` palabra clave para crear una instancia de la clase o llamar a un método que devuelva una instancia de la clase. Para obtener más información, vea [New (operador](../../../language-reference/operators/new-operator.md)). A continuación, puede usar la siguiente sintaxis para llamar al `Sub` método en el objeto de instancia:

```vb
object.MethodName[(argumentList)]
```

### <a name="illustration-of-declaration-and-call"></a>Ilustración de declaration y Call

El siguiente `Sub` procedimiento indica al operador de equipo qué tarea está a punto de realizar la aplicación y también muestra una marca de tiempo. En lugar de duplicar este código al inicio de cada tarea, la aplicación simplemente llama `tellOperator` desde varias ubicaciones. Cada llamada pasa una cadena en el `task` argumento que identifica la tarea que se va a iniciar.

[!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]

En el ejemplo siguiente se muestra una llamada típica a `tellOperator` .

[!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]

## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedad](./property-procedures.md)
- [Procedimientos de operador](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Instrucción Sub](../../../language-reference/statements/sub-statement.md)
- [Procedimiento apara llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [Cómo: Llamar a un controlador de eventos en Visual Basic](./how-to-call-an-event-handler.md)
