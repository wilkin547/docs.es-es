---
title: Lista de parámetros (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: 0dded7fd68256b9b9de8ebe4b48073eb40696c12
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582181"
---
# <a name="parameter-list-visual-basic"></a>Lista de parámetros (Visual Basic)

Especifica los parámetros que un procedimiento espera cuando se llama. Varios parámetros se separan mediante comas. A continuación se encuentra la sintaxis de un parámetro.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a>Elementos

`attributelist`  
Opcional. Lista de atributos que se aplican a este parámetro. Debe incluir la [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) entre corchetes angulares ("`<`" y "`>`").

`Optional`  
Opcional. Especifica que este parámetro no es necesario cuando se llama al procedimiento.

`ByVal`  
Opcional. Especifica que el procedimiento no puede reemplazar o volver a asignar el elemento variable subyacente al argumento correspondiente en el código de llamada.

`ByRef`  
Opcional. Especifica que el procedimiento puede modificar el elemento variable subyacente en el código de llamada de la misma manera que el propio código de llamada puede.

`ParamArray`  
Opcional. Especifica que el último parámetro de la lista de parámetros es una matriz opcional de elementos del tipo de datos especificado. Esto permite al código de llamada pasar un número arbitrario de argumentos al procedimiento.

`parametername`  
Requerido. Nombre de la variable local que representa el parámetro.

`parametertype`  
Es obligatorio si se `On` `Option Strict`. Tipo de datos de la variable local que representa el parámetro.

`defaultvalue`  
Obligatorio para los parámetros de `Optional`. Cualquier expresión constante o constante que se evalúe como el tipo de datos del parámetro. Si el tipo es `Object`, o una clase, una interfaz, una matriz o una estructura, el valor predeterminado solo se puede `Nothing`.

## <a name="remarks"></a>Comentarios

Los parámetros se incluyen entre paréntesis y se separan mediante comas. Un parámetro se puede declarar con cualquier tipo de datos. Si no se especifica `parametertype`, el valor predeterminado es `Object`.

Cuando el código de llamada llama al procedimiento, pasa un *argumento* a cada parámetro necesario. Para obtener más información, vea [diferencias entre parámetros y argumentos](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).

El argumento que el código de llamada pasa a cada parámetro es un puntero a un elemento subyacente en el código de llamada. Si este elemento no es *variable* (una constante, un literal, una enumeración o una expresión), es imposible que cualquier código lo cambie. Si es un elemento *variable* (una variable declarada, un campo, una propiedad, un elemento de matriz o un elemento de estructura), el código de llamada puede cambiarlo. Para obtener más información, vea [diferencias entre argumentos modificables y no modificables](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).

Si se pasa un elemento variable `ByRef`, el procedimiento también lo puede cambiar. Para obtener más información, vea [diferencias entre pasar un argumento por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).

## <a name="rules"></a>Reglas

- **Paréntesis.** Si especifica una lista de parámetros, debe escribirla entre paréntesis. Si no hay ningún parámetro, todavía puede usar paréntesis que incluyan una lista vacía. Esto mejora la legibilidad del código al aclarar que el elemento es un procedimiento.

- **Parámetros opcionales.** Si usa el modificador `Optional` en un parámetro, todos los parámetros subsiguientes de la lista también deben ser opcionales y declararse mediante el modificador `Optional`.

     Cada declaración de parámetro opcional debe proporcionar la cláusula `defaultvalue`.

     Para obtener más información, vea [parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).

- **Matrices de parámetros.** Debe especificar `ByVal` para un parámetro `ParamArray`.

     No puede usar `Optional` y `ParamArray` en la misma lista de parámetros.

     Para obtener más información, consulte [matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).

- **Pasando el mecanismo.** El mecanismo predeterminado para cada argumento es `ByVal`, lo que significa que el procedimiento no puede cambiar el elemento variable subyacente. Sin embargo, si el elemento es un tipo de referencia, el procedimiento puede modificar el contenido o los miembros del objeto subyacente, aunque no puede reemplazar o volver a asignar el propio objeto.

- **Nombres de parámetro.** Si el tipo de datos del parámetro es una matriz, siga `parametername` inmediatamente entre paréntesis. Para obtener más información sobre los nombres de parámetros, vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra un procedimiento `Function` que define dos parámetros.

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
