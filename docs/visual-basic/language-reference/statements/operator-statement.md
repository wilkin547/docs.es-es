---
title: Operator (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: c4fae40992fa665121aff637ae427ef0cafbf547
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582383"
---
# <a name="operator-statement"></a>Operator Statement

Declara el símbolo del operador, los operandos y el código que definen un procedimiento de operador en una clase o estructura.

## <a name="syntax"></a>Sintaxis

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a>Elementos

`attrlist`  
Opcional. Vea [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).

`Public`  
Requerido. Indica que este procedimiento de operador tiene acceso [público](../../../visual-basic/language-reference/modifiers/public.md) .

`Overloads`  
Opcional. Vea [sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md).

`Shared`  
Requerido. Indica que este procedimiento de operador es un procedimiento [compartido](../../../visual-basic/language-reference/modifiers/shared.md) .

`Shadows`  
Opcional. Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

`Widening`  
Obligatorio para un operador de conversión a menos que especifique `Narrowing`. Indica que este procedimiento de operador define una conversión de [ampliación](../../../visual-basic/language-reference/modifiers/widening.md) . Vea "conversiones de ampliación y de restricción" en esta página de ayuda.

`Narrowing`  
Obligatorio para un operador de conversión a menos que especifique `Widening`. Indica que este procedimiento de operador define una conversión de [restricción](../../../visual-basic/language-reference/modifiers/narrowing.md) . Vea "conversiones de ampliación y de restricción" en esta página de ayuda.

`operatorsymbol`  
Requerido. Símbolo o identificador del operador que define este procedimiento de operador.

`operand1`  
Requerido. El nombre y el tipo del operando único de un operador unario (incluido un operador de conversión) o el operando izquierdo de un operador binario.

`operand2`  
Requerido para los operadores binarios. Nombre y tipo del operando derecho de un operador binario.

`operand1` y `operand2` tienen la sintaxis y las partes siguientes:

`[ ByVal ] operandname [ As operandtype ]`

|Parte|Descripción|
|----------|-----------------|
|`ByVal`|Opcional, pero el mecanismo de paso debe ser [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).|
|`operandname`|Requerido. Nombre de la variable que representa este operando. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
|`operandtype`|Opcional a menos que se `On` `Option Strict`. Tipo de datos de este operando.|

`type`  
Opcional a menos que se `On` `Option Strict`. Tipo de datos del valor que el procedimiento del operador devuelve.

`statements`  
Opcional. Bloque de instrucciones que ejecuta el procedimiento de operador.

`returnvalue`  
Requerido. Valor que el procedimiento del operador devuelve al código de llamada.

`End` `Operator`  
Requerido. Finaliza la definición de este procedimiento de operador.

## <a name="remarks"></a>Comentarios

Solo se puede usar `Operator` en una clase o estructura. Esto significa que el contexto de la *declaración* de un operador no puede ser un archivo de código fuente, un espacio de nombres, un módulo, una interfaz, un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

Todos los operadores deben ser `Public Shared`. No se puede especificar `ByRef`, `Optional` o `ParamArray` para ninguno de los operandos.

No se puede utilizar el símbolo de operador o el identificador para contener un valor devuelto. Debe utilizar la instrucción `Return` y debe especificar un valor. Cualquier número de instrucciones `Return` puede aparecer en cualquier parte del procedimiento.

La definición de un operador de este modo se denomina *sobrecarga de operadores*, tanto si se usa la palabra clave `Overloads` como si no. En la tabla siguiente se enumeran los operadores que se pueden definir.

|Type|Operadores|
|----------|---------------|
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|Conversión (unaria)|`CType`|

Tenga en cuenta que el operador `=` de la lista binaria es el operador de comparación, no el operador de asignación.

Al definir `CType`, debe especificar `Widening` o `Narrowing`.

## <a name="matched-pairs"></a>Pares coincidentes

Debe definir ciertos operadores como pares coincidentes. Si define un operador de este tipo, debe definir también el otro. Los pares coincidentes son los siguientes:

- `=` y `<>`

- `>` y `<`

- `>=` y `<=`

- `IsTrue` y `IsFalse`

## <a name="data-type-restrictions"></a>Restricciones de tipos de datos

Cada operador que defina debe incluir la clase o estructura en la que se define. Esto significa que la clase o estructura debe aparecer como el tipo de datos de lo siguiente:

- Operando de un operador unario.

- Al menos uno de los operandos de un operador binario.

- El operando o el tipo de valor devuelto de un operador de conversión.

 Ciertos operadores tienen restricciones de tipo de datos adicionales, como se indica a continuación:

- Si define los operadores `IsTrue` y `IsFalse`, ambos deben devolver el tipo de `Boolean`.

- Si define los operadores `<<` y `>>`, ambos deben especificar el tipo de `Integer` para la `operandtype` de `operand2`.

El tipo de valor devuelto no tiene que corresponder al tipo de uno de los operandos. Por ejemplo, un operador de comparación como `=` o `<>` puede devolver `Boolean` aunque no se `Boolean` ninguno de los operandos.

## <a name="logical-and-bitwise-operators"></a>Operadores lógicos y bit a bit

Los operadores `And`, `Or`, `Not` y `Xor` pueden realizar operaciones lógicas o bit a bit en Visual Basic. Sin embargo, si define uno de estos operadores en una clase o estructura, solo puede definir su operación bit a bit.

No se puede definir el operador de `AndAlso` directamente con una instrucción `Operator`. Sin embargo, puede usar `AndAlso` si ha cumplido las condiciones siguientes:

- Ha definido `And` en los mismos tipos de operando que desea usar para `AndAlso`.

- La definición de `And` devuelve el mismo tipo que la clase o estructura en la que se ha definido.

- Ha definido el operador de `IsFalse` en la clase o estructura en la que ha definido `And`.

Del mismo modo, puede utilizar `OrElse` si ha definido `Or` en los mismos operandos, con el tipo de valor devuelto de la clase o estructura, y ha definido `IsTrue` en la clase o estructura.

## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions

Una *conversión de ampliación* siempre se realiza correctamente en tiempo de ejecución, mientras que una *conversión de restricción* puede producir un error en tiempo de ejecución. Para obtener más información, consulta [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

Si declara un procedimiento de conversión para que se `Widening`, el código de procedimiento no debe generar ningún error. Esto significa lo siguiente:

- Siempre debe devolver un valor válido de tipo `type`.

- Debe administrar todas las excepciones posibles y otras condiciones de error.

- Debe controlar cualquier devolución de error de cualquier procedimiento al que llame.

Si existe la posibilidad de que un procedimiento de conversión no se lleve a cabo correctamente o de que se produzca una excepción no controlada, debe declararlo como `Narrowing`.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se usa la instrucción `Operator` para definir el contorno de una estructura que incluye procedimientos de operador para los operadores `And`, `Or`, `IsFalse` y `IsTrue`. `And` y `Or` tienen dos operandos de tipo `abc` y `abc` de tipo de valor devuelto. `IsFalse` y `IsTrue` toman un único operando de tipo `abc` y devuelven `Boolean`. Estas definiciones permiten que el código de llamada use `And`, `AndAlso`, `Or` y `OrElse` con operandos de tipo `abc`.

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a>Vea también

- [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [IsTrue (operador)](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Widening](../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Llamar a un procedimiento de operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [Utilizar una clase que define operadores](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
