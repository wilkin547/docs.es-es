---
description: 'Más información sobre: procedimientos de operador (Visual Basic)'
title: Procedimientos de operador
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 836eeb2e705a96c49b5fa53e277ccf025d1915b2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100479964"
---
# <a name="operator-procedures-visual-basic"></a>Procedimientos de operador (Visual Basic)

Un procedimiento de operador es una serie de instrucciones Visual Basic que definen el comportamiento de un operador estándar (como `*` , `<>` o `And` ) en una clase o estructura que ha definido. Esto también se denomina *sobrecarga de operadores*.

## <a name="when-to-define-operator-procedures"></a>Cuándo definir procedimientos de operador

Cuando haya definido una clase o estructura, puede declarar variables para que sean del tipo de esa clase o estructura. A veces, una variable de este tipo debe participar en una operación como parte de una expresión. Para ello, debe ser un operando de un operador.

Visual Basic define operadores solo en sus tipos de datos fundamentales. Puede definir el comportamiento de un operador cuando uno o ambos operandos son del tipo de la clase o estructura.

Para obtener más información, vea [Operator Statement](../../../language-reference/statements/operator-statement.md).

## <a name="types-of-operator-procedure"></a>Tipos de procedimientos de operador

Un procedimiento de operador puede ser uno de los siguientes tipos:

- Definición de un operador unario en el que el argumento es del tipo de la clase o estructura.

- Definición de un operador binario en el que al menos uno de los argumentos es del tipo de la clase o estructura.

- Definición de un operador de conversión en el que el argumento es del tipo de la clase o estructura.

- Definición de un operador de conversión que devuelve el tipo de la clase o estructura.

 Los operadores de conversión siempre son unarios y siempre se usan `CType` como el operador que se está definiendo.

## <a name="declaration-syntax"></a>Sintaxis de la declaración

La sintaxis para declarar un procedimiento de operador es la siguiente:

```vb
Public Shared [Widening | Narrowing] Operator operatorsymbol ( operand1 [,  operand2 ]) As datatype

' Statements of the operator procedure.

End Operator
```

La `Widening` `Narrowing` palabra clave o solo se usa en un operador de conversión de tipos. El símbolo del operador siempre es la [función ctype](../../../language-reference/functions/ctype-function.md) para un operador de conversión de tipos.

Se declaran dos operandos para definir un operador binario y se declara un operando para definir un operador unario, incluido un operador de conversión de tipos. Se deben declarar todos los operandos `ByVal` .

Cada operando se declara de la misma manera que se declaran los parámetros para [los procedimientos sub](./sub-procedures.md).

### <a name="data-type"></a>Tipo de datos

Dado que está definiendo un operador en una clase o estructura que ha definido, al menos uno de los operandos debe ser del tipo de datos de esa clase o estructura. Para un operador de conversión de tipos, el operando o el tipo de valor devuelto debe ser del tipo de datos de la clase o estructura.

Para obtener más información, vea [Operator Statement](../../../language-reference/statements/operator-statement.md).

## <a name="calling-syntax"></a>Sintaxis de llamada

Un procedimiento de operador se invoca implícitamente mediante el símbolo de operador en una expresión. Los operandos se proporcionan de la misma manera que para los operadores predefinidos.

La sintaxis de una llamada implícita a un procedimiento de operador es la siguiente:

`Dim testStruct As`  *structurename*

`Dim testNewStruct As`  *structurename* `= testStruct` *símbolodeoperador*      `10`

### <a name="illustration-of-declaration-and-call"></a>Ilustración de declaration y Call

La siguiente estructura almacena un valor entero de 128 bits con signo como el componente de orden superior y de orden inferior. Define el `+` operador para sumar dos `veryLong` valores y generar un `veryLong` valor resultante.

[!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]

En el ejemplo siguiente se muestra una llamada típica al `+` operador definido en `veryLong` .

[!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]

## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Procedimientos Sub](./sub-procedures.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedad](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Procedimiento para definir un operador](./how-to-define-an-operator.md)
- [Procedimiento para definir un operador de conversión](./how-to-define-a-conversion-operator.md)
- [Procedimiento para llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)
- [Procedimiento para usar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)
