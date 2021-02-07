---
description: 'Más información acerca de: instrucción Operator'
title: Operator Statement
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
ms.openlocfilehash: f6a8ae2ac51e8bc8fe1be0de3549004b9dda4ef4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768823"
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

## <a name="parts"></a>Partes

`attrlist`  
Opcional. Vea [lista de atributos](attribute-list.md).

`Public`  
Necesario. Indica que este procedimiento de operador tiene acceso [público](../modifiers/public.md) .

`Overloads`  
Opcional. Vea [sobrecargas](../modifiers/overloads.md).

`Shared`  
Necesario. Indica que este procedimiento de operador es un procedimiento [compartido](../modifiers/shared.md) .

`Shadows`  
Opcional. Vea [Shadows](../modifiers/shadows.md).

`Widening`  
Obligatorio para un operador de conversión a menos que especifique `Narrowing` . Indica que este procedimiento de operador define una conversión de [ampliación](../modifiers/widening.md) . Vea "conversiones de ampliación y de restricción" en esta página de ayuda.

`Narrowing`  
Obligatorio para un operador de conversión a menos que especifique `Widening` . Indica que este procedimiento de operador define una conversión de [restricción](../modifiers/narrowing.md) . Vea "conversiones de ampliación y de restricción" en esta página de ayuda.

`operatorsymbol`  
Necesario. Símbolo o identificador del operador que define este procedimiento de operador.

`operand1`  
Necesario. El nombre y el tipo del operando único de un operador unario (incluido un operador de conversión) o el operando izquierdo de un operador binario.

`operand2`  
Requerido para los operadores binarios. Nombre y tipo del operando derecho de un operador binario.

`operand1` y `operand2` tienen la sintaxis y las partes siguientes:

`[ ByVal ] operandname [ As operandtype ]`

|Parte|Descripción|
|----------|-----------------|
|`ByVal`|Opcional, pero el mecanismo de paso debe ser [ByVal](../modifiers/byval.md).|
|`operandname`|Necesario. Nombre de la variable que representa este operando. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`operandtype`|Opcional a menos que `Option Strict` sea `On` . Tipo de datos de este operando.|

`type`  
Opcional a menos que `Option Strict` sea `On` . Tipo de datos del valor que el procedimiento del operador devuelve.

`statements`  
Opcional. Bloque de instrucciones que ejecuta el procedimiento de operador.

`returnvalue`  
Necesario. Valor que el procedimiento del operador devuelve al código de llamada.

`End` `Operator`  
Necesario. Finaliza la definición de este procedimiento de operador.

## <a name="remarks"></a>Observaciones

Solo se puede usar `Operator` en una clase o estructura. Esto significa que el contexto de la *declaración* de un operador no puede ser un archivo de código fuente, un espacio de nombres, un módulo, una interfaz, un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

Todos los operadores deben ser `Public Shared` . No se puede especificar `ByRef` , `Optional` ni `ParamArray` para ninguno de los operandos.

No se puede utilizar el símbolo de operador o el identificador para contener un valor devuelto. Debe utilizar la `Return` instrucción y debe especificar un valor. Cualquier número de `Return` instrucciones puede aparecer en cualquier parte del procedimiento.

La definición de un operador de este modo se denomina *sobrecarga de operadores*, tanto si se usa la `Overloads` palabra clave como si no. En la tabla siguiente se enumeran los operadores que se pueden definir.

|Tipo|Operadores|
|----------|---------------|
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|Conversión (unaria)|`CType`|

Tenga en cuenta que el `=` operador de la lista binaria es el operador de comparación, no el operador de asignación.

Al definir `CType` , debe especificar `Widening` o `Narrowing` .

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

- Si define los `IsTrue` operadores y `IsFalse` , ambos deben devolver el `Boolean` tipo.

- Si define los `<<` operadores y `>>` , ambos deben especificar el `Integer` tipo para el `operandtype` de `operand2` .

El tipo de valor devuelto no tiene que corresponder al tipo de uno de los operandos. Por ejemplo, un operador de comparación como `=` o `<>` puede devolver `Boolean` aunque ninguno de los operandos sea `Boolean` .

## <a name="logical-and-bitwise-operators"></a>Operadores lógicos y bit a bit

Los `And` `Or` operadores,, `Not` y `Xor` pueden realizar operaciones lógicas o bit a bit en Visual Basic. Sin embargo, si define uno de estos operadores en una clase o estructura, solo puede definir su operación bit a bit.

No se puede definir el `AndAlso` operador directamente con una `Operator` instrucción. Sin embargo, puede usar `AndAlso` si ha cumplido las condiciones siguientes:

- Ha definido `And` en los mismos tipos de operando que desea usar para `AndAlso` .

- La definición de `And` devuelve el mismo tipo que la clase o estructura en la que se ha definido.

- Ha definido el `IsFalse` operador en la clase o estructura en la que ha definido `And` .

Del mismo modo, puede utilizar `OrElse` si ha definido `Or` en los mismos operandos, con el tipo de valor devuelto de la clase o la estructura, y ha definido `IsTrue` en la clase o estructura.

## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions

Una *conversión de ampliación* siempre se realiza correctamente en tiempo de ejecución, mientras que una *conversión de restricción* puede producir un error en tiempo de ejecución. Para obtener más información, consulta [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

Si declara que un procedimiento de conversión es `Widening` , el código de procedimiento no debe generar ningún error. Esto significa lo siguiente:

- Siempre debe devolver un valor válido de tipo `type` .

- Debe administrar todas las excepciones posibles y otras condiciones de error.

- Debe controlar cualquier devolución de error de cualquier procedimiento al que llame.

Si existe la posibilidad de que un procedimiento de conversión no se lleve a cabo correctamente o de que pueda provocar una excepción no controlada, debe declararlo como `Narrowing` .

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente `Operator` se usa la instrucción para definir el contorno de una estructura que incluye procedimientos de operador para los `And` `Or` operadores,, `IsFalse` y `IsTrue` . `And` y `Or` cada uno de ellos toman dos operandos de tipo `abc` y tipo de valor devuelto `abc` . `IsFalse` y `IsTrue` cada toman un solo operando de tipo `abc` y devuelven `Boolean` . Estas definiciones permiten que el código de llamada use `And` ,, `AndAlso` `Or` y `OrElse` con operandos de tipo `abc` .

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a>Vea también

- [Operador IsFalse](../operators/isfalse-operator.md)
- [Operador IsTrue](../operators/istrue-operator.md)
- [Widening](../modifiers/widening.md)
- [Narrowing](../modifiers/narrowing.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Procedimientos de operador](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Procedimiento para definir un operador](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Procedimiento para definir un operador de conversión](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Procedimiento para llamar a un procedimiento de operador](../../programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [Procedimiento para usar una clase que define operadores](../../programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
