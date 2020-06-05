---
title: Operadores de concatenación
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: c123438a86a2c3293a99770107d970535fcdbdf8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388795"
---
# <a name="concatenation-operators-in-visual-basic"></a>Operadores de concatenación en Visual Basic

Los operadores de concatenación unen varias cadenas en una sola. Existen dos operadores de concatenación: `+` y `&`. Ambos efectúan la operación de concatenación básica, como se aprecia en el siguiente ejemplo.

```vb
Dim x As String = "Mic" & "ro" & "soft"
Dim y As String = "Mic" + "ro" + "soft"
' The preceding statements set both x and y to "Microsoft".
```

Estos operadores también concatenan variables de `String`, como indica el siguiente ejemplo.

[!code-vb[VbVbalrOperators#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#76)]

## <a name="differences-between-the-two-concatenation-operators"></a>Diferencias entre los dos operadores de concatenación

El [operador +](../../../language-reference/operators/addition-operator.md) tiene el propósito principal de sumar dos números. aunque también puede concatenar operandos numéricos con operandos de cadena. El operador `+` posee un conjunto de reglas complejo que establecen si hay que sumar, concatenar, señalar un error de compilador o generar una excepción <xref:System.InvalidCastException> en tiempo de ejecución.

El [operador&](../../../language-reference/operators/concatenation-operator.md) solo se define para los `String` operandos y siempre amplía sus operandos a `String` , independientemente de la configuración de `Option Strict` . El uso del operador `&` es recomendable para concatenar cadenas, ya que se está expresamente definido para cadenas y reduce las probabilidades de generar una conversión inintencionada.

## <a name="performance-string-and-stringbuilder"></a>Rendimiento: cadena y StringBuilder

Si realiza una cantidad considerable de manipulaciones en una cadena (como concatenaciones, eliminaciones y reemplazos), el rendimiento puede verse beneficiado si usa la clase <xref:System.Text.StringBuilder> del espacio de nombres <xref:System.Text>. Esta clase toma una instrucción extra para crear e inicializar un objeto <xref:System.Text.StringBuilder>, así como otra instrucción para convertir su valor final a una `String`, pero este tiempo se puede recuperar, ya que el rendimiento de <xref:System.Text.StringBuilder> es más rápido.

## <a name="see-also"></a>Consulte también

- [Option Strict (instrucción)](../../../language-reference/statements/option-strict-statement.md)
- [Tipos de métodos de manipulación de cadenas en Visual Basic](../strings/types-of-string-manipulation-methods.md)
- [Operadores aritméticos en Visual Basic](arithmetic-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Operadores lógicos y bit a bit en Visual Basic](logical-and-bitwise-operators.md)
